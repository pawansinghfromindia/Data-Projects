
# Spark 

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
  <summary> <b>  </b>  </summary>

→ 

#
</details>
