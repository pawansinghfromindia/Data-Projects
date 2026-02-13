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
  <summary> Expand it for raw explanation </summary>

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

Around 2010, in order to fulfill those requirements, we're going to build a ***Data Lake***. <br/>
Now we as Data Engineer don't need database(data warehouse). Now we have a very very cheap storage and can pull whatever you wish likes from Databases sources, images, videos, JSON etc and pull and push it in one place i.e Data Lake. 

But Now Data Engineer will not do Transformations for you, Now Data Engineers are only Loading Master.
It is cheap, fast and everything and everyone need data they can grap the data from Data Lake. <br/>
Now Data Analyst, Data Scientists, Power Businedd Users and Standard Business users can access the data and Transform it and do their job.


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/b6c2e8aa-a7e8-4be1-9529-c9a29b11094a" />


But Transformation is start giving problems. Bcuz Transformation is one of the most annoying step on ETL, bcuz data is very raw, in many projects we have 
to do Data Transformations for months in order the make data very friendly for Data Analyst, BI Users and everyone that's why It involvers various steps like Data Preparations, Data Cleansing and so on. 

So Transformation is the biggest part after getting your data into one source, bcuz this data is going to used in number of projects and each project has 
to do these Transformation which is very hard, heavy lifting , expensive and annoying. 

SO, Data LAkes becomes just like a garbage where you put the data inside it. It is costly for the Transformation, It is not costly for storage, It is very cheap.

Imagine from one Data Sources, the Transformation taking 6 month and suppose there are 10 projects, so transformation is going to happens 10 times.
So If you just do EL and T is done by every project that idea got failed.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/a93665e9-dcfe-4e3a-9395-d574c3c533c9" />


So, Should we go back to Data Warehouses?
No, Data Warehouses are expensive for huge data and not suitable for all different types of data like images, videos or JSONs files and also not scalable.
Problem with Data WareHouse -> Expensive, Not Suitable for different types of data, not scalable.

So Ideas was to make some kind of **Data Lake** together inside a **Data Warehouse** and is titled as ***Data lakehouse***.
- So we still need everything to be fast, cheap storage, accepts any kind of data, but now Data Engineers have to take Transformation back which make sense. So Data Engineers will do now all **ETL**.
- Data Engineers started doing some kind of Warehousing again but on a new technology like They're going to make 3 layers and all of them are Data Lakes based on files not databases.
  1. Bronze Layer
  2. Silver Layer
  3. Gold Layer  

- So Now Data Engineers, Extract the data, load it in Data Lakes and then do Transformation in between these 3 layers.

- We can call these layers anything, Stage1, Stage2, Stage3 or presentation layers. Like in different companies their Data Architect name it differently.
  like raw -> Processing -> refined or bronze -> Silver -> gold

- So we do things step by step not everything in one place.
- With this concept we are ready to serve anything like if Data Analyst , BI Developer, or Data Scientists, Power Business users or Standard Business users

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/63fe0e6d-afa8-44a2-8b44-6d11b69e8604" />

<br/>

We spend almost 20 years in building Data Warehouse and then in 2010 we start doing Data Lake, and then Data Lakewarehouse is brand new introduced not from industry but by universities Data Science research sponsered by DataBricks they provide their platform. 

It was big idea but we have big struggle still until now. because those Transformations in between those 3 layers are still heavy for Data Engineers bcuz
Data Analyst and Business know the data very well like what they exactly need. But as a Data Engineers when we do transformations we ask them a lot of questions what to keep and what to remove from the raw data. 

Example imagine you have 20 Data Source systems, you have to understand each of them in order to make that Transformation that's why when we are about to start Transformation we bring the Data Scientists, Business Users people joining us building the LakeHouse. 

In big companies, you don't have a single point of truth for whole company at Data Lakehouse. They will not put everything at one place like Mercedes-benz or Netflix etc. That's why new concept is introduced around 2024-25 called **Data Mesh**

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/f4fe07d8-5949-46a3-9fd3-69e5965807d3" />


