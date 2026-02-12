# Module 3 : Data Engineering Using Databricks
- The evolution of data management (Warehouse, Lake, Lakehouse)
- What Data Engineering is and it evolved
- Core Databricks concepts for Data Engineers
- Medallion Architecture (Data Lakehouse)
- Project : Building the Bike Data Lakehouse


<details>
  <summary> <b> Databricks VS Snowflakes vs Microsoft Fabric </b> </summary>

<br/>

> **Databricks is able of cover all the aspects of data** like Data Engineering, Data Analytics, Data Science and even now they're going in the directions
 of Transactional Application(OLTP), not only limited to OLAP. They want to cover everything, in last 2 years they changed many things.

> **Snowflakes** is very centralized in Data Warehouse idea using SQL as well as open format stuffs but they are narrowing focus on only one topic  to build
SQL Data Warehouse, Data Systems completely using SQL and to do Analytics

> **Microsoft Fabric** is unified, AI-powered analytics platform includes tools like OneLake, Azure Synapse Analytics, PowerBI , Azure Data factory,
 Microsoft Fabric Pipelines which is very similar to ADF. 

</details>

<details>
  <summary> <b> PowerBI as Data Engineer</b> </summary>

<br/>

Sometime as Data Engineer, you use powerBI in order to maje report or dashboards or getting configured the databricks to PowerBI.

<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/1e338e13-ee16-404b-be4d-0a890bda933d" />
<br/>

There are 2 ways to connect your databricks to PowerBI.
1. `Import` : Import the data to PowerBI, 90% of the companies, less expensive, need refresh data
2. `Direct Query` : use for ***Big Data*** Project when your data get 4-5 GB then your powerBI start taking time to refresh and also for ***Real Stream***


Of course Data stays at Unity Catalog, and we use some kind of computing to send data to PowerBI. As a compute here usually we use ***SQL Warehouse***
- Data is in `Unity Catalog`
- `SQL Warehouse` >  start server `Serverless Starter Warehouse` > `Connection details ` | Here you can connect your server with `PowerBI, Tableau, Python`

It is important bcuz we're going to connect PowerBI to this server in order to pull the data.

<br/>
<img width="350" height="350" alt="image" src="https://github.com/user-attachments/assets/bfa48903-b34e-455a-b87f-72a6813a4020" />
<br/>
<img width="350" height="200" alt="image" src="https://github.com/user-attachments/assets/28cceeb9-129f-4218-bb33-6720b5b377e8" />
<br/>
<img width="350" height="350" alt="image" src="https://github.com/user-attachments/assets/eda4d994-9e6d-44f8-b660-715bfb08fe21" />
<br/>

This is usually a way to connect databrick to PowerBI <br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/e6ed0f10-f1b0-44ae-920c-ee3192edeb55" />

<br/>

Open PowerBI Desktop Application > `Get Data` > `More` > search for `Databricks` you get 2 instances one for `Azure databricks` paid and other one
`Databricks` free edition and copy Host name and HTTP Path of server from databricks and add it to PowerBI and `Connect` <br/>
Now you will see all the catalogs preview inside PowerBI , load the data(whichever table you want) inside powerBI and build your reports.
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/41c98087-76dc-45d9-aec0-f8a0add203e5" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/e4c31cda-4382-46c9-a4af-6556ed8687f7" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d1b8b9d5-b4ac-47ac-a069-e5ca77b1fcfd" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/1a02fff7-114e-4dc9-8d55-7b047581c7c4" />
<br/>

With this we connect our databricks to PowerBI very easily.

</details>

## 3.1 The evolution of data management (Warehouse, Lake, Lakehouse)

<details>
  <summary> Class Expand </summary>

<br/>

> **Starting Point** : Data Analyst + Excel + Business Users

Data Analyst + n excels for questions asked by Business users. <br/>
Time Consuming, Chatics, Expensive and might lead to wrong business decisions. <br/>
Still companies do it even now bcuz few departments are doing advanced stuffs using modern tools but there are a lot of departments where people are still
using Excels.
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/e9c2c32d-ab44-4012-8641-bd6ee2e5cd16" />


