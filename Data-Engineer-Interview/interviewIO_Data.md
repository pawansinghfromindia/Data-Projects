# Data Engineer Interview Questions


## ETL

<details>
  <summary> <b> Difference Between ETL and ELT </b> </summary>

<br/>

> **ETL and ELT are two data-processing approaches for analytics**. <br/>
> to filter, sort, and clean , prepare, transform this large data volume to make it useful for analytics and
business intelligence. 

<img width="500" height="330" alt="image" src="https://github.com/user-attachments/assets/f853fdee-c279-43e3-94ab-7ec2138ff22a" />

<br/>

MPP(Massively Parallel Processing)



|               ETL                         |                       	ELT                   |
|-------------------------------------------|-----------------------------------------------|
| ***Extract Transform Load***              | ***Extract Load Transform***                  |
| Extract and Transform before loading data | First Extract and Load raw data, transform it later  |
| `Approach` : uses a set of business rules to process data from several sources before centralized integration| `Approach` : loads data as it is and transforms it at a later stage, depending on the use case and analytics requirements |
| `Process` : Takes raw data, transforms it into a predetermined format, then loads it into the target data warehouse | `Process` : Takes raw data, loads it into the target data warehouse, then transforms it just before analytics |
| `Speed`	: ETL is slower than ELT            | `Speed` : ELT is faster than ETL as it can use the internal resources of the data warehouse.|             |                                                                                                                                                                             
| `Costs` : Can be time-consuming and costly to set up depending on ETL tools used | `Costs` : More cost-efficient depending on the ELT infrastructure used |
| `Data compatibility` : Best with structured data | `Data compatibility` : Can handle structured, unstructured, and semi-structure data |
| `Tools`	: Informatica, Talend	              | `Tools` : Databricks, Snowflake, BigQuery, Redshift |


ETL tools are best for smaller datasets, complex transformations, and legacy systems where data quality and 
compliance are critical like Data Protection sectors Health, Military. 

Data scientists mainly use ETL to load legacy databases in the data warehouse, while ELT has become the norm today.
ELT became the modern data integration method for efficient analytics.