As company is big, so each domain now going to build their own Data Lakehouse like Domain1 Lakehouse, Domain2 Lakehouse.
A central team is building data products, buildind the gold layer but only for their domain.
Eg: If we're making Lakehouse for Car Engineering, we will not go to the sales. 

So As a Data Engineer, we're focus on only domain and build the Lakehouse and build the data product gold layer and other will do another. We never build the whole enterprizes as a whole. 

So The idea of **Data Mesh** is to build one Data Lakehouse for the whole company. That's why it is netwroking of different domain data. So we are basically building Domain driven data products. 

Databricks is exactly preparing for this to building something called **Data Mesh**. <br/>
It is domain driven data architecture to make a **data mesh** but in order to do that you need 2 things :
1. Maketplace
2. Data Catalog

So, suppose we're working as data engineer and build a very amazing gold data product for the users. Now we have to tell everyone about the new data products that we build. So in order to put our data products (gold layer) somewhere a place something called **Market Place** in the company and I need a **Data Catalog** to explain our data products.

Now supoose a data scientist will come to **marketplace**, here he/she sees about a data products from **Data catalog** read about that particular Data products in the data catalog and then goes/comes to us(data Engineers) to get the analysis about that particular data product.
That's why we need a marketplace and data catalogs. <br/>

> Databricks is moving in direction to building this. We will see whether it's going to be successful or not. But It is all about how the company make the **Data Strategy** 

Currently things look good, we're able to use Databricks as a single point platform to help in making Data Strategy but It's all about the people who are using the platform. It's always mindset that's prevail over only having tool is not enough. 

We have something called unity calalog in Databricks.

> **Unity Catalog** : This is the catalog that is available for the whole company.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/210cddfa-f18d-43cd-963f-7262e19c79e2" />

When you go to `Catalog or Unity Catalog` > inside `My oraganization` > you will see all the `Workspaces` and their `catalogs` available inside the company. 


> Steps in the development of Data Management, As a Data Engineers we have to understand those concepts to understand what you're doing not just blindly doing stuffs on old technology or even new.

This is all about Data Management and most of the companies are trying to implement this bcuz this make sense that each domain build their own data Lakehouse not only that you can mix up data warehouse in data lake.

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
  <summary> Expand it for raw explanation </summary>

<br/>

> **One Machine to Hadoop to Spark to Databricks platform**

As a Data Engineer we worked on Databases and  Data Warehouse before like 15 years ago.
We use ETL tools like [Talend renamed to Qlik](https://www.talend.com/) <br/>
You have a lot of ETL tools in the market that are trying to push their on-premises solution for those stuffs are now almost dead.

We're not using anymore ETL Tools, We're not trying to build any data lakes, Now things moving to platforms like Data Bricks, Snowflakes, Microsoft Azure Data Factory and Synapse, Fabric etc. So these platorms are enabling different tools to support those technology. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/9de6bde1-9fe0-44f0-85f4-b1e9bb414cf8" />


Let's move to the Databricks.

So, Databricks is a platform that supports Spark technology, They're the same team who developed the Spark where It was a very simple idea you can't process the data using a single Machine, It will not work as data increase. <br/>
So we need distributed machines in order to process huge data like Data Transformation, Data Agggregations and stuff like that.

Spark can splits the into multiple machines in order to work parallelly and they collect the data in the final result.

This is currently best practices on how to process massive huge amount of data.

Before Spark we have Hadoop, but issue with Hadoop was it was using HardDisk in order to store data but with Spark, It enable in-memory processing (using RAM instead of HDD) that makes it faster.
> Spark is a distributed system, using in-memory processing(RAM) to have faster speed.  

This was the massive amount of work for Data Engineers to make setups and configurations that's why we have a plaform which provides easy way to work with huge data without doing configuration and infrastructure and stuffs, just focusing on the Data Project works and platform name is **Databricks** which does everything from setting configurations and infrastructure stuffs hidding the complexity from you Databricks team preparing everything in background,  we( as Data Engineers)  just have to use it correctly and only focusing on the project on how to do ETL and how to move data.

So, If you don't want to use databricks and want to do hardcoded, of course you can use Spark and make configurations on your own(if you're expert), buy virtual machine from Azure, you can make full setup like Databricks. But imagine you have a lot of project in the company and each projects needs configurations and all those stuffs, maintainence and another things which cost a lot of time and resources. It's better to use a tool like Databricks and makes our life easier.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/78ad36d0-ba90-4ebc-805e-d0d0243f8c81" />

