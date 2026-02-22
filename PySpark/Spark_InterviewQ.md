
# Spark 

## 🚀 Basic-Level

<details>
  <summary> <b> 1. What is Apache Spark and why is it faster than Hadoop MapReduce ? </b>  </summary>

→ Apache `Spark` is **a distributed data processing framework** designed for fast, large-scale data processing. 

It is faster than `Hadoop MapReduce` mainly because :
- Spark processes data **in memory (RAM)**, while MapReduce writes intermediate results to disk.

- Spark supports **DAG execution**, optimizing the entire workflow.

- Spark enables **lazy evaluation**, reducing unnecessary computations.

- It supports multiple workloads (**batch processing, streaming processing, ML, SQL Analytics**) in one engine.

> **Spark is faster primarily due to in-memory computation and DAG optimization.**

#
</details>


<details>
  <summary> <b> 2. Difference between RDD, DataFrame, and Dataset. </b>  </summary>

→  RDD, DataFrame, and Dataset

| Feature      | RDD       | DataFrame          | Dataset                  |
| ------------ | --------- | ------------------ | ------------------------ |
| Level        | Low-level | High-level         | High-level + type safety |
| Schema       | No        | Yes                | Yes                      |
| Optimization | Manual    | Catalyst optimized | Catalyst optimized       |
| Type safety  | Yes       | No                 | Yes                      |
| Performance  | Slowest   | Faster             | Similar to DataFrame     |

- **RDD** → low-level, flexible, but slower
- **DataFrame** → optimized, most commonly used
- **Dataset** → type-safe (mainly in Scala/Java)

> **For Python (PySpark), mostly DataFrames are used.**

#
</details>

<details>
  <summary> <b> 3. What are transformations and actions in Spark?  </b>  </summary>

→ 
**Transformations and actions** are the two fundamental operations in Apache Spark used to process data in a distributed environment.

**1. Transformations**

- Transformations define how data should be manipulated but do not execute immediately.  

- They are **lazy operations**, meaning Spark only records the operations (building a lineage or Directed Acyclic Graph - DAG) and 
does not compute anything until an action is triggered.

- Examples : `map`, `filter`, `select`, `join`, `groupBy`, `flatMap`
 
- These operations **return a new RDD or DataFrame** without changing the original data.

**2. Actions**

- Actions **trigger the actual computation/execution**.  

- They execute the entire lineage of transformations built up by previous operations and **return a result to the driver program** or **write data to output**. 

- Examples: `count`, `collect`, `show`, `write`, `saveAsTextFile`, `write.parquet`

- Actions are eager, meaning they cause Spark to run the job and produce output. 

***Summary of Transformations and Actions***
> The key difference is: **Transformations build the plan; actions execute it**.  <br/>
> This lazy evaluation allows Spark to optimize the execution plan, combine operations, and improve performance. 

#
</details>


<details>
  <summary> <b> 4. What is lazy evaluation in Spark? </b>  </summary>

→ 
**Lazy evaluation** means Spark does not execute transformations immediately. <br/> 
Instead, it builds a logical execution plan (DAG) and executes only when an action is called/triggered.

Benefits:
- Enables optimization
- Reduces unnecessary computation
- Improves performance

Example:
```py
df.filter(col("age") > 30).select("name")
```
Nothing runs until an action like `.show()` is called.

#
</details>

<details>
  <summary> <b> 5. What is a DAG in Spark? </b>  </summary>

→ 
**DAG (Directed Acyclic Graph)** is the logical execution plan of Spark jobs. 

It represents the sequence of transformations to be performed on data.

Flow : **`Job → Stages → Tasks`**

> - **DAG helps Spark optimize execution**
> - **Minimizes shuffles when possible**


#
</details>

<details>
  <summary> <b> 6. What is partitioning in Spark ? </b>  </summary>

→ Partitioning is the process of **dividing data into smaller chunks** that can be processed in parallel across the cluster.

→ Partitions are the basic units of parallelism - each partition is processed by a single task, enabling Spark to execute operations in parallel.

Why it is important:
- Enables parallelism
- Improves performance
- Avoids data skew