> **Next Stage** : ETL Developers, Data Analyst + Business Users

ETL Developers later known as Data Engineer

Data Engineers job was intially do grab the data from multiple systems and put that in something called a **Data WareHouse**

So Data Engineers start doing a process called ETL using different tools like Talend.
- **Extract** the Data from the source systems
- Start preparing the data, **Transforming** it, cleaning it up and then
- **Load** it to data warehouse

End the end to build reports from Data Warehouse or Data Analysts or BI Developers will build reports and analyzes the data on top od Data Warehouse.  

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/c286ac88-5b4e-41e5-824e-7eb49d68acc1" />

So, All what a ETL Developer/Data Engineer need is a storage like Data Warehouse could be inside SQL Server/Oracle and start saving the data inside the
Data warehouses from different sources.

Over the time those differents sources getting bigger and bigger which start causing big issue, as well as It is getting complicated. <br/>
Example one of the sources says we will not give you access to databases now onwards we become modern so we stream our data using Kafka or API

Here you as ETL Developer(Data Engineer) didn't have the enough tool to consuming(streaming) the data inside data warehouse. This is really hard, if you
have an oprem system try it you will realize it.

<img width="350" height="350" alt="image" src="https://github.com/user-attachments/assets/87e66d8e-1e68-4c61-befd-a6d7842437aa" />


So as ETL Developers, struggle with new Data sources technologies like Kafka, APIs and even data nature changes like images, json start coming
you will not able to put everything inside the data warehouse without any tool. Also in consumer now Data Scientists, Power Business Users, Business users
are started coming and aking access to the data warehouse, bcuz reports were not enough for them. 

Over the time most of the Data Warehouses become so big that you can't load it anymore. Like loading data starts taking 10-20 hrs everyday.
So Data Warehouse projects starts failing because of the sources and demands from Data Scientist as they want to build Moduling.
So Data Warehouse as classical warehouse starts failing. <br/>

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/1844b002-7aa8-4896-81e8-e642887e4409" />


There new title is introduces for ETL Developer as Big Data Developer or Data Engineer where we say Databases are really crap to build a data platform 
Around 2010, in order to fulfill those requirement, we're going to build a ***Data Lake***.



</details>


<details>
  <summary> <b> Docs Expand </b> </summary>

<br/>

> **History**

Modern data architectures did not appear all at once.
They evolved step by step as companies faced new data volumes, new use cases, and new organizational challenges. 
This page explains the journey from Data Warehouse to Data Lake, Data Lakehouse, and finally Data Mesh, focusing on what each phase solved,
what broke, and why the next evolution became necessary.

<details>
  <summary> Phase 1 : <b> Data Warehouse </b> </summary>

<br/>

**What it is?** <br/>
Centralized system with structured data and schema-on-write, built mainly for BI and reporting

**What worked well** <br/>
High data quality, consistency, trusted KPIs, strong governance


**What didn’t scale?** <br/>
Very rigid schemas, slow to change, expensive scaling, poor support for raw and semi-structured data

**What led to the next phase?** <br/>
Explosion of data volume and data types, need for cheaper storage and faster ingestion

#
</details>

<details>
  <summary> Phase 2 : <b> Data Lake </b> </summary>

<br/>

**What it is?** <br/>
Central storage for raw data in any format using schema-on-read

**What worked well** <br/>
Cheap storage, massive scalability, fast ingestion, supports logs, events, files

**What didn’t scale?** <br/>
Weak data quality, poor performance for analytics, data swamps, hard to trust results

**What led to the next phase?** <br/>
Analysts wanted reliability, engineers wanted flexibility, companies did not want two separate systems

#
</details>

<details>
  <summary> Phase 3 : <b> Data Lakehouse </b> </summary>

<br/>

**What it is?** <br/>
Lake storage combined with warehouse guarantees like ACID, schema enforcement, time travel

**What worked well** <br/>
One unified platform, supports analytics, engineering, and ML, medallion architecture, better performance