<br/>

> **Spark Engine**

Since, We have amazing Engine i.e **Spark Engine**, The Engine is from Spark, This is the brain, this is heart of databricks. So this is going to split the tasks into multiple machines and start managing the memory and stuffs.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f65d549d-fa47-4d34-99ee-82c9df066cf0" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/070314d9-4d08-459f-8d0b-a0e0b3e5c34f" />
<br/>
For you as Data Engineer/Analyst using databricks, you have 2 ways to giving the task to ***Spark Engine*** 

> **Spark SQL to Spark Engine**

1. You can use only SQL, not anything else (Python, PySpark). So you have engine called **`Spark SQL`**, so your SQL query will send to Spark SQL engine and Spark SQL will go to Spark Engine and do the query. <br/>
This is something Databricks teams behind the scene pushing a lot in order to have you working with SQL and to build things not only Data Analyst but also Data Engineers can do almost every stuffs using simple SQL to build your data products. <br/>
Note : But It is only for not complicated stuffs like you have only 10-20 files then It is understand to build data lakehouse using only SQL. but if you want to do something professional and complex we have another way
<br/>

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/5c8bb0a8-4dd8-456f-ba07-5fb4659a27cf" />

<br/>

> **PySpark to Spark Engine**

2. Professional ways like you have complex logic where you're dealing with multiple scenarios like you have Kafka, Streaming stuffs from multiple data sources, there only SQL is not enough, SQL code will be huge for the stuffs that's why we need Python. To work to Spark using Python we have something called PySpark. <br/>
We can use python in order to build our data project. To work with Spark using Python, Python provide a library called **`PySpark`**  <br/>
We have to install it, which is already installed in Databricks.

```py
pip install pyspark   
```
```py
pip install pyspark[sql,pandas_on_spark,connect]

# This is to include optional components like SQL, pandas API on Spark, or Spark Connect,
```
```py
import pyspark

print(pyspark.__version__)   
```

So, We can use PySpark in order to work with big data using Python in Spark technology.
- PySpark looks very very similar to SQL like in SQL you do `Create, drop, Select, JOIN, Merge, Update,Insert,Update, Delete, truncate, filtering, aggregations etc` everything what we can do in SQL we can do more than that in PySpark.
- So you will find yourself that you're doing almost same thing SQL but in a new language called PySpark.
- Now whatever you write in PySpark It is going to use same Engine Spark Engine in order to process your Queries.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f916b357-07b0-41b6-97df-a38858ebfb26" />
<br/>

> **Spark SQL vs PySpark**

Generally Junior Developers thinks that they're using SQL (SparkSQL) that's why slow performance buz not using PySpark. That's not true. At the end It doesn't matter whether you're using Spark SQL or PySpark both of Queries goes to Spark Engine behind the at the end. 

Not only that we can put SQL statements into PySpark as well and it is called **PySpark SQL**

So we have 3 different options :
1. Either Write only `SQL`, It is known as ***Spark SQL***
2. Or you can write only `Python`, It is known as ***PySpark***
3. Or you can write `Python` + `SQL`, It is known as ***PySpark SQL***

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/bbb95f33-62a0-4f8b-9acb-54d310b708e3" />

<br/>

we have to learn multiple concepts like Spark, Spark SQL, PySpark, PySpark SQL and databricks tools as well.

So now we know : What is `Spark SQL`?, What is `PySpark`? and What is `PySpark SQL`? 
- They're different ways to write code in order to communicate with ** Spark Engine**


Let's jump to Databricks :