[**ETL vs ELT**](https://aws.amazon.com/compare/the-difference-between-etl-and-elt/)

#
</details>

<details>
  <summary> <b> Extraction, Transformation, Load </b> </summary>

<br/>

> **Extraction**

- [x] Extraction is about collecting raw data from different sources.

- [x] These could be databases, files, software as a service (SaaS) applications, Internet of Things (IoT) sensors,
       or application events. 
- [x] We can collect semi-structured, structured, or unstructured data at this stage.


> **Transformation**

- [x] Transformation focuses on changing raw data from its original structure into a format that meets the requirements of
the target system where you plan to store the data for analytics. 

- [x] **Examples of transformation** :
   - Changing data types or formats
   - Removing inconsistent or inaccurate data.
   - Removing data duplication.

- [x] We apply rules and functions to clean and prepare data for analysis in the target system.

There are two types of transformations perform at two different stages:
1. Data Cleansing, Data Preparations, Data Standardization
2. Business Rules and Logics

> **Load**

- [x] In this phase, you store data into the target database system. 

- [x] ETL processes load data as a final step, so that reporting tools can use it directly to generate actionable
      reports and insights. 

- [x] However, in ELT, we still need to transform the extracted data after loading it.

#
</details>

<details>
  <summary> <b> Data types and File Formats </b> </summary>

<br/>

**Data** : 

1. **Structured Data**, Organized in a fixed schema with rows and columns.<br/>
e.g. : relational databases(SQL Tables), spreadsheets, csv files, 

2. **Semi-Structured Data**, Partially organized with tags, metadata, or key-value pairs.<br/>
e.g. : JSON, XML, Parquet, Avro, ORC.

3. **Unstructured Data**, No predefined format or schema; raw and free-form.<br/>
e.g. : audio, images, videos, PDFs, logs, Emails, social media posts.

> 1. Apache Parquet
> - Type: Column based storage.
> - Best for: Analytics and read-heavy workloads (OLAP).
> - Widely used in Spark, Hive, and data lakes
> - High compression and efficient column-level operations
> - Cons: Slower writes; inefficient for small files.

> 2. Apache Avro
> - Type: Row-based storage.
> - Best for: Streaming and write-heavy operations (e.g., Kafka)
> - Fast serialization and compact binary format
> - Cons: Poor compression; not optimized for analytical queries.

> 3. Apache ORC (Optimized Row Columnar)
> - Type: Columnar storage.
> - Best for: High-performance analytics in Hive-based data warehouses. 
> - Highest compression (zlib, Snappy).
> - Built-in indexing, ACID support, and vectorized processing.
> - Cons: Limited tool support outside Hadoop ecosystem


**File Formats** :

Text/CSV: Easy to read but lacks schema and compression.

JSON: Ideal for semi-structured data but can be verbose.

Avro: Schema-based, compact, and supports schema evolution.

Parquet/ORC: Columnar formats optimized for analytics.

Delta Lake: ACID-compliant format for large-scale data lakes.


#
</details>


## Paritioning

<details>
  <summary> <b> What is Data Partitioning? </b> </summary>

<br/>

> Data Partitioning is a technique for dividing large datasets into smaller, manageable chunks called `partitions`.
Each partition contains a subset of data and is distributed across multiple nodes or servers. 

These partitions can be stored, queried, and managed as individual tables, 
though they logically belong to the same dataset. 

Partitioning **improves database performance ⬆️ and scalability ⬆️** as your data grows. <br/>

<details>
  
With the right strategy in place, we can reduce query latency, optimize storage, and simplify maintenance. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/c0cb8697-04ed-465a-a164-ac5da380a3ee" />

<br/>
For instance, searching for a data point in the entire table takes longer and uses more resources than searching 
 for it in a specific partition.  That's why data is stored as partitions.

</details>

#
</details>

<details>
  <summary> <b> Types of Data Partitioning </b> :  </summary>

<br/>

> **Horizontal partitioning**

<details>
  
Instead of storing all the data in a single table, horizontal partitioning ***splits the data into rows***, 
meaning different sets of rows are stored as partitions. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/115f16cd-4008-4d03-b369-3d6727663d93" />

<br/>
<br/>
</details>


  
> **Vertical partitioning**

<details>
  
Vertical partitioning ***divides data by columns***, so each partition contains the same number of rows but fewer columns. 

The ***primary key ( partition column)*** will be present in every partition, maintaining the logical relationship.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/e9abb4e8-0ef9-4689-84cb-14249bb09eaa" />
<br/>
<br/>
</details>


  
> **Range partitioning**

<details>
  
Range partitioning ***splits data based on a range of values*** for a particular column. 

Typically, each partition has a lower and upper bound for the key column, and a record 
that falls within this range is assigned to that partition. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/099382fc-014d-42dc-82b0-ee555210fb58" />
<br/>
<br/>
</details>

  
> **Hash partitioning**

<details>
  
A hash function is applied to the partition key, and the output determines which record should be stored 
in which partition.

In this technique, the number of partitions is decided beforehand. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/1fb4202a-0c9b-478e-b3ca-cd6d7a8a3d69" />
<br/>
<br/>
</details>

  
> **List partitioning**

<details>
  
List partitioning is similar to range partitioning, but instead of dividing data by a range of values,
list partitioning ***divides the data based on a predefined set of values***. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/83558a1c-fad9-4256-b9a0-1ddf9320ae5c" />
<br/>
<br/>
</details>


  
> **Composite partitioning**

<details>

Combination of two partitioning techniques.

A table is first divided using one strategy, and each partition is further divided using another technique.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/ea85aef7-5627-480d-aeca-4e05afce0ca3" />
<br/>
</details>

#
</details>

<details>
  <summary> <b> Use Cases for Data Partitioning </b> </summary>

1. Distributed databases

2. OLAP operations

3. Log management

4. Machine learning pipelines


#
</details>

<details>
  <summary> <b> How to Implement Data Partitioning? </b> </summary>

<br/>

Data partitioning can be implemented in both **SQL**(`MySQL, Microsoft SQL Server, PostgreSQL`) and 
**NoSQL**(`Amazon DynamoDB, MongoDB, Apache Cassandra`) databases.

<details>
  <summary> Step 1: Understand data and access patterns thoroghly </summary>

- [x] Queries, Identify key columns frequently involved
- [x] What data is often accessed, the size of the data, and performance bottlenecks.

</details>

<details>
  <summary> Step 2: Choose a partitioning technique </summary>

- [x] Horizontal partitioning
- [x] Vertical partitioning
- [x] Hybrid approach

</details>

<details>
  <summary> Step 3: Create partitions </summary>

```sql
CREATE TABLE employee(
    firstname VARCHAR(25) NOT NULL,
    username VARCHAR(16) NOT NULL,
    email VARCHAR(35),
    salary INT,
    joining_date DATE NOT NULL
)
PARTITION BY RANGE( YEAR(joining_date) ) (
    PARTITION p1 VALUES LESS THAN (2024),
    PARTITION p2 VALUES LESS THAN (2025),
    PARTITION p3 VALUES LESS THAN (2026)
);
```

```sql
CREATE TABLE employees (
    emp_id INT NOT NULL,
    name VARCHAR(30),
    joining_date DATE NOT NULL DEFAULT '2026-01-01',
    job_id INT,
    location_id INT
)
PARTITION BY HASH(location_id)
PARTITIONS 4;
```
</details>

<details>
  <summary> Step 4: Monitor and optimize partitions </summary>

- [x] Continuously monitor your data operations, ensure the partitions are up-to-date 
- [x] Ensure the data is evenly distributed among partitions; otherwise, you may need to rebalance it. 
- [x] Add more partitions or choose a different approach as the data scales up

</details>

#
</details>

<!------------------------------------------------------------------>

## Processing Data

<details>
  <summary> <b> Batch Processing </b> </summary>

### 📦 Batch Processing

Batch Processing is a method of ***processing large volumes of data at scheduled intervals, 
instead of processing each event immediately***.

> **Process accumulated data in chunks at a specific time**

Data is collected over time → processed together → output generated

**`Source → Ingestion → Storage → Batch Processing → Warehouse → BI Dashboard`**

Batch is very common in : **Data Warehouses | OLAP systems | Reporting systems**

### 🚀 Use Cases of Batch Processing


**1. Sales Reports**
- [x] Daily/weekly revenue summary

**2. ETL Pipelines**
- [x] Transform raw data nightly

**3. Machine Learning Training**
- [x] Train models on historical data

**4. Payroll Processing**
- [x] Salaries calculated monthly

**4. Banking Transactions**
- [x] Interest calculated daily

### ⏳ Batch vs Real-Time (Streaming)

| Feature         | Batch Processing   | Streaming Processing |
| --------------- | ------------------ | -------------------- |
| Processing Time | Scheduled          | Immediate            |
| Data Size       | Large volumes      | Small events         |
| Latency         | High               | Low                  |
| Example         | Daily sales report | Fraud detection      |

#
</details>

<details>
  <summary> <b> Streaming/Real-time Processing </b> </summary>

### ⚡Streaming/Real-time Processing

Streaming Processing is a method of ***processing data in real time (or near real time) as soon as it is generated***.

> **Data is processed continuously, event by event, without waiting**.

Example : A user swipes a credit card 💳 
- The system checks fraud immediately
- Approves or blocks transaction in milliseconds

That’s stream processing.

`Data Source → Message Queue → Stream Processor → Real-Time Output`

**`User Click → Kafka → Spark Streaming → Dashboard Update`**

Data flows continuously.

### 🚀 Use Cases of Stream Processing

**1. Fraud Detection**
- [x] Bank detects suspicious transactions instantly.

**2. Real-Time Dashboards**
- [x] Live sales dashboard updating every second.

**3. Ride-Sharing Apps**
- [x] Matching drivers and riders instantly.

**4. Log Monitoring**
- [x] Detecting system failures immediately.

**5. IoT Devices**
- [x] Temperature sensor alerts in factories.

### 🆚 Batch vs Streaming 

| Feature    | Batch         | Streaming            |
| ---------- | ------------- | -------------------- |
| Processing | Scheduled     | Continuous           |
| Latency    | Minutes/Hours | Milliseconds/Seconds |
| Use Case   | Reports       | Alerts               |
| Data Size  | Large chunks  | Event by event       |
| Complexity | Lower         | Higher               |

### 🏗 Typical Streaming Architecture

```
Event Source
   ↓
Message Broker (Kafka)
   ↓
Stream Processor (Flink / Spark)
   ↓
Real-Time Database / Dashboard

```

### ⚙️ Popular Streaming Tools

Apache Kafka

Apache Flink

Spark Structured Streaming

Amazon Kinesis

Google Pub/Sub

Azure Event Hubs


#
</details>


<!-------------------------------------------------------->
## RDDs , DataFrames, Datasets

<details>
  <summary> <b> The evolution of RDD, DF and DS </b> </summary>

The evolution and usage of three core Apache Spark APIs: 
- [x] **RDDs** (Resilient Distributed Datasets),
- [x] **DataFrames**, and
- [x] **Datasets**.

DataFrames and Datasets were introduced later to address limitations of RDDs by providing structured APIs.

<img width="300" height="250" alt="image" src="https://github.com/user-attachments/assets/e88f860f-6ec0-4a77-bc80-2032bd85be97" />

</details>

<details>
  <summary> <b> RDDs </b></summary>

<br/>

The original fundamental abstraction in Apache Spark.

Represents a logical, distributed collection of immutable, partitioned data across a cluster

> **Resilient** : lineage of operations allows automatic recovery from failures.

> **Immutable** : transformations create new RDDs without altering original data.

> **Compile-time type safety** : RDDs are strongly typed (e.g., RDD[Int], RDD[String]).

> Supports both **structured and unstructured data**, but **does not inherently understand schema**.

RDDs provide unmatched control but at the cost of complexity and limited optimization since Spark treats transformations 
as opaque functions.


**RDDs** :
- [x] When you need fine-grained control over data processing.
- [x] When working with ***unstructured or semi-structured data*** where schema is unknown or irrelevant.
- [x] When you do not require Spark’s automatic optimizations.
- [x] If you are comfortable with ***low-level functional programming*** patterns.


**Limitations of RDDs** :
- [ ] Lack of optimization opportunities because Spark cannot introspect opaque lambda functions.
- [ ] Potential inefficient execution especially in non-JVM languages like Python due to external process calls.
- [ ] Developers must explicitly specify ***how to do computations***, not ***what to do***, which can lead to
      suboptimal performance.

**DataFrames and Datasets** were introduced later to address limitations of RDDs by providing structured APIs.

#
</details>

<details>
  <summary> <b> DataFrames and Datasets </b></summary>

<br/>

Introduced later to address limitations of RDDs by providing structured APIs.

> **DataFrames : Conceptually equivalent to a relational table with named columns and schemas**.

> **Datasets : Typed extension of DataFrames, allowing JVM object representations of rows with compile-time type safety**.


Enable developers to express ***what to do*** declaratively rather than ***how to do*** it.

By using Dataframes and Datasets, Spark ***can optimize queries***

By using Dataframes and Datasets, Spark ***Support better error detection***
- [x] SQL queries may fail at runtime
- [x] DataFrames provide compile-time safety at the method level but runtime errors on column names.
- [x] Datasets offer the highest compile-time safety through typed JVM objects.


Structured APIs (DataFrames and Datasets) allow Spark to “understand” the computation,***enabling powerful query optimizations*** 
through Catalyst and Tungsten.

The future of Spark development is heavily oriented towards ***DataFrames and Datasets***, 
as evidenced by their foundational role in Structured Streaming, ML pipelines, GraphFrames, and integrations with 
deep learning frameworks like TensorFlow

DataFrames and Datasets promote ***cleaner, more readable code and allow early error detection, reducing costly runtime failures***.

**DataFrames and Datasets**:

- [x] For most ETL and analytical workloads where data is structured and schema is known.
- [x] When you want better performance through Spark optimizations.
- [x] If you want code that is readable, maintainable, and declarative.
- [x] When you require compile-time type safety (Datasets in JVM languages).
- [x] When working with modern Spark features like Structured Streaming and ML pipelines.


Note : Datasets combine the best of RDDs (type safety) and DataFrames (query optimization) but are limited to JVM languages.

#
</details>

<details>
  <summary> Dataframe </summary>

<br/>

It is Distributed table with named columns.

Unlike an RDD, in dataframe, data is organized into named columns, like a table in a relational database. 

It is ***Designed to make large data sets processing even easier***.

<img width="867" height="273" alt="image" src="https://github.com/user-attachments/assets/b7a6b7af-ba1a-4197-a37f-534a05ed13cd" />


#
</details>

<details>
  <summary> <b> Datasets </b></summary>

<br/>

Datasets is an extension to Dataframe API, the latest abstraction which tries to provide best of both RDD and Dataframe.

It provides compile time safety which was not available in Data frames.

It is strongly typed version of DataFrame.

#
</details>

<details>
  <summary> <b> Summary of RDDs, DFs, DSs</b></summary>

<br/>

|       	                  | RDDs                  	 |  DataFrames	            | Datasets              |
|---------------------------|--------------------------|--------------------------|-----------------------|
| Abstraction Level :      	| Low-level	               | High-level declarative	  | High-level + type-safe |
| Data Structure :	        | Unstructured or semi-structured |	Structured with schema |	Structured with JVM object type |
| Type Safety :             | Compile-time	Partial (method level compile; | column names runtime)	| Strong compile-time |
| Optimization :            |	Limited (opaque functions)|	Catalyst & Tungsten optimizations |	Catalyst & Tungsten optimizations |
| API Style :               | Imperative (how to do)	| Declarative (what to do)  |	Declarative + typed functional |
| Lazy Evaluation :         | Yes	                    | Yes	                      | Yes                             |
| Ease of Use/Readability : |	More complex, verbose	  | More concise, SQL-like	  | Concise + type-safe |
| Suitable Use Cases :      |	Low-level control, unstructured data	| Most ETL, SQL-like queries	| Typed transformations, JVM integrations |
| Language Support :        |	`Scala`, `Java`, `Python`| `Scala`, `Java`, `Python`| `Scala`, `Java` (no `Python`) |
| Performance	:             | Potentially slower (esp. Python)	| High (optimized physical plans)	| High (optimized physical plans) |


**The importance of structured APIs in Spark** :

> **Understand the trade-offs between control and optimization.**

- [ ] ***RDDs*** will be continued and relevant for the low-level foundation for developer productivity and system performance.
- [ ] Use RDDs selectively when you need custom low-level transformations that are not easily expressed with higher-level APIs.

- [x] The evolution towards ***DataFrames*** and ***Datasets*** aligns Spark with modern data processing paradigms emphasizing 
declarative programming and query optimization.

- [x] Prefer DataFrames and Datasets for better optimization and maintainability.

#
</details>


## Big data

<details>
  <summary> <b> 5 Vs of Big Data </b> </summary>

<br/>

> **1. Volume**

- [x] The sheer ***amount of data*** generated from various sources (e.g., social media, IoT devices).  <br/> 
    Example : Terabytes or petabytes of data stored in data lakes

> **2. Velocity**

- [x] The ***speed at which data is generated***, collected, and processed.  <br/> 
   Example : Real-time data streaming from sensors or financial transactions.

> **3. Variety**

- [x] The ***different types of data*** - structured (databases), semi-structured (JSON, XML), and unstructured
     (videos, audio, images, logs).  <br/> 
    Example : Combining customer emails, social media posts, and transaction records.

> **4. Veracity**

- [x] The ***accuracy, quality, and trustworthiness*** of data. <br/> 
    Example : Ensuring data from multiple sources is clean and reliable before analysis.

> **5. Value**

- [x] The actionable insights and business benefits derived from data.  <br/> 
    Example : Using customer behavior data to improve marketing strategies.


> **Variability**, referring to data that ***changes in meaning or format over time***.   

e.g. : sentiment analysis in social media


#
</details>

<details>
  <summary> <b> What is Data Profiling ?</b> </summary>

### 🏥 Data Profiling

Data Profiling is the process of analyzing datasets to understand their ***structure, content, quality, and relationships*** 
before using them for analytics, reporting, or machine learning.

> Health check-up of our data before using it

### 🚀 Why Data Profiling is important ?

Before building pipelines, dashboards, or ML models, we must have to do data profiling otherwise the bad data leads to
Wrong reports, Poor ML predictions, Business decision errors.

Data Profiling like : <br/>
✔ Is the data complete ? <br/>
✔ Are there null values ? <br/>
✔ Are there duplicates ? <br/>
✔ Are formats consistent ? <br/>
✔ Does the data follow business rules ? <br/>

### 🧩 What does Data Profiling analyze ?

Data profiling usually covers three main areas :

**1️⃣ Structure Analysis (Metadata Profiling)** 

Understand the schema and format of data. e.g. :
- [x] Column names
- [x] Data types (`INT`, `STRING`, `DATE`)
- [x] Number of columns
- [x] Table size
- [x] File format (`CSV`, `Parquet`, `JSON`)

If `Order_Date` is stored as `string` → problem.

**2️⃣ Content Analysis (Column Profiling)** 

Analyze actual values inside columns. For each column:
- [x] Count of rows
- [x] Null count
- [x] Unique count
- [x] Min / Max values
- [x] Average
- [x] Standard deviation
- [x] Most frequent values
- [x] Pattern checks (email format, phone format)

If `salary = -5000` → data issue

**3️⃣ Relationship Analysis (Cross-Column Profiling)**

Checks relationships between columns or tables. e.g. :
- [x] Primary key uniqueness 
- [x] Foreign key validation
- [x] Functional dependency
- [x] Correlation
- [x] Duplicate detection

No duplicate `order_id` as it is a primary key <br/>
`Order.customer_id` must exist in `Customer.customer_id`

### 🛠 Common Data Quality Checks

| Check Type   | Example                     |
| ------------ | --------------------------- |
| Completeness | No missing required fields  |
| Uniqueness   | No duplicate primary keys   |
| Validity     | Email format correct        |
| Consistency  | Date format same everywhere |
| Accuracy     | Sales amount not negative   |
| Range Check  | Age between 0–120           |


**`Source → Ingestion → Data Profiling → Cleaning → Transformation → Storage → Analytics`**



#
</details>


<details>
  <summary> <b> What is Data Governance ?</b> </summary>


### 🏛  Data Governance

Data Governance is the framework of ***policies, processes, standards, and controls*** that ensure :<br/>
**`Data Accuracy` , `Data Security` `Data Availability`, `Data Compliance and Trust`** 

> Data Governance = Rules and control system for managing data properly.

### 🚀 Why Data Governance is important ? 

Since in an organization,  Multiple teams use the same data, Data comes from different systems,  Sensitive information exists (PII, financial data)

Regulations must be followed, Without governance it lead to conflicts.
- Data leaks happen 🔐
- Data Compliance fines occur 💰
- Data Ownership No one knows who owns the data 🤷

✔ Prevent data leaks <br/>
✔ Improve trust in reports  <br/>
✔ Avoid legal penalties  <br/>
✔ Enable secure self-service analytics  <br/>
✔ Maintain consistency across teams like Naming standards enforced <br/>


### 🧩 Key Components of Data Governance

1️⃣ **Data Ownership & Stewardship** defines ***Who owns the data ? | Who maintains it ? | Who approves changes ?***

Data Owner → Responsible for business meaning

Data Steward → Maintains quality

Data Engineer → Builds pipelines

Data Consumer → Uses data

2️⃣ **Data Quality Management** ensures ***No duplicates | No missing critical values | Proper formats | Valid business rules***


3️⃣ **Data Security & Access Control** controls ***Who can view data ? | Who can modify data ? | Who can delete data ?***

Done by using the following techniques : 

Role-Based Access Control (RBAC)

Encryption

Masking sensitive data

4️⃣ **Metadata Management**, Data about data is metadata, It Includes : ***Table definitions | Column descriptions | Data lineage | Source system***

It helps team to understand What it is, Where data came from, How it was transformed etc. Now it is very crucial for training AI Models.


5️⃣ **Data Lineage** is hierarchy of data flow. Data Lineage must be tracked.

**```Source → ETL → Data Warehouse → Dashboard```**

It is Critical for debugging & auditing. like Where did this come from? | What transformation changed it ?


### 🔥 Difference: Data Governance vs Data Management 

| Data Governance    | Data Management       |
| ------------------ | --------------------- |
| Sets rules         | Executes processes    |
| Defines policies   | Implements pipelines  |
| Focuses on control | Focuses on operations |

> **Governance = Strategy and Management = Execution**

#
</details>


## Apache Hadoop/Hadoop

<details>
  <summary> Traditional systems <b>a single machine to Hadoop </b> </summary>

<br/>
  
Traditional systems often struggle with datasets that exceed the capacity of **a single machine**, both in storage and computing. 

Hadoop resolves this by distributing data across many nodes and executing computations in parallel. 


Hadoop is a powerful open-source framework built **to process and store massive datasets** 
**by distributing them across clusters** of affordable, commodity hardware.

Its strength lies in **scalability and flexibility**, enabling it to work with **both structured and unstructured data**.

How it stores, processes, and manages data at scale.

#
</details>

<details>
  <summary> <b> Features of Hadoop </b> </summary>

<br/>

- **Distributed storage and processing** allow it to store extremely large datasets and query them.
- **Horizontal scalability** without requiring high-end machines.
- **Data locality optimization**, moving computation to where the data resides
- **Resilience to failure** via replication and task re-execution.

These features make Hadoop well-suited for batch data processing, log analysis, and ETL pipelines. 

Hadoop is a classic case study in distributed computing, where computation happens across multiple nodes to increase efficiency and scale.

#
</details>

<details>
  <summary> <b> Overview of Hadoop Ecosystem </b> </summary>

<br/>

Hadoop is not a single tool. It’s an ecosystem that includes multiple modules that work together 
to manage data storage, processing, and resource coordination.

**Hadoop consists of four foundational modules** :

> **1. HDFS (Hadoop Distributed File System)**

A distributed storage system that splits files into blocks and distributes them across a cluster.

> **2. MapReduce**

A programming model for processing data in parallel across nodes.

> **3. YARN (Yet Another Resource Negotiator)**

Manages resources and schedules jobs in the cluster.

> 4. **Hadoop Common**

A set of shared libraries and utilities that support other modules.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/bc9cfdeb-6a7f-4b05-9084-915ee75201e3" />

<br/>
These modules work together to create a distributed computing environment capable of handling petabytes of data

#
</details>

<details>
  <summary> MapReduce </summary>

<br/>

Master Node 

Slave Nodes / Worker Nodes

It is needed when we were not able to do computation on a single machine like after horizontal scaling (compute + storage)

To do this we try to divide our job using **Map** and **Reduce** concepts.

First we try to distribute the data into small chunks on different clusters/machines then we have a driver( a start program) which
instead of sharing the data (as it is huge) we share the  code on worker nodes where it does the in memory computation individually.

In first step Map part, we get intermediate result from each of the worker nodes.

In Second step, all the intermediate results will be combined.

HDFS has fault taularance feautures so It has Replication factor (by default data is stored as 3 different blocks)



### 🧠 What is NameNode?

The NameNode is the brain of HDFS.

It does NOT store actual data.
Instead, it stores information about the data (metadata).

### 📦 What Does NameNode Store?

The NameNode stores:

✅ File names

✅ Directory structure

✅ File permissions

✅ Block locations

✅ Replication information


### 🔄 How It Works (Step-by-Step)

🟢 When writing a file:

1. Client requests NameNode to store file.

2. NameNode: <br/>
   Splits file into blocks (default 128MB) <br/>
   Decides which DataNodes will store blocks

4. Client sends actual data directly to DataNodes.

5. DataNodes report back to NameNode.


🔵 When reading a file:

1. Client asks NameNode: “Where is my file?”

2. NameNode replies with block locations.

3. Client directly reads from DataNodes.


### 🧾 Key Responsibilities of NameNode

| Responsibility      | Description                                   |
| ------------------- | --------------------------------------------- |
| Metadata Management | Keeps track of files and blocks               |
| Block Mapping       | Maps blocks → DataNodes                       |
| Replication Control | Ensures data is replicated (default 3 copies) |
| Health Monitoring   | Receives heartbeat from DataNodes             |


```

                Client
                  |
                  v
            +-------------+
            |  NameNode   |  <-- Metadata
            +-------------+
              /    |    \
             /     |     \
            v      v      v
        DataNode DataNode DataNode
        (Block1)  (Block2)  (Block3)
```

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/7feb3934-95ea-4ab7-b4ba-78b85554539c" />

<br/>

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/263bb14c-2c50-4a77-a1a5-d9fc6001feb7" />

<br/>


### NameNode vs DataNode

| Feature             | **NameNode**                             | **DataNode**                   |
| ------------------- | ---------------------------------------- | ------------------------------ |
| Role                | Master node                              | Worker node                    |
| Main job            | Manages metadata                         | Stores actual data             |
| Stores              | File names, block locations, permissions | Real data blocks               |
| Data storage        | ❌ Does NOT store file data               | ✅ Stores file data             |
| Responsibility      | Controls filesystem namespace            | Handles read/write of blocks   |
| Client interaction  | Client contacts first for metadata       | Client transfers data directly |
| Block placement     | Decides where blocks go                  | Follows NameNode instructions  |
| Heartbeat           | Receives heartbeats                      | Sends heartbeats               |
| Block reports       | Receives reports                         | Sends block reports            |
| Replication control | Decides replication factor               | Performs replication           |
| Failure impact      | Critical (cluster may stop)              | Limited (data re-replicated)   |
| Number in cluster   | Usually 1 active (plus standby in HA)    | Many (scales horizontally)     |
| Memory usage        | High (metadata in RAM)                   | Lower compared to NameNode     |
| Startup dependency  | Must start first                         | Starts after NameNode          |
| Analogy             | 🧠 Brain / Librarian                     | 🗄️ Storage / Bookshelf        |


🧠 Summary

> **NameNode = Brain (metadata)**

> **DataNode = Muscle (data storage)**

> - NameNode → Knows locations
> - DataNode → Holds blocks
> - Client → Talks to both

#
</details>

<details>
  <summary> <b> Hadoop Distributed File System (HDFS) </b> </summary>

<br/>

HDFS is primary storage system. It is designed to reliably store the vast amounts of data across a cluster of machines

[HDFS](https://www.databricks.com/glossary/hadoop-distributed-file-system-hdfs)

#
</details>