**What didn’t scale?** <br/>
Centralized ownership becomes a bottleneck, platform teams overloaded, slow domain delivery

**What led to the next phase?** <br/>
Organizations grew larger, more teams and domains, need for parallel ownership and faster delivery

#
</details>


<details>
  <summary> Phase 4 : <b> Data Mesh </b> </summary>

<br/>

**What it is?** <br/>
Decentralized, domain-oriented data architecture where data is treated as a product

**What worked well** <br/>
Scales across teams, ownership close to business, faster innovation, shared standards

**What didn’t scale?** <br/>
Requires strong culture, governance discipline, mature teams

**What led to the next phase?** <br/>
Built to solve organizational scaling, not a replacement for lakehouse but an operating model on top

#
</details>

<details>
  <summary> <b>Summary</b> </summary>

<br/>


| Phase	           | What it is	                 | What worked well             	| What didn’t scale	              | What led to the next phase  |
|------------------|-----------------------------|--------------------------------|---------------------------------|-----------------------------|
| `Data Warehouse` | Centralized system with structured data and schema-on-write, built mainly for BI and reporting |High data quality, consistency, trusted KPIs, strong governance	| Very rigid schemas, slow to change, expensive scaling, poor support for raw and semi-structured data | Explosion of data volume and data types, need for cheaper storage and faster ingestion |
| `Data Lake`	     | Central storage for raw data in any format using schema-on-read | Cheap storage, massive scalability, fast ingestion, supports logs, events, files	 | Weak data quality, poor performance for analytics, data swamps, hard to trust results| Analysts wanted reliability, engineers wanted flexibility, companies did not want two separate systems |
| `Data Lakehouse` | Lake storage combined with warehouse guarantees like ACID, schema enforcement, time travel |	One unified platform, supports analytics, engineering, and ML, medallion architecture, better performance	| Centralized ownership becomes a bottleneck, platform teams overloaded, slow domain delivery |	Organizations grew larger, more teams and domains, need for parallel ownership and faster delivery |
| `Data Mesh`	     | Decentralized, domain-oriented data architecture where data is treated as a product |	Scales across teams, ownership close to business, faster innovation, shared standards	| Requires strong culture, governance discipline, mature teams |	Built to solve organizational scaling, not a replacement for lakehouse but an operating model on top |


<img width="1743" height="737" alt="image" src="https://github.com/user-attachments/assets/ac60bc2d-3459-46ea-b252-25fb97e7ab7a" />


</details>



#
</details>
<!------------- The evolution of data management (Warehouse, Lake, Lakehouse) ------------>

## 3.2 What Data Engineering is and it evolved
<details>
  <summary> <b> Expand </b> </summary>

<br/>

> **Early days**

Data engineers started as database and ETL specialists. <br/>
Their job was mainly to move data from operational systems into data warehouses using scheduled batch jobs,
with a strong focus on SQL, schemas, and stability.

> **Big data era**

As data volume and variety exploded, data engineers moved beyond databases into distributed systems. <br/>
They began working with Hadoop, Spark, and data lakes, focusing on scalability, ingestion of raw data, and handling semi-structured data.

> **Cloud and platform era**

With cloud platforms, the role shifted again. <br/>
Data engineers became platform builders, managing pipelines, storage, compute, security, and governance using managed services like Databricks, 
cloud storage, and orchestration tools.

> **Modern data engineer**

Today, data engineers design reliable, end-to-end data systems. <br/>
They focus on data quality, observability, versioning, cost control, and enabling analytics, ML, and AI teams, not just moving data.

#
</details>
<!------------- What Data Engineering is and it evolved ------------>

## 3.3 Core Databricks concepts for Data Engineers
<details>
  <summary> <b> Expand </b> </summary>

<br/>

<details>
  <summary> <b>How to interact with Spark?</b> </summary>

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/26b75ea9-47ee-48e6-a8fd-0ca432ffd106" />

<details>
  <summary> <b> Apache Spark </b> </summary>

 