As Data Engineer, the most important thing in Databricks you work with is `workspace`. You can connect here GitHub or create notebooks and many other things.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/f6b68619-ccad-4a5b-88c8-4be9f8a26e70" />

In companies, as Data Engineers the thing we're going to use is **Notebooks**

You can rename the notebooks, put it inside the folders and arrange it, save it and use it in pipeline in order to automate the thing, you can schedule it and many more things like history of notebooks, changes made in notebooks, there are a lot of features which makes your life easier. 

Inside Notebooks you can write SQL using `%sql`, Pythons using `%python` or any other languaages like markdown using `%md` for comments or documentations explaining the datails about the Notebooks and each query what it is doing?

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/8dee05d6-0cf8-4d4a-9bd6-b6a2fd830893" />

<br/>

Simple SQL(Spark SQL), It goes to Spark SQL Engine for processing.
```sql
%sql

SELECT * FROM workspace.salesDb.dim_customers;
```
PySpark Code, It also goes to Spark Engine for processing
```python
%python

import pyspark.sql import functions as F

df = spark.table("workspace.salesDB.dim_customers");
df.display()
```
PySpark SQL, It also goes to Spark SQL Engine for processing.
```python
%python
# Create a SparkSession (if not already created)
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("SelectFromTable").getOrCreate()
# not required in databricks already there

df = spark.sql("""SELECT * FROM workspace.salesDb.dim_customers""");
df.show();
df.display();
print(df);
```
All of these 3 ways are same, give exactly same performances bcuz all of them goes to Spark Engine behind the scene at the end

We will have projects in companies where we can do everything in SQL.
15 years ago, It was dream to work with distributed system using SQL that's possible bcuz we have Spark Engine which supports SQL/Python.


> **Dataframe Concept**
> - A DataFrame stores data in a tabular format where each column can hold different data types (e.g., numbers, text, dates), and each row represents a record.
> - The structure is highly flexible and widely used in data science and analytics.

Dataframe is something, you're going to here a lot if you use spark, Pyspark, Spark SQL. <br/>
It is main thing that we use to do anything.

So Dataframe concept is very important to understand. and It is very simple.

All what we have to do as Data Engineer is we have source tables. <br/>
We want to take data from the source and move it to the target. <br/>
On the way as we're moving the data from Source to Target, we want to do data transformations.(Transform, Aggregate, Clean, Prepare the data for business).


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/4fb8983f-b4ba-4167-a876-d1e0ef9cf770" />
<br/>

So, The concept of dataframe is in Spark, Pandas, R, Python, Snowflake(Snowpark) and others. It is not only limited to Spark

So, First **read the data from the source**, put in in something called ***Dataframe***. Dataframe it is first in the memory and anything which we do to this dataframe It is going to process always parallelly.

So, If we're using Spark It will go to Spark Engine. Pandas doesn't have parallel processing.

So basically Dataframe is ready to be distributed on multiple machines.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f95cef16-23f8-49e7-a8fb-351f921fb2f3" />
<br/>

If we data transformation, suppose GROUP BY or TRIM or UPPER  etc whatever you do as data transformation it always like you're doing it on dataframe.
Dataframe is going to splitted into small data distributed on multiple machines and processed for different functions like Group BY, TRIM, UPPER etc and then returns back to the dataframe and become as a whole unit and your data is transformed.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/77392aa6-8daa-428d-987b-d0c7ebad767c" />
<br/>

So Dataframe is that something which is temporary. It is live as long as we have session open bcus here we're using in-memory processing(RAM).
So, We take the a copy of the data from dataframe and do whatever we want to do and a the end if we want to save the result of transform data we create tables/views from the dataframe. 

We usually don't immediately do transformations directly on the source of data. We always take copy this is the main thing to do. Here in PySpark we use dataframe. We do manipulation on it nad write it somewhere else. 

This is actual concept of what data engineers do in a company. Whatever we do whether loading the data in bronze layer or silver layer, It's always we have to think about those 3 steps of (1. from where I read the data, put it in dataframe, do something about it like transform it or not and then write it back in a table. 