→ Spark automatically creates partitions based on factors like HDFS block size (e.g., 128 MB per block in Hadoop v2) or the number of CPU cores.

→ We can also manually control partitioning using transformations like 
- `repartition()` (which triggers a shuffle) or
- `coalesce()` (to reduce partitions more efficiently)

operations :
- `repartition(n)` → increases/decreases with shuffle
- `coalesce(n)` → reduces partitions (no full shuffle)

Partitioning can occur in memory (RDD/DataFrame) or on disk via `partitionBy()` when writing data.

#
</details>


<details>
  <summary> <b> 7. Difference between repartition and coalesce ? </b>  </summary>

→ `repartition()` Vs `coalesce()`
| Feature             | repartition | coalesce     |
| ------------------- | ----------- | ------------ |
| Shuffle             | Yes         | No (usually) |
| Increase partitions | Yes         | No           |
| Decrease partitions | Yes         | Yes          |
| Performance         | Expensive   | Cheaper      |

Golden rule :
> - Use **`repartition()`** when increasing partitions
> - Use **`coalesce()`** when decreasing partitions

#
</details>


<details>
  <summary> <b> 8. What causes shuffling in Spark ? </b>  </summary>

→ Shuffling occurs when data needs to move across partitions/nodes.

→ Common shuffle operations:
- `join`
- `groupBy`
- `reduceByKey`
- `distinct`
- `orderBy`
- `repartition`

Why Shuffling is bad:
- Network I/O heavy
- Disk spill
- Performance bottleneck

#
</details>

<details>
  <summary> <b> 9. What is data skew and how do you handle it ? </b>  </summary>

→ Data skew occurs when some partitions have significantly more data than others, causing certain tasks to run much longer. 

Solutions:
- Salting keys
- Broadcast join
- Repartitioning
- Skew hints (Spark 3)
- Increase parallelism

> **Salting is a technique used in Apache Spark to mitigate data skew**.
> data skew — a condition where certain partitions receive disproportionately more data than others, causing performance bottlenecks.

<details>
  <summary> How It Works : </summary>

1. Identify the skewed key (e.g., a user ID with millions of records). 
2. Add a salt (random number) to the key in the large dataset. 
3. Expand the smaller dataset (e.g., via explode) to include all possible salt values for each key. 
4. Join on the salted key, ensuring even distribution. 
5. Remove the salt after processing if needed.

This balances the workload across executors and prevents slow, overloaded tasks.

```py
from pyspark.sql.functions import rand, floor, concat, lit, explode, array

# Add salt (0–9) to skewed DataFrame
salted_df = skewed_df.withColumn("salt", floor(rand() * 10))
                     .withColumn("salted_key", concat(col("key"), lit("_"), col("salt")))

# Expand small lookup table with all salt values
salt_values = array([lit(i) for i in range(10)])
lookup_salted = lookup_df.withColumn("salt", explode(salt_values)) \
                          .withColumn("salted_key", concat(col("key"), lit("_"), col("salt")))

# Join on salted_key
result = salted_df.join(lookup_salted, "salted_key").drop("salt", "salted_key")   
```

</details>

#
</details>

<details>
  <summary> <b> 10. Explain broadcast join. </b>  </summary>

→ Broadcast join is an optimization where the smaller dataset is sent to all worker nodes to avoid shuffling the large dataset. 

→ Benefit of broadcast join : Avoids expensive shuffle.

When to use broadcast join :
- One table is small (< ~10–100 MB typically)
- Large fact table + small dimension table

PySpark : 
```py
from pyspark.sql.functions import broadcast
df1.join(broadcast(df2), "id")
```

#
</details>

## 🚀 Medium-Level

<details>
  <summary> <b> 1. What is the Catalyst Optimizer ? </b>  </summary>

→ Catalyst is Spark SQL’s query optimizer. 

It automatically optimizes logical and physical query plans to improve performance.

Key responsibilities:
- Logical plan optimization
- Predicate pushdown
- Constant folding
- Join reordering
- Physical plan selection

> **Catalyst is Spark SQL's rule-based and cost-based optimizer that improves query performance automatically**.