What it is? <br/>
The distributed processing engine that runs computations across a cluster

What it is NOT? <br/>
~~Not a programming language, not SQL, not a database~~

Who usually uses it <br/>
***Everyone indirectly***

#
</details>


<details>
  <summary> <b> Spark SQL </b> </summary>


What it is? <br/>
A SQL interface that lets you query data using SQL syntax on top of Spark

What it is NOT? <br/>
~~Not a separate engine, not a traditional database~~

Who usually uses it <br/>
***Data Analysts, Business Users, Engineers***

#
</details>


<details>
  <summary> <b> PySpark </b> </summary>

What it is? <br/>
A Python API to interact with Spark using DataFrames and functions

What it is NOT? <br/>
~~Not a different engine, not Python-only execution~~

Who usually uses it <br/>
***Data Engineers***

#
</details>

<details>
  <summary> <b> PySpark SQL </b> </summary>

What it is? <br/>
Using SQL queries inside PySpark code

What it is NOT? <br/>
~~Not different from Spark SQL at runtime~~

Who usually uses it <br/>
***Data Engineers***

#
</details>

#
</details>


<details>
  <summary> What is DataFrame? </summary>

<br/>

[**Databricks What are DataFrames?**](https://www.databricks.com/glossary/what-are-dataframes)

A DataFrame is an in-memory, distributed representation of your data that Spark can process in parallel across many machines. <br/>
You read data from storage into a DataFrame, apply transformations on it, and then write the result back to storage in a clean and scalable way.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/c36de115-1d85-4d02-83ed-ddc8153b6951" />


#
</details>

<details>
  <summary> <b> What is Delta Tables? </b> </summary>

<br/>

[**What is Delta Lake in Databricks? | Databricks on AWS**](https://docs.databricks.com/aws/en/delta/)


Delta Lake is a storage layer that sits on top of your data files and adds reliability, structure, and control. <br/>
It turns a folder of Parquet files into a table you can safely read, write, audit, and optimize.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/e6bb520d-9b8e-4464-b38b-b7e5817cefc9" />

<br/>

| Aspect	                 |  Normal Parquet Files	       |  Delta Table               |
|--------------------------|-------------------------------|----------------------------|
| ***Data storage***     	 |  Parquet files in a folder    |  Parquet files in a folder |
| ***Table behavior***     |	No table awareness           |	Acts like a real table    |
| ***Reads and writes***	 |  Basic, no guarantees	       |  Safe, transactional       |
| ***Updates and deletes***|	Difficult and risky	         |  Supported and reliable    |
| ***Versioning***         |	Not available	               |  Built-in                  |
| ***Audit history***      |	Not available	               |  Built-in                  |
| ***Optimization***	     |  Manual	                     |  Built-in operations       |


**Delta Table Load Modes**

| Mode	                | What it does	                                      | When to use                                                |
|-----------------------|-----------------------------------------------------|------------------------------------------------------------|
| ***Overwrite***	      | Deletes existing data and replaces it with new data |	Full reloads, rebuilding tables, development, small tables |
| ***Append***	        | Adds new rows to existing data	                    | Incremental data that never changes                        |
| ***Upsert (Merge)***  |	Updates existing rows and inserts new ones          |	Mutable data, late updates, slowly changing data           |

#
</details>

<details>
  <summary> <b> PySpark & SQL Operations </b> </summary>

<br/>

[**PySpark basics | Databricks on AWS**](https://docs.databricks.com/aws/en/pyspark/basics)


**Operation and What it does**                   

| ***Create table***   |	Create a Delta table from data |
|----------------------|---------------------------------|

SQL
```sql
CREATE TABLE silver_customers USING DELTA AS SELECT * FROM workspace.bronze.crm_cust_info
```
PySpark
```py
df = spark.table("workspace.bronze.crm_cust_info")
df.write.format("delta").saveAsTable("silver_customers")
```

| ***Read table***	   |  Read data from Delta table     |
|----------------------|---------------------------------|

SQL
```sql
SELECT * FROM silver_customers
```
PySpark
```py
df = spark.table("silver_customers")
```

| ***Append data***    |	Add new rows                   |
|----------------------|---------------------------------|

SQL
```sql
INSERT INTO silver_customers SELECT * FROM new_customers
```
PySpark
```py
df_new.write.format("delta").mode("append").saveAsTable("silver_customers")
```

| ***Overwrite data*** |	Replace table data             |
|----------------------|---------------------------------|

SQL
```sql
INSERT OVERWRITE silver_customers SELECT * FROM cleaned_customers
```
PySpark
```py
df_clean.write.format("delta").mode("overwrite").saveAsTable("silver_customers")
```


| ***Update rows***    |	Update existing records        |
|----------------------|---------------------------------|

SQL
```sql
UPDATE silver_customers SET status = 'active' WHERE last_login >= '2024-01-01'
```
PySpark
```py
from delta.tables import DeltaTable

delta_tbl = DeltaTable.forName(spark, "silver_customers")
delta_tbl.update(condition="last_login >= '2024-01-01'", set={"status": "'active'"})
```

| ***Delete rows***    |	Remove records                 |
|----------------------|---------------------------------|

SQL
```sql
DELETE FROM silver_customers WHERE is_test_user = true
```
PySpark
```py
from delta.tables import DeltaTable

delta_tbl = DeltaTable.forName(spark, "silver_customers")
delta_tbl.delete("is_test_user = true")
```


| ***Merge (upsert)*** |	Update or insert rows          |
|----------------------|---------------------------------|

SQL
```sql
MERGE INTO silver_customers t USING
updates_customers s
ON t.customer_id = s.customer_id
WHEN MATCHED THEN UPDATE SET * WHEN NOT MATCHED THEN INSERT *
```
PySpark
```py
from delta.tables import DeltaTable

delta_tbl = DeltaTable.forName(spark, "silver_customers")
df_updates = DeltaTable.forName(spark, "updates_customers")

delta_tbl.alias("t").merge(source=df_updates.alias("s"), condition="t.customer_id = s.customer_id")
            .whenMatchedUpdateAll()
            .whenNotMatchedInsertAll() .execute()

```

| ***Time travel***    |	Read old table version         |
|----------------------|---------------------------------|

SQL
```sql
SELECT * FROM silver_customers VERSION AS OF 3
```
PySpark
```py
df_old = spark.read.format("delta").option("versionAsOf", 3).table("silver_customers")
```

| ***History***        |	View table changes             |
|----------------------|---------------------------------|

SQL
```sql
DESCRIBE HISTORY silver_customers
```
PySpark
```py
spark.sql("DESCRIBE HISTORY silver_customers").show()
```

| ***Optimize***       |	Compact small files            |
|----------------------|---------------------------------|

SQL
```sql
OPTIMIZE silver_customers
```
PySpark
```py
spark.sql("OPTIMIZE silver_customers")
```


| ***Vacuum***	       |  Remove old files               |
|----------------------|---------------------------------|

SQL
```sql
VACUUM silver_customers
```
PySpark
```py
spark.sql("VACUUM silver_customers")
```

#
</details>

#
</details>
<!------------- Core Databricks concepts for Data Engineers ------------>

## 3.4 Medallion Architecture (Data Lakehouse)
<details>
  <summary> <b> Expand </b> </summary>

<br/>

This visual shows how raw data is transformed step by step into trusted, business-ready data using the Medallion Architecture. <br/>
Each layer has a clear responsibility, reducing complexity, improving data quality, and making pipelines reliable, scalable, and easy to debug.

[**What is the medallion lakehouse architecture? | Databricks on AWS**](https://docs.databricks.com/aws/en/lakehouse/medallion)

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/fe71cebe-b530-48b1-8a94-412f879ba7f5" />

Layer

<details>
  <summary> Layer 1 : <b> Bronze (Raw) </b> </summary>

<br/>

**What happens here** <br/>
Raw files are ingested exactly as received. No transformations. 1:1 copy of source data.

**Why this layer exists** <br/>
Preserve original data and ingest fast without assumptions

**What problem it solves** <br/>
Protects against data loss, allows reprocessing, decouples ingestion from logic

#
</details>

<details>
  <summary> Layer 2 : <b> Silver (Clean) </b> </summary>

<br/>

**What happens here** <br/>
Data is cleaned, standardized, typed, and validated. Still no business modeling.

**Why this layer exists** <br/>
Create reliable, reusable datasets for multiple use cases

**What problem it solves** <br/>
Removes noise, fixes quality issues, prevents duplicated cleaning logic

#
</details>


<details>
  <summary> Layer 3 : <b> Gold (Business) </b> </summary>

<br/>

**What happens here** <br/>
Business rules applied. Aggregations, flat tables, or star schemas created.

**Why this layer exists** <br/>
Deliver data ready for analytics, dashboards, reporting and AI


**What problem it solves** <br/>
Keeps business logic separate from raw data, improves performance and clarity

#
</details>


#
</details>
<!------------- Medallion Architecture (Data Lakehouse) ------------>

## 3.5 Project: Building the Bike Data Lakehouse
<details>
  <summary> <b> Expand </b> </summary>

<br/>

In this project, you will build a **complete Data Lakehouse** from scratch using **Databricks** and the **Medallion Architecture**.

You will start with raw data and step by step transform it into clean, reliable, and business-ready datasets using the **Bronze, Silver, and Gold** layers. 
This is how modern data platforms are built in real companies.

You won’t just write code. You will design architecture, improve data quality, model data for analytics, and automate everything with pipelines and jobs.

By the end, you will have a production-style Lakehouse you can confidently showcase and extend further.

Let’s build it the right way.

<details>
  <summary> <b> Project Resources </b> </summary>

Datasets as source for the lakehouse Project <br/>
**Datasets** used as the source data for building the Lakehouse project.

[**What is the medallion lakehouse architecture? | Databricks on AWS**](https://docs.databricks.com/aws/en/lakehouse/medallion) <br/>
Official explanation of the Bronze, Silver, and Gold architecture pattern.


A similar hands-on project where a full SQL data warehouse is built from scratch. <br/>
This helps you understand the same layering and cleaning concepts, but using SQL Server,
which is important for building the right data engineering mindset.

#
</details>

###  Project Phases & Guide

<details>
  <summary> <b> Phase 1 - Project Initialization </b> </summary>

<br/>

> Goal: Preparation steps before building the Lakehouse.
 
- [ ]  **Design the architecture**
    - [ ]  Read Databricks reference for the project → [**LINK**](https://docs.databricks.com/aws/en/lakehouse/medallion)
    - [ ]  Draw the data lakehouse architecture using draw.io or similar → [**LINK**](https://www.drawio.com/)
- [ ]  **Create GitHub repository** → [**LINK**](https://github.com/)
- [ ]  **Connect GitHub to Databricks using URL** (**Workspace → Create → Git Folder**)
- [ ]  **Create Lakehouse schemas (Unity Catalog) using**UI or SQL**: **`bronze` `silver` `gold`**
- [ ]  **Create a volume inside bronze schema** `raw_sources`
- [ ]  Upload the 6 CSV files from engineering folder into the Bronze volume 

<aside>

> **Result:** Project is ready to start building Bronze, Silver, and Gold layers.

</aside>

#
</details>

<details>
  <sumary> <b> Phase 2 - Building Bronze Layer </b> </sumary>

<br/>

> **Goal**: Build the Bronze layer by ingesting all raw CSV files into Delta tables without any kind of transformations.

- [ ]  Create a folder in the repository called `bronze` to store all scripts inside it
- [ ]  **Create Bronze notebook**
- [ ]  **Initial ingestion (manual)** For each of the 6 CSV files:
    - [ ]  Read the CSV into a DataFrame
    - [ ]  Write the DataFrame to a table in the Bronze schema using overwrite mode, and use a source-system prefix in the table name
           (for example `erp_` or `crm_`) to clearly identify where the data comes from.
    - [ ]  Run the script and query the bronze table to verify it is loaded correctly
- [ ]  Run the whole notebook to see if everything works successfully.
- [ ]  Commit & Push your changes to the GitHub repository

<aside>

**Bonus Advanced Task**

**Code review and Identify repeated logic**

- Create a dictionary to store file paths and table names
- Loop through the dictionary to ingest all files
</aside>

<aside>

> **Result**: All 6 raw source files are ingested into dedicated Bronze tables with no transformations applied.

</aside>

#
</details>

<details>
  <sumary> <b> Phase 3 - Building Silver Layer </b> </sumary>

<br/>

> **Goal**: It is time to clean and transform our bronze data and load the clean results into silver layer.
This is usually the most time consuming phase of the project and the fun part!

- [ ]  Create repository structure
    - [ ]  Create a folder called `silver`
    - [ ]  Create two subfolders:  `crm` `erp`
- [ ]  For each Bronze table (6 tables)
    - [ ]  Create a Silver notebook `silver_<source>_<table_name>` e.g.  `silver_crm_cust_info`
    - [ ]  Analyze data quality using SQL and List all identified issues
        - [ ]  Find duplicates
        - [ ]  Validate string values: Check extra spaces, Identify abbreviations to normalize
        - [ ]  Validate dates values: Check Data Type, check the format, handle missing values
        - [ ]  Validate numeric values
        - [ ]  Standardize business key IDs to ensure tables can be joined correctly.
        - [ ]  Check the name of columns and table and make a plan how to rename them to something friendly.
    - [ ]  Section 1: Read data Bronze Table and Load it into a DataFrame
    - [ ]  Section 2: Transform data
        - Fix issues one by one
        - Keep transformations small and clear
        - Avoid one large transformation block
        - Use Spark SQL or PySpark (Python)
        - Before going to next transformation always check the result “df.display()”
    - [ ]  Sanity checks the final DataFrame before writing
    - [ ]  Section 3: Write the DataFrame to a new Silver Table and use a friendly name for the new table
    - [ ]  Sanity checks of silver table after writing
    - [ ]  Finalize notebook
        - [ ]  Run the full notebook end to end
        - [ ]  Review structure and readability
        - [ ]  Add comments and documentation
        - [ ]  Clone the notebook as a template for the next table
    - [ ]  Commit & Push your changes to the GitHub repository

<aside>

**Bonus Advanced Task**

- Review all 6 Silver notebooks and identify repeated code
- Reduce repetition by:
    - Using a config file with loops, or
    - Creating reusable Python functions

**Result:** Cleaner, scalable code and a strong step toward senior data engineering.

</aside>

<aside>

> Result: All Bronze tables are transformed into analytics-ready Silver tables with validated data quality and standardized structure.

</aside>

#
</details>

<details>
  <summary> <b> Phase 4 - Building Gold Layer </b>  </summary>

<br/>

> **Goal**:
> - Break the data model away from the source systems and introduce a new data model that is suitable for business intelligence and analytics.
> - Use dimensional modeling to transform the Silver tables into a star schema with fact and dimension tables.

- [ ]  Data Modeling Phase
    - [ ]  Understand the content of each Silver table
    - [ ]  Map each table to a business object such as customers, products, or sales
    - [ ]  Use draw.io to design the target data model. Example: `fact_sales`, `dim_customers`, `dim_products`
- [ ]  Build Gold tables - For each table in the new model:
    - [ ]  Write an SQL query
        - [ ]  Join all relevant Silver tables for the dimension or fact
        - [ ]  Ensure no duplicates after joins
        - [ ]  Validate the query output
    - [ ]  Load the result into a DataFrame
    - [ ]  Write the DataFrame to a new Gold table using a clear naming prefix such as `dim_` for dimension tables or `fact_` for fact tables.
    - [ ]  Sanity checks of gold table after writing
- [ ]  Commit & Push your changes to the GitHub repository

<aside>

**Bonus Task - Data Product Ownership**

At this point, the data is ready for analytics and your tables represents a **data product**

You are now responsible for making it reliable, clear, and easy to use

**Enhance metadata in Unity Catalog**

- Add meaningful descriptions to Gold tables
- Add clear descriptions to all important columns
- Ensure column names and meanings are easy to understand for analysts

**Define data relationships**

- Define primary keys for dimension tables
- Define foreign keys between fact and dimension tables
</aside>

<aside>

> **Result**: All Silver tables are transformed into business-ready Gold tables designed for analytics and reporting.

</aside>

#
</details>

<details>
  <summary> <b> Phase 5 - Building the Pipeline </b> </summary>

<br/>

> Goal: Automate the end-to-end Lakehouse flow so data is processed reliably from Bronze to Silver to Gold.

### Current Setup

- 1 Bronze notebook
- 6 Silver transformation notebooks
- 3 Gold notebooks (dimensions and facts)

To run each layer cleanly, we introduce **orchestration notebooks** that act as single entry points.

---

- [ ]  **Create Orchestration Notebooks**
    - [ ]  Silver orchestration: Create one Silver orchestration notebook that triggers all 6 Silver notebooks in sequence.
           Use **`dbutils.notebook.run`** to run notebookes.
    - [ ]  Silver orchestration: Create one Gold orchestration notebook that triggers all 6 Silver notebooks in sequence.
           Use **`dbutils.notebook.run`** to run notebookes.
- [ ]  **Create a Databricks Job**
    - [ ]  Go to **Databricks → Jobs & Pipelines** then create Create a new Job
    - [ ]  Create a new Job and Give it a clear name, for example: `loading_bike_data_lakehouse`
    - [ ]  Add three Tasks:
        
        ![image.png](attachment:31475068-a648-4836-a654-8b23aa9bffe4:image.png)
        
        - [ ]  Bronze layer: bronze notebook
        - [ ]  Silver layer: silver_orchestration that triggers all other silver notebookes
        - [ ]  Gold layer: gold_orchestration that triggers all other gold notebookes
- [ ]  **Run and Validate**
    - [ ]  Click **Run All,**
    - [ ]  Monitor the job execution
    - [ ]  Ensure all tasks complete successfully
    - [ ]  Verify Bronze, Silver, and Gold tables are created correctly
- [ ]  **Schedule the Pipeline**
    - [ ]  Add a trigger to run the job on a schedule (for example daily)
    - [ ]  For the first few days: (Mointor the runes and check logs)
    - [ ]  After three days, pause or adjust the trigger as needed

#
</details>

### 🎉 Congratulations

You’ve just built a complete **Data Lakehouse**.

This is **Lakehouse 1.0** and it represents the core foundation of real data engineering work.

#
</details>

<details>
  <summary> <b> Portfolio & Career Tip </b> </summary>

<br/>

If you are **preparing for job interviews**, make sure you practice explaining this project:

- Why you designed the Lakehouse this way
- How data flows from Bronze to Silver to Gold
- How you ensured data quality and scalability
- How you automated everything with pipelines

Being able to clearly explain this project can be a **strong differentiator** and may be one of the reasons a company decides to hire you.

This is real, practical data engineering work.

#
</details>

<details>
  <summary> <b> Next Steps! </b> </summary>

<br/>

**From here, you can take your Lakehouse to the next level by adding more advanced capabilities, such as:

- **Data quality checks**
    - Row counts, null checks, duplicates, and business rules
- **Reusable code and functions**
    - Shared transformation logic, configs, and utilities
- **New data sources**
    - APIs, Kafka, streaming data, and operational databases
- **CI/CD pipelines**
    - Automated testing, deployment, and environment promotion
- **Security and governance**
    - Access control, row-level security, and data masking
- **Monitoring and observability**
    - Pipeline health, alerts, and performance tracking
- **Incremental and streaming pipelines**
    - CDC, MERGE patterns, and real-time data processing

This is exactly how real-world data platforms evolve.

Strong foundations first, then continuous improvement.**

#
</details>

<!------------- Project: Building the Bike Data Lakehouse ------------>