Of course, on dataframe we can use SQL Spark or PySpak. SQL you must know about CTE, SubQueries etc where database Engine create temporary storage of your data in order to reuse multiple times.

<br/>

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/79278439-8462-4312-984b-ab230480f1a8" />

<br/>

So far we have learned, How to work with Spark? Main thing about spark like How we load data inside a dataframe and stuffs. It is important to understand those concepts otherwise you don't know why you're creating a dataframe.

When you work with Databricks tool your source might be delta tables but once you load the data into one layer to another layer you always load it in delta table. So we always use delta tables inside databricks, we never use csv file to be written at the end.

> We use a very advanced file format called delta files or delta tables.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/1c969e46-0d21-4520-8e71-a0624f9714a3" />


Why we have files delta files/tables, why don't we have like databases tables? <br/>
There is a big difference, you can see a lot of SQL Developers, they build warehouses, they load the data inside tables inside SQL Servers or PostGres or others. But as a Data Engineer we stop doing that since we're working in Data Lake, In Data Lake we always store the data as files, there is no more normal table like what we have in SQL Server Data Warehouses. Even with Data Lakehouse We store data files in the end. 
- Of course files has different format and stuffs.
- File format for databricks is an open format called Delta Table or Delta file.
- So if you say, I'm developing a data lakehouse inside the databricks actually you're working with files and you have to have some basic understanding on how to work on the file(Delta file, a open format file) 

**What is delta table?** or Delta file or Delta table.
There are 2 types of file :
1. **Close Format** like the one that is stored behind the scene in Databases, they can be only used for databases engine nowhere else. 
2. **Open Format** It is something we can use it whereever we want. Like we can take a file and use it for AI or for Analytics or for BI whatever you need for. But Closed file inside the databases they can be only used for databases engine nowhere else.

This File concept is developed from Spark Team. They said and wanted everyone to work only with Open File format, as we're using the files across the field not only limited to databases. 

One of the amazing Open file format that we can use is Parquet file. 

Parquet files are amazing for historization, where we can get history of file from the day we created to uptil the we're going to drop. 

We as Data Engineers have always to main the history of data, always have possibility to travel back to the data see the history. If you read the documentation Warehousing, this was the main idea of building a data  warehouse is that I need store data as well as history of data. And Parquet file is an amazing technique or file format to do that.   

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/89801153-8a90-40c5-9717-dd1efed11bcd" />


Initially in databricks, there were no delta tables, there were only Parquet files.

If you start working with files, you feel, they're not really safe to use if you do inserting new data, updating the files etc etc, the files can get easily corrupted, It is nighmare to work with files bcuz it's very hard to manage it, maintain it. It is very risky. That'w why databricks add a new techniques on top of those open files to make it easier to be used as well as manage and maintain safely in order to do operation on top of files.
So that we as Data Engineers not suffer anymore with `Parquet files` we will work with more advancef file format `delta files` which makes our life easy and safe than working with those parquet files. 

We can use PySpark to do operations like create, read, write, overwrite, append, travel history, optimization etc etcon these delta files very easily.
Bcuz they not only use not delta tables inside parquet but also they have logs and metadata in order to maintain history and getting info inside the Delta files.

<br/>
<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/d5a7c393-f749-4643-bb2a-1e077cab7a7a" />
<br/>

Everything that we see in catalogs, all are delta files or delta tables. (Behind the scenes parquet files and logs files and metadata files behind the scene)

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/e5898b58-3ef9-4900-ba8f-6341740596ab" />

<br/>

```sql
%sql
DESCRIBE HISTORY workspace.salesDB.dim_customers;
```
This operation you can never able to do on normal databaseS like SQL Server, PostGres, MySQL. It is something that we can only do on delta files/tables 

So, basically each interaction we're doing on a table Spark create a history of it. And with time we can check the history it's known as ***Time travel***
```sql
%sql

SELECT * FROM workspace.salesDB.dim_customers VERSION AS OF 1
```
```sql
%sql

RESTORE TABLE workspace.salesDB.dim_customers TO VERSION AS OF 1
```