> **Catalyst Optimizer works mainly with DataFrame/Dataset, not RDD**.


#
</details>

<details>
  <summary> <b> 2. What is Project Tungsten ? </b>  </summary>

→ Project Tungsten is Spark’s execution engine improvement initiative focused on memory management and CPU efficiency.

Main improvements:
- Off-heap memory management
- Cache-friendly binary processing
- Whole-stage code generation
- Reduced GC overhead

Impact: Faster execution and better resource utilization.

> **Tungsten improves Spark performance at the physical execution level**.

#
</details>

<details>
  <summary> <b> 3. What is the difference between cache() and persist() ? </b>  </summary>

→ Cache() and persist() in Apache Spark are both used to store intermediate results (RDDs, DataFrames, or Datasets) in memory or on disk to avoid recomputation, improving performance. 

**1. `cache()`** <br/>
`cache()` is a shorthand method equivalent to `persist(StorageLevel.MEMORY_ONLY)` for RDDs, but for DataFrames, it defaults to `MEMORY_AND_DISK`. 

It stores data only in memory (or spills to disk if memory is insufficient) and provides no option to customize the storage level.

**2. `persist()`** <br/>
`persist()` offers full control over the storage level. 

You can explicitly specify storage levels such as:
- `MEMORY_ONLY`: Store data in memory only.
- `MEMORY_AND_DISK`: Store in memory first, spill to disk if needed.
- `MEMORY_ONLY_SER`: Store serialized data in memory.
- `MEMORY_AND_DISK_SER`: Store serialized data in memory, spill to disk if needed.
- `DISK_ONLY`: Store data only on disk. 

**Difference between `cache()` and `persist()`**
| Feature             | cache()     | persist()    |
| ------------------- | ----------- | ------------ |
| Default storage     | MEMORY_ONLY | User-defined |
| Flexibility         | No          | Yes          |
| Performance control | Limited     | More control |

Explanation:
- `cache()` = shortcut for `persist(MEMORY_ONLY)`
- `persist()` allows storage levels like:
  - `MEMORY_AND_DISK`
  - `DISK_ONLY`
  - `MEMORY_ONLY_SER`


> Use cache() when you want a simple, default in-memory (or memory+disk) caching for frequently reused data and the default behavior suffices.

> Use persist() when you need fine-grained control over where and how data is stored—especially useful for large datasets that may not fit in memory or when durability and performance trade-offs are critical.

#
</details>

<details>
  <summary> <b> 4. What is checkpointing in Spark ? </b>  </summary>

→ Checkpointing truncates the lineage graph by saving the RDD/DataFrame to reliable storage (like HDFS).

Why checkpointing is needed:
- Prevents very long lineage
- Helps in fault recovery
- Used in iterative algorithms
- Important in streaming

Difference from cache:
- Cache → performance optimization
- Checkpoint → fault tolerance + lineage cut

Key point interviewers expect: checkpoint writes to reliable storage.
#
</details>


<details>
  <summary> <b> 5. Explain narrow vs wide transformations. </b>  </summary>

→ 

**1. Narrow Transformation**

Narrow transformations are operations where each output partition depends on data from only one input partition. 

They do not require data to be shuffled across the cluster, making them fast and efficient.
- **No shuffling** : Data remains within the same partition. 
- **Parallel execution** : Each partition is processed independently. 
- Examples: `map()`, `filter()`, `union()`, `select()`, `flatMap()`.

- No data shuffle
- Each partition depends on one parent partition
- Faster

`These transformations are pipelined within a single stage in Spark’s execution plan, reducing overhead.`

**2. Wide Transformation**

Wide transformations require data from multiple input partitions to compute a single output partition. 

This necessitates a shuffle—data is redistributed across the cluster, which is expensive in terms of I/O, network, and memory.

- **Shuffling involved** : Data is reorganized across partitions, often by key. 
- **Stage boundary** : Each wide transformation creates a new stage in the DAG.
- **Examples** : `groupBy()`, `join()`, `reduceByKey()`, `distinct()`, `orderBy()`. 

- Requires shuffle
- Partition depends on multiple parent partitions
- Expensive

`Shuffles can lead to performance bottlenecks, especially with data skew or large datasets.`


Golden line:
> **Wide transformations cause shuffles; narrow transformations do not**.

#
</details>


<details>
  <summary> <b> 6. Explain Spark Driver vs Executor. </b>  </summary>


**1. Spark Driver**

The Driver is the central coordinator of a Spark application.
- Single instance per application.
- Runs the main program, creates `SparkContext`, and converts code into tasks.
- Builds the execution plan (DAG) and schedules tasks to Executors
- Communicates with the Cluster Manager (e.g., YARN, Mesos) to request resources.
- Tracks task progress and ensures fault tolerance by re-executing failed tasks.
- Collects and returns results to the user.

**2. Spark Executor**

Executors are worker processes that run on cluster nodes and execute tasks. 
- Multiple instances per application (one or more per worker node).
- Launch when `SparkContext` is created and run until the application ends.
- Run tasks assigned by the Driver and store data in memory/disk (e.g., cached RDDs).
- Report task status back to the Driver.
- Manage local memory and CPU for task execution.


**Driver : Brain of the app — manages logic, planning, and coordination**. 

**Executor : Worker — performs actual data processing in parallel**.

> **Driver coordinates; executors do the actual work.**.

#
</details>


<details>
  <summary> <b> 7. How does Spark handle failures ? </b>  </summary>

→ Spark uses RDD lineage for fault tolerance.

Mechanism:
- If a partition is lost → Spark recomputes it using lineage
- Tasks are retried automatically
- Speculative execution handles slow tasks

Important point : No need to replicate intermediate data like Hadoop.

#
</details>

<details>
  <summary> <b> 8. What is speculative execution ? </b>  </summary>

→ Speculative execution detects slow-running tasks (stragglers) and launches duplicate tasks on other executors.

Goal : Reduce job completion time.

When speculative execution is helpful:
- Data skew
- Uneven hardware
- Network issues

Config:
```py
spark.speculation = true
```

#
</details>


<details>
  <summary> <b> 9. What is the difference between groupByKey and reduceByKey ? </b> </summary>

→ 

**`groupByKey`**
- **Groups all values** by key into an iterable (e.g., (key, [v1, v2, ...]))
- **No pre-aggregation** : All values are shuffled across the network as-is
- **High memory and network usage**, especially for large datasets.
- Use when you need to **process all values per key** (e.g., computing median)

**`reduceByKey`**
- **Applies a reduction function** (e.g., sum, max) to combine values per key.
- **Performs local reduction** on each partition **before shuffling**, reducing data transfer. 
- **More efficient** than groupByKey for aggregations like sum or count.


| Feature         | groupByKey | reduceByKey |
| --------------- | ---------- | ----------- |
| Shuffle size    | Large      | Smaller     |
| Pre-aggregation | No         | Yes         |
| Performance     | Slower     | Faster      |
| Memory usage    | High       | Efficient   |


- `groupByKey` shuffles all values

- `reduceByKey` performs map-side aggregation

> **Always prefer `reduceByKey` over `groupByKey` for better performance.**


#
</details>


<details>
  <summary> <b> 10. What are accumulators and broadcast variables? </b> </summary>

→ 

**Accumulators**

Accumulators are write-only variables used for aggregating values across tasks, such as counters or sums. 

- Workers can add to them but cannot read their value. 
- Only the driver can read the final value. 
- Ideal for tracking metrics like error counts or processed records.
- Fault-tolerant: Spark prevents double-counting on task retries. 

Example: Counting invalid data entries across a distributed dataset.

**Broadcast Variables**

Broadcast variables are read-only variables cached on each executor to avoid repeated data transfer. 

- Efficiently share large datasets (e.g., lookup tables, configurations).
- Sent to each node once, reducing network overhead. 
- Immutable: Cannot be modified after broadcast.

Example: Distributing a large reference table for joins or lookups.


> **Accumulators**: Workers update, driver reads (e.g., counters).

> **Broadcast variables** : Driver broadcasts, workers read (e.g., shared data).

Use accumulators for distributed aggregation and broadcast variables for efficient data sharing.

#
</details>