So, the more numbers of operations on delta table, the more numbers of log files will be there in delta file and with time things go slow bcuz databricks manage all of those file and for this companies has to pay for its storage and operations stuufs. So as Data Engineer we have to work with these files and pay attentions on these files and do optimization to boost the speed on interval basis 

So, you can see with Spark, How SQL as language as a way to interact with Data is an important skills. 

#
</details>

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

There are 3 ways to insert the data in Spark :
1. `Overwrite` : Delete the previous data and load it with the new one
2. `Append` : Keep the previous data as it is, insert the new data below that. Happens only on sensors kind of stuffs that never changes event base.
3. `Merge` : check if the old data if it match with the new one update it with new one if not match keep as it is, known as `Upsert`

Merge is increamental load, update first and then insert. <br/>
So Merge is nothing but Update + Insert.

Append is event based least used, only stuffs like sensor so something.

Generally we use Overwrite and Merge(Upsert).

For small data sources, go with overwrite. Merge/Upsert is risky becuz If you had a bad days, you didn't load the data correctly if you have small source system and you can overwrite. But if you have a big sources system, Overwrite takes long time that's why we have to do Merge/Upsert and for this we have to dependent on primary keys and stuffs like that.

So Merge/Upsert improve the performance, where it check first to update if data exists if not exists then insert. So only few rows is going to be changed.

But anyway we don't have to worry about the source system bcuz you're going to get history of delta tables bcuz delta files already saving the parquet files with the log and metadata files. 

So if something went wrong with data we get the data back from history and do the operation again. This happens a lot in company projects.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/5fe190d1-7377-4a86-95b5-68a0aabb3ee0" />
<br/>


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

## How Data Lakehouse is built in a company from scratch

<details>
  <summary> <b> Design, Code and Implementation </b> </summary>

There is no one book or one way on how to build a Data Lakehouse. So, there is no standards, It depends on scenario and depends on situation and depends sources on the company itself, depends on data architect. 

In the project, the first step as a Data Architect what you do is :

**Step 1 :  Design a Data Lakehouse for your data Project** <br/>
Make a diagram on how to design a data project. 
You can't immediately jump and start scripting. 
Have a design and then last thing is scripting otherwise It'll become messy.

For Lakehouse we usually design 3 layers :
1. Bronze layer (raw)
2. Silver Layer (processing)
3. Gold Layer (refined)

`Bronze Layer` : <br/>
When you're building Data Lakehouse, you need always a place where you put raw data as it is. <br/>
It is very important to not do any transformation immediately. <br/>
So just **Extract and Load**, So It's usually 1:1 copy of data **No Transformation** in Bronze Layer.

Why so? 
- of course this is a standard way. The reason to store it without any transformation is if something goes wrong in your Silver Layer or Gold Layer, instead of relying on sources of data, you can rely on your own Bronze Layer without worrying about data sources avaliability bcuz there might be possibilities that sources data is deleted/changed/modified in order to optimize their system and also that is manage by another team, you will have to raise the request for the data and so on. Imagine they deleted the data and don't have archive for it. 

- You can't reverse the transformation on that huge source data so easily. So, It better to keep the raw data as it so that if any audit will have to happen team can easily do that. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/a576a14e-4e6c-40fa-a208-2cdb1f2951db" />

So basically you defined the rule. 


Next step is to clean up the data. We can't keep data as it is.

We don't do transformations all at once. We do it step-wise.

**Tranformation** is of 2 types :
1. Transformation that we do in order **to  Clean up the data**
- e.g : trim for white spaces, changing the case of data types, replacing the nulls with new values 

2. Transformation that we do in order **to apply Business Rules**
- It is something that comes from business, where they if if customer having more than 100 orders then this customer is VIP. So those rules comes from the business, company. And Each company has its own business rules. 

Since, We have 2 types of **Transformations**, we will not put everything in one place. <br/>
So, we always try to split, the more we split, the more it is easier to manage. But of course you have to have a balance.  <br/>
You can't have n numbers of layers. This is crazy that's not what a good Data Architect does. So Maximum 3 layers and it is standard Medallian Architecture Model. 

`Silver Layer` : <br/>
So in the Silver layer we do transformation only related to Data Cleansing. <br/>
Like Clean Data, Standard data type changes, Replace Nulls, Trim spaces etc. <br/>
So define the rules for it. 

So We didn't allow to do Data Moduling in Silver Layer. The reason is we want to maintain the shape of data like the source system bcuz many times the Data Scientists or Data Analysts come and want to see and analyze the source data, they want not to break the model structure or add something new.  

So the bigger the project the more people come and want to see the original data like it is from sources but in clean way that's we made another rule that there is no data modelling in Silver Layer.


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f8290b11-c94d-4cff-b3c1-890a8c518b60" />

<br/>

In the next step, in Gold Layer, which is a business layer, here you're allowed to apply those business rules.

Here in Gold Layer you're allow to change the shape of data, you can do data modelling and break the old one and creat new one. <br/>
Introduce star schema, Aggregations do whatever is required, prepare the data as final user can use it.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/3f962643-a384-49bc-8c76-03e9022384d8" />


<br/>

You can give the access point for your Data Lakehouse is Silver and Gold. 

There are many use cases of it. As a Data Engineer, you're not a data owner but you're advisor for data bcuz Data Owner are usually from the business. So As Data Engineer you're the **Data Product Owner**. So, if someone come and ask you for the data, you always try to push the gold product bcuz the're really prepared and ready. But if things didn't work for them they want something else then only you can allow or serve them the silver layer. 

Now you have defined your rules what you're going to do what is allowed and what is not allowed, where to do what. You have already done your 50% job done. Usually this is done by Data Engineers, Senior Data Engineers or Data Architects. Data Architects mostly involved in designing and guiding the developers. By the way when you joined the project which is already in progress always ask about rules each layer. 

**Step 2 :   How to build(implement) this idea of Data Lakehouse that we designed in real Project?** <br/>

So, Now we're going to code(scripts). <br/>
We will write script in `PySpark` or `Spark SQL` or `PySpark SQL` either of them for each layer Bronze, Silver and Gold seperately.

We write the scripts(codes) in Notebooks by using the Dataframe as we're using here Spark Technology for Distributed System and Parallel Processing. 

In the Scripting, we're going to build storage, so we have to create storage folders seperately for each layer bronze, silver and gold.
Usually we put everything in Unity Catalog. 

What first notebooks scripts of Bronze Layer is going to do is read data from the source, create dataframes, do extraction and loading and write it to storage.  

The next Notebooks scripts of Silver layer is going to do is read the data from Bronze layer, create dataframes, do transformation(Clean up) and write it to storage.

Similarly the last Notebooks scripts of Gold layer is going to read the data from Silver layers, create dataframes, do transformation(Business) and write to storage.

That's it! This is what we have to do as Data Engineer. 

Once data lands in the final layer i.e. Gold Layer that is the final Data Product. Now you can go and say to Data Scientists, Data Analyst, Standard Business Users and Power Users, Hey Data is ready now you can go and consume it.

Now of course, this is not a single time process, we do have to repeat it once we have new data, either it can be daily or weekly or monthly.
So we can't run it manually everytime. That's not the professional way. So we have to automate it.

In order to automate, we will build a data pipeline. This is something we also have to do in order to make an Orchestration, Orchestration means put everything in one place and if we want to run it just by one click, it will run and execute ech commands/scripts. So Data Pipeline is going to trigger the Bronze Notebooks and their command sequentially and then Silver one and at the end Gold one.  

Now you can schedule your pipeline in the night shift to load the data.

That's all fundametals of what a Data Engineer do?

Now you job is to learn how to write script, how to build data pipeline.  

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/b0aaad16-87e5-4c27-839e-113e556d93aa" />

 #
</details>


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
