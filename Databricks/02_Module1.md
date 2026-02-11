# Module 1 : Introduction to Databricks 
- From One Machine to Databricks
- Problem, Why and What is Databricks
- Databricks in Real Company Workflows
- Tour Into the Databricks Interface
- Getting Data Into Databricks
- Assignments

## 1.1 From One Machine to Databricks 

<details>
  <summary> Expand </summary>


Q : Why we have databricks?

Q : Ideas behind the whole databricks thing

> As a Data Analyst/Data Engineer you need to do data processing like query data, aggregations, data transformations etc. 

<details>
  <summary> <b> Era 1: Single Machine Computing </b> </summary>

<br/>

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/8b5ae2a7-914c-49aa-bba3-94d1c7893712" />

**Before ~2008, What is was** like  At the start we had only one machine/server/compute and All data processing happened on one computer/server/machine.

**Why it worked** is bcuz - Data was small - One CPU and one disk were enough.


`Data increase -> Database size increase -> Processing Machine(Server) increase` 

Companies started buying bigger processing machines(servers/computes), but at the end those server are not enough bcuz data starts increasing exponentially. <br/>
One big machines might break and takes a lot of time and this concepts are not working as we scaling up our data.

**What broke** was - Data did not fit on disk or memory - Processing took too long - One crash stopped everything

> **Problem: You cannot scale forever by buying a bigger machine.**

**What we needed next** was - A way to **split data and computation across many machines**.

</details>

<details>
  <summary> <b> Era 2: Hadoop </b> </summary>

<br/>

So in 2005-06, ~20 years ago, another concept another ideas came **Hadoop** to handle **big data**

**What Hadoop solved** was :
- Distributed storage with HDFS
- Distributed batch processing with MapReduce

**Why it mattered** was
- Data could be stored across many machines
- Hardware failures became normal, not fatal
- Very large datasets became manageable

Split the compute(machines/servers) into multiple nodes(machines) and splitted our data onto those different machines. 
Now if one of those machines fails that totally okay bcuz now we have other machines at the same time speed up processing faster.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/650c91ca-7f9b-4e71-a925-aa32603031ed" />

So, Data Engineers start doing ***big data processing*** using the first idea of how to handle big data i.e. using ***Hadoop***


But there we **one big issue with Hadoop** which is very annoying that **data is going to be stored inside hard-disk**, so processing is still **slow** 
bcuz each of those small servers have to interact(read/write) on HardDisk and this takes time.

So, the biggest drawback of hadoop was Data is stored inside our HardDisk which makes processing very slow even though we had multiple computes.



**Limitations** of Hadoop was :
- Heavy disk usage
- Slow batch jobs
- Complex development and debugging

> **Hadoop solved scale, but not speed or simplicity.**
 

**What we needed next** was Faster distributed processing.


</details>

<details>
  <summary> <b> Era 3: Spark </b> and <code>PySpark</code> </summary>

<br/>

So to resolve the drawback of hadoop, Reseachers/developers in 2009-10 bring the **Spark** into picture and the idea was very same like Haddop we have multiple 
servers but **What changed** was Spark introduced ***in-memory processing*** instead of constant disk writes, which made distributed data processing much faster.

This is the best concept of processing the big data even today.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/ed8d1c64-15c2-45da-8b5b-2782e264e268" />

Of course, here the next problem is how do we're going to program or code this? <br/>
At that time `Python` was best thing, so developers of Sparks decided to put the whole commands into **`Python`** and people can use the their library **`PySpark`**
in order to build the setup. That's makes easy for data engineers to they can work with `Python` and build this whole thing. 
So far only Data Engineers(IT People, experts) were working with the concept of Spark for big data processing not Data Analysts

So Data Engineers starts using `Pyspark` to use the concept of Spark in order to process big data. Now we can process huge massive amount of data using 
the Server memory(in-memory processing).

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/750458a5-8ea3-4e10-9d27-585801e5fcea" />

For Spark, we have a python library i.e. known as `PySpark`. This made Spark accessible to: - data engineers, - data analysts and - Python-first teams

> **DataFrames** became the standard way to work with big data.

This unlocked other things like :
- interactive analytics
- iterative workloads like machine learning
- one engine for SQL, batch, streaming, and ML

But still this is huge problem and pain because we have to configure a lot of things to work with Spark using `PySpark` like 
- Configure the Storage i.e. Database like preparing the blob storage
- Configure Nodes i.e. Computes/Server/Machines
So we have to do a lot of things in order to use Spark concepts in reality than just having in theory.

Data Engineers feel exhausted in just doing configurations. (infrastructure setup)


</details>

<details>
  <summary> <b>  Era 4: Databricks </b> </summary>

<br/>

So, Data Engineers feel exhausted in just doing configurations that's when the **Databricks** tool came to help us configuring those stuffs.

In 2013+, Same reseachers and developers team came with an idea of building a platform and started it as databricks company. <br/>
They're came up with solution like as a company, databricks team handles the whole complexity of this setup of Spark (like configuring the storage, configuring 
the nodes. 

> **What Databricks is** A managed data platform built around Spark.

**What Databricks solved** was :
- Easy cluster management and autoscaling
- Collaboration with notebooks and SQL
- Reliable data with Delta Lake
- Jobs, scheduling, monitoring, and data governance

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/a8204eba-e19e-430a-af1b-3140c8b9162f" />

Now Data Engineers don't have to deal with infrastructure(configuration setups), they just focus on their projects (data, data processing).
In a few click data engineers can build configuration like creating clusters etc. That was the main idea behind the databricks.

Since then for **Data Engineers** are now solely focus on their projects more
Now it is not only limited to specialist or experts like Data Engineers but also **Data Analysts** can start working on this data platform Databricks.
Even **Business users** who want to work with their, they can also use this data plaform databricks using AI


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/7d9808c4-46d0-4707-ae4f-875955a8bed1" />


> So the idea of databricks comes from data processing on normal single machines, big data processing through Hadoop, big data processing through Spark using PySpark to
big data processing through Spark using Pyspark on a data platform Databricks which handles the infrastructure(configurations).

**Big shift** From fragile data lakes to a reliable **lakehouse platform**

> **Databricks is not a new engine. It is the system that makes Spark usable in real companies.**


</details>

> This was the history of databricks. This is the main ideas of why do we have databricks!

<details>
  <summary> Why Data Engineers and Data Analysts learn <b>Databricks</b>? </summary>

<br/>

Databricks Benefits :
- For Data Engineers, Databricks makes their life easier instead of wasting the time in configuring the infrastructure, focus on projects
- For Data Analysts, Databricks provides a simple and easy way to work with big data.

</details>

<!-----------------From One Machine to Databricks ----------------->
</details>

## 1.2 Problem, Why and What is Databricks

<details>
  <summary> Expand </summary>

Q : Why Companies interested in Databricks?

<details>
  <summary> <b> What are the Industry Problems and How Databricks Tries to Solve Them </b> </summary>

<br/>

From company perspective why companies are interested in Databricks. <br/>
In the big companies they don't have one big central team that is handling the data. <br/>
Companies don't have one central platform to like okay this is the place for single point of truth. <br/>

Companies had different teams building different projects. There are n numbers of projects in which they're doing something with data. <br/>
e.g. : AI Data Projects, Dashboard and standard Reports Projects etc

Companies have different Departments, Based on that Projects and based on that teams. <br/>
So, If you start building a project, first you have to decide **tools** based on the requirements of the project 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/5545f666-2a18-449b-bd6b-83539b158534" />


`For Storage : Database`
- Project 1, team decides to use **Oracle** database
- Project 2, Another team decides that let's use **PostgreSQL**
- Project 2, Another team decides that let's use **SQLite**
- Other team let's build a Data WareHouse using **SQL Server**

`For Processing Data : How to process the data (Pipelines) as ETL Tool`
- Microsoft **Azure Data Factory** integrates seamlessly with Microsoft services like Power BI and Azure Synapse, offering cloud-native scalability.
- **AWS Glue** offers serverless, cloud-native ETL/ELT with seamless integration into the Amazon ecosystem.
- **Talend** provides strong data governance, AI integration, and hybrid cloud support, with real-time and batch capabilities
- **Informatica** Informatica is a leading enterprise data integration platform built on a batch-first ETL (Extract, Transform, Load) architecture,. 
- **Apache Nifi** excels in real-time data flow automation, ideal for IoT, event-driven architectures, and high-throughput streaming.

`For Data Visualization : How to visualize/dashboard/reports Visualization Tool` <br/>
There were n numbers of tools that're used before PowerBI and Tableau but somehow they reduce those tools to 2 but it's debatable who is better between them.
- **PowerBI**
- **Tableau**

Not only Storage are different, tools(processing, visualization) are different but Policies are also different :
- If a team can has access to all data or not bcuz of no concern for Data Security
- Another team can't have whole data access, they can have access to few data(tables/rows)
- So, to handle this each project has to define different policies in order to how to access data.

These were nightmare bcuz it depends on human that're running the project, how you understand the security. <br/>
That's why we have different technology, different policies.

As a manager of a company in the data projects and want to do data governance It was impossible to manage all those stuffs.

That's why Databricks as a platform helps companies by providing their tools.
Like don't need different tools and stuffs, just build one data layer **Delta Lake** put everything that you have in the company in this layer. <br/>
After that define the policies using something called **Unity Catalog**

Example if customers data goes only for this department then you define the policies only once and then bring everyone from the company and they start doing 
their use cases (PowerBI, Machine Learning, ).  <br/>
So Data Engineers build this Unity Catalogs and now Data Analysts, Business Users.

Anything about the data, It is going to be on top of these 2 layers Data Layer(Delta Lake) and Unity Catalog

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/e2def11c-f4c8-4d5c-a048-83d3f298fc05" />


If you're not a good Data Engineers then still you can make weird thing inside Data layer or policies stuffs. So It's not always about the tools, It slso about the Mindset.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/444eb201-7fd1-4399-ad15-c56117310c6d" />


#
</details>

<details>
  <summary> <b> What Databricks Is (High-Level) </b>  </summary>


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/5fd3a980-f40c-4f4b-8fc4-a02bac6eb8a0" />

Databricks is a **unified analytics platform** used to build, run, and maintain data, analytics, and AI solutions at scale.

It integrates directly with your **cloud storage and security**, and it manages the underlying infrastructure for you. 
This means teams can focus on working with data instead of managing systems.

#
</details>

<details>
  <summary> <b> Databricks Components </b>(Conceptual View)  </summary>


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d3c9cfdd-b763-4f74-93a5-b28299c7df46" />

> **One data foundation, one governance layer, many workloads, no fragmentation.**


| Layer in the diagram	| 	            What it means                    | Why it exists                                                |
|-----------------------|------------------------------------------------|--------------------------------------------------------------|
|**`Open Data Lake`** : | Your cloud storage where all data lives	| Keeps data open, portable, and owned by the company |
|**`Unified Data`** : |	One shared set of tables on top of the data lake	| Eliminates multiple copies and creates a single source of truth |
|**`Unified Governance`** :|	Central security, access control, and lineage	| Solves siloed security and inconsistent access rules |
|**`Data Intelligence Engine`** : |	The compute and intelligence layer	| Runs queries, pipelines, ML, and AI on the same data |
|**`Data Warehousing`**	: | SQL analytics and reporting workloads	| Allows warehouse-style analytics without moving data |
|**`Business Intelligence`** : |	Dashboards and reporting	| Lets business users consume trusted data |
|**`AI and Data Science`** : |	Machine learning and AI workloads	| Brings models and AI close to the data |
|**`ETL and Real-Time Analytics`**	: | Batch and streaming data processing	| Handles ingestion, transformations, and real-time use cases |
|**`Orchestration`** :	| Scheduling and workflow management |	Turns data work into automated, reliable pipelines |


[**What is Databricks? | Databricks on AWS**](https://docs.databricks.com/aws/en/introduction)


#
</details>

<!---------------Problem, Why and What is Databricks------------------->
</details>
 
## 1.3 Databricks in Real Company Workflows

<details>
  <summary> Expand </summary>

<details>
  <summary> <b> The real story in companies </b> </summary>

<br/>

> **"Databricks is not used by one team. It is used by many teams, in a specific order."**


<details>
  <summary> <b> Data Sources </b> </summary>

We uses different data sources tools as Data Sources but now a lot sources are providing data in Kafka bcuz this makes life easier for everyone for that they produces and for us as a consumer. Some companies are pushing to using **Kafka**.

So, ***Kafka*** is one important tool that we have to learn as data engineer.

Also your data could be on File Servers like ***FTP*** or ***SFTP***

It could be on ***Internet Server*** (https://) or may be you could get id from ***API*** (DD-API)

<img width="253" height="502" alt="image" src="https://github.com/user-attachments/assets/bace5fb6-5c48-431b-9fdb-726e5160c009" />


</details>

<details>
  <summary> Consumers/Use cases</summary>

We as Data Engineers gets empty Databricks and we need to build a data product.

Databricks gives us a reference on how to build a system something called ***Data Lakehouse***

So as a data engineers we're going to make 3 Layers : `Bronze`, `Silver` and `Gold` It is called as ***Madellian Architecture***

Why we have 3 layers, It's bcuz It is seperation of concerns, It is easier for us to manage 3 different purpose than putting everything in one place.

We will build ***Pipeline*** to load the data in those layers.

Of course, we(Policies Experts) will be configuring the ***Unity Catalogs***

And also we're going to build ***Data Lakehouse***


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/218829f4-ed9c-4708-acd3-ed206343a2eb" />


This is what our job is and this is what we do as a Data Engineers. <br/>
This is not easy, it's very hard to do bcuz it involves a lot of **data processing**, **data transformation**, **understanding of how to module data** and stuffs
like that. This is the world of a data engineer. <br/>
We can do the whole thing ***Pipelining, automations, definition of Policies*** everything in just only one tool i.e. ***databricks***. You don't need storage, you don't need
get databases like Oracle etc etc. <br/>

Before Databricks, we had to use 6-7 tools in order to do all those stuffs but with databricks we can do everything in one place.

Everything ends for us as Data Engineers as we build the final layer i.e `Gold Layer`. So basically `Gold Layer` is final product. We have data ready, everything is
prepared and now we something called a **Data Product**. Now everyone can use it for Analytics etc.

Now comes ***Use Cases***, Here a lot people are interested in your data, you're going to have ***Standard Users***, ***Data Analysts***, ***Data Scientists***, 
***PowerBI Users***. <br/>
They have a lot of options on how to do this.

One easy and standard way is just use a new tool(not databricks tool) build a standard report using ***PowerBI***. So start consuming the data from gold layer and 
start building a standard dashboard and offer it our users.

Now those **Standard users** consume the PowerBI reports just by clicking.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/118a2171-a355-45c1-a5ea-daedea98e978" />

Of course, this is not the only thing we can do with data. <br/>
As a Data Analyst, we have to do ***Data Exploration***, of course we can do that using PowerBI but generally data exploration you do for yourself to understand the
context, what is inside the Data Lakehouse bcuz you can't directly build dashboard without understanding the content. So as a Data Analyst last thing we do is building dashboard and reports using PowerBI before that we have to do a lot of explorations and investigations and we do this using databricks.

There are many options like we can do using either ***Databricks Notebooks*** in case if we want to work using `SQL` or `Python` or
you can just use `SQL` using ***SQL Editor*** as well.

Sometimes the standard users don't really want the PowerBI, They want to see and play around the data in data lakehouse. So some of those Standard Users is going to be ***Power Users*** (users that has SQL Skills) they want to explore the data bcuz reports are not making enough sense to them.

So even the Business Users those who have SQL skills, they can start exploring the big data in Data Lakehouse. 

We can also build the ***dashboard in Databricks*** but it is different than the PowerBI dashboard. It is not the final product of your dashboard it for us if everything make sense and everyone is agree here in databricks dashboard then only build the PowerBI Dashboard.

***Data Scientists*** can do ***Machine Learning*** by using the same final data by feeding this to their models.

Now since AI diiferent Code Models came into market, now even Standard Business users can interact with data lakehouse like the Gold Layer final data not using `SQL`  not using `PowerBI Dashboard` but using the LLM (ChatGPT) by prompting not works in all use cases still in progress.

</details>

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/8e281b17-492c-4123-861d-a04408e78fc3" />

If we look at Databricks as a big picture, This is something like we didn't dream of bcuz working on big data projects like this in databricks is only for experts.
It requires heavy scripting, know how to configure clusters and stuffs. So even Data Analyst can't interact with all components of databricks. Maximum what Data Engineers can do to Data Analyst is provide you an extra database in order to work with PowerBI.

So whole Data Lakehouse is only for Data Engineers. Noone can access these. They build it different products and share it using SQL and databases.

But now we don't do it anymore bcuz we offers the data for multiple usecases and now everyone is able to interact with such a platform where you have multi proessing and scalable systems.

That's why Database is used very widely and getting a lot of attention.

#
</details>


<details>
  <summary> 1. Data engineers <b>build the Lakehouse foundation</b> </summary>

<br/>

Everything starts with ***data engineers***. Their job is to **build the data lakehouse**.

They ingest data from : | ***operational databases*** | ***SaaS tools*** | ***logs and events*** | ***files and streams***

All data lands in cloud storage and is stored as **Delta tables**.

**At this stage** : | ***data is raw*** | ***schemas can change*** | ***quality is not guaranteed***

The goal is simple : **Get all data into the lakehouse"** safely.


#
</details>


<details>
  <summary> 2. Data engineers <b>create layers and pipelines </b> </summary>

<br/>

Next, Data engineers organize the data. 

They build layered pipelines, often :
- raw layer
- cleaned layer
- business-ready layer

Using scheduled jobs, they :
- clean data
- validate it
- standardize formats
- apply business logic

These pipelines run automatically and produce **trusted tables**.

> **"Pipelines turn raw data into reliable data."**
 

#
</details>

<details>
  <summary> 3. Governance experts <b> define Unity Catalog rules </b> </summary>

 <br/>

Once ***data becomes valuable***, governance comes in. <br/>
***Data governance and security experts*** work with data engineers to :
- define who can access which data
- set rules per schema, table, or column
- assign ownership
- enable lineage and auditing

This is done centrally using **Unity Catalog**.

Security is defined once and applies everywhere.

> **"Governance is built into the platform, not added later."**

#
</details>

<details>
  <summary> 4. <b>Data is exposed as products</b> </summary>

<br/>

Now something important happens. Instead of sharing raw tables, teams expose **data products**.

A data product is :
- a curated dataset
- well documented
- governed
- stable
- trusted

These products are meant to be reused by many teams.

> **"Data stops being a pipeline output and becomes a product."**
 

#
</details>

<details>
  <summary> 5. <b>Analytics and dashboards are built </b> </summary>

<br/>

***Analysts and BI teams*** use these data products. <br/>
They :
- write SQL queries
- build dashboards
- define metrics

They do not copy data to another system.

They query the same Delta tables governed by Unity Catalog.

> **"One data product powers many dashboards."**

#
</details>


<details>
  <summary> 6. <b>Data science and AI use the same data </b> </summary>

<br/>

**Data scientists** use the same curated data products. <br/>
They :
- explore features
- train models
- validate predictions

No new data copies.

No separate security rules.

Models read from and write back to the lakehouse.

> **"Analytics and AI share the same foundation."**

#
</details>

<details>
  <summary> 7. <b>Data is served to applications </b> </summary>

<br/>

***Results*** are not just visualized. <br/>
They are also : <br/>
- served to applications
- written to operational databases
- exposed to external systems
- shared with partners

This is where data creates real business value.

> **"Data moves from insights to action."**

#
</details>

<details>
  <summary> 8. <b>Business users interact in simple ways </b> </summary>

 <br/>

Finally, ***business users*** consume the data. <br/>
They use : <br/>
- dashboards
- reports
- natural language queries
- shared datasets

They never see pipelines or clusters.

They just get answers.

> **"Complex systems, simple access."**

#
</details>

<details>
  <summary> <b> The full flow, end to end </b>All inside one platform. </summary>

<br/>

Raw data → Lakehouse tables → Curated data products → Governed access → Analytics, AI, and apps → Business decisions


#
</details>


> **In real companies, Databricks connects data engineers, governance teams, analysts, scientists, and applications into one continuous workflow.**

<!---------------Databricks in Real Company Workflows------------------->
</details>


## 1.4 Tour Into the Databricks Interface

<details>
  <summary> Expand </summary>

The goal is not to memorize menu, but to know where things live and when to use them.

As a Data Analyst, SQL section is important for you. There is no way around it, you can use all these stuffs.
<details>
  <summary> <b> SQL section </b> </summary>

<img width="262" height="337" alt="image" src="https://github.com/user-attachments/assets/0700a1e4-da3f-4bdb-8d41-d70f2c7370fb" />

</details>

In new section most important thing is **Catalog and Compute**

Let's see what is Unity Catalog?
<details>
  <summary> <b> Unity Catalog/Catalog <code> Metastore > catalog >  schema > Tables | Views | Volume | Functions </code> </b> </summary>

<img width="220" height="343" alt="image" src="https://github.com/user-attachments/assets/b472f095-2e6a-4bf0-bba4-f0ecc427fbd6" />

We have always ask ouself where is the data in each platform? <br/>
So in databricks the data is present in something they call ***Unity Catalog or Catalog***. <br/>
They present the data in a way it looks like database. It looks like a database but it's not the real database. There is no DBMS is running over here.

<img width="600" height="437" alt="image" src="https://github.com/user-attachments/assets/94c6da65-51d3-4abd-b951-c33365111adf" />

**Compute** : In the free edition you will have only one compute/server/machine for you to use. Bcuz it cost, It is virtual machine of Microsoft or AWS or GCP.

<img width="600" height="442" alt="image" src="https://github.com/user-attachments/assets/b6a27f24-94a1-4e58-98ce-958b0df9676c" />

> So, You always need a storage/Database/DataLake and Compute/Machine/Server

In databases, data always stored in files. And in SQL Server, PostgresSQL, Oracle etc the files of databases are not for us, we're not the person who go and start working with database files. That file is closed file locked file and only SQL Engine/Oracle Engine can interact with those files.

But in databricks, Data Lakes, files are like open format called ***parquet***. So the open format file where everyone is welcome to use the data

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/fd0e5b20-a1ff-43eb-9fc7-17a8073d9d4c" />


In the background everything is stored inside a **Blob Storage** in the cloud. This is the bigger term used in cloud. 
It like a container of files. So we can put inside anything like a csv file, an image, and the standard way on using files in databricks called **delta files** or **delta tables**. They are bracket files but with some extra logs and transactions which have some add on benefits. But it is an open file, you can use it for any purpose. So you can use it in databricks outside databricks.

<img width="350" height="245" alt="image" src="https://github.com/user-attachments/assets/ef3ac0a7-f151-4733-ada6-00d2dff91314" />

Earliers as Data Analyst/Engineers we had to learn how to work with Delta files like read files, earlier you can immediately jump to SQL and you had to read this file through python by loading this. Which is still very hard for few people like only expert can do this.

Let's make something that everyone knows. Something looks like Database. So they build something Unity Catalog on top of it(delta files) i.e. MetaStore <br/>
that makes it look like database for you and database everyone can use it.

> **`Metastore`** > **`catalog`** > **`schema`** > `Tables` | `Views` | `Volume` | `Functions` |

As we know in DBMS system we always have hierarchy on how we oraganize and find our data. So in databricks It starts with `metastore` this is the highest node and then we can build different catalogs in databricks like one catalog for development another catalog for production may be for HR another catalog so for each project each big thing we can create a new `catalog` and depends on each project we create `schemas` like bronze, silver, gold. So far everything is logical, oraganized data.
You don't see data inside `catalog` or `schema` It's just how you organize the company data.

Inside the `schema` things get interesting, you cab build a table(rows, columns) and you can also `view` on top of it. <br/>
You can also build something called `volume`.
> **`Volume` is just like a folder that looks like `blob storage` where you can put data that is not ready to have the `table` shape**.
> - Not all data is in `Table` form (columns and rows). So we can have `JSON` file, `image` file, `video` file whatever
> - So can't always have Structured data like table and view so that't why we have Volume
> So `Volume` is a folder/container for those kinds og stuffs.


> **`Functions`** : We also have something called `functions` which is an advanced thing. In case you want to build some automatic functions for data filtering, or function for security stuffs and stuffs like that then we build functions

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/c994df34-e759-4566-99c9-d0b53473e97a" />



This was the main idea behind the ***Unity Catalog/Catalog***. It is just a way on how to organize the data and to hide the complexity behind the databricks

As a Data Analyst, you don't have to know all these stuffs but as a Data Engineer you must have to know how to process delta file, how to load delta files.

</details>

Inside the catalog, we have `My organization` > `workspace` | `system`

<details>
  <summary> <code> My oragnization > Workspace > schemas > tables| views | volumes| functions </code> </summary>

So, `My oragnization` means this is my big company over here. <br/>

Below it we have `workspace` for each project so for project1 we have one workspace1, for project2 we can have workspace2 and so on.

Inside `workspace`, we will have `schemas`, so here we put silver, bronze and gold and stuffs like that.

Inside it we have `tables`, `views`, `volumes` or `functions`

> Inside the `workspace`, There is a `default schema` so if you don't create your schema your data will go into this default schema.  

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/408a7d7b-9999-4e08-85c3-04d08327c5d8" />


</details>

Now Compute, There is two things about Compute in databricks : 1. Clusters and 2. SQL Warehouse

<details>
  <summary> Compute  : <code>Cluster | SQL Warehouse</code> </summary>

<br/>

About the compute it is very complex story. But It's way better than before.

Databricks Computes splits into 2 sections :
1. Clusters
2. SQL Warehouse.

**Cluster**
- As a Data Engineer we have to understand everything behind cluster.
- Cluster is meant to be for Data Engineers. A cluster is something that as a data engineer we build in order to configure how to process data.
- Usually we do everything using `PySpark` and `Python`.
- We have a lot of details to prepare like some installation and some libraries.

So, Clusters are something advanced in order to do ***Data Engineering*** or ***Data Science***.
So for Data Engineers/Scientists, they must have to know clusters.

**SQL Warehouse**
- For Data Analyst, you will be using SQL Warehouse.
- It is something like Cluster only but It is made reallt easy that you can configure it very simple easily.
- You just have to say like the way you select your T-shirt size XS, S, M, L, XL. Similar to this just define the size of your SQL Warehouse and start using it.

SQL Warehouse is totally optimized and prepare for Data Analyst by reducing whole complexity  of the whole thing under the hood it. 

So, As Data Analyst you don't have to understand anything behind the scene. You just define the size of your SQL Warehouse and start using it.

> In the free edition we allowed to use only SQL Warehouse.

There are 2 types inside each 2 of these.
```md
Databricks Compute
│ 
├── Cluster  for Data Engineers
│    │
│    ├── Serverless
│    │     │
│    │     └── Shared
│    │           ├── Job Compute
│    │           └── All purpose
│    │
│    └── Client managed
│          │
│          ├── Single User
│          │    ├── Job Compute
│          │    └── All purpose
│          │
│          └── Shared
│               ├── Job Compute
│               └── All purpose
│ 
└── SQL Warehouse for Data Analysts
     │
     ├── Shared
     │    ├── Job Compute
     │    └── All purpose
     │
     ├── Serverless
     │             
     │
     └── Client Managed
             ├── Classic
             └── Pro
```


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/e474adfc-54d7-470a-9fb6-0bf046148144" />


> **Serverless** warehouse : It is something that start immediately and always online. You can use it immediately.
> - Old way was start your cluster(warehouse), wait for 5-10 minutes until databricks starts Azure Virtula Machine/AWS cirtual Machine.
> - So It is the process which tool a lot of time.The speed  was not that fast. that's why we have something called Serverless. It is always online and you pay for only if you use the data.
> - So once you click on Start warehouse then only you're going to pay for the whole infrastructure for Microsoft and Databricks if you're using it otherwise if you just start and not using it then you will not have to pay.
> So only if you start using your data, processing your data then only you will pay for the service.

Note : Serverless is a type of warehouse that is always online and it is fair to use bcuz you onlly have to pay for the service if you're using and processing your data. Earlier you had to pay for resources without even using it. Even you just started it.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/98feb0cc-6559-4f3e-a083-523c7f73ba98" />


So as data analyst yoou don't have to go to compute section, you always go to the SQL section there you find SQL Warehouse from there you can start using it.

One thing cool here in serverless is that since we're at cloud and we're doing the project in the cloud if we're working daily like building a dashboard and stuffs and working with data we always use the size smalll which means small servers but let's say we have presentation day and an important meeting and we have to show a very important analysis to manage and stakeholders, so on that day, we can make the size large in case to make things faster and smooth. and then get back to the small size so that it will cost you less.

> In the cloud, you can always scale up, make everything very fast for important days and scale down everything so that it costs you low while not needed.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/7b2c04ee-0998-4d8d-9174-c35a367691bb" />

You can also decide to shutdown after 10min or so on. It is so easy to configure now.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/4840d037-cfab-47c1-966f-068433023b02" />


But How Data Engineers do the compute is completely different than this, there we need to connect databricks to Azure/AWS/GCP stuffs? We will see it later 

</details>



<details>
  <summary> <b> Summary of Databricks UI </b>Interfaces </summary>

- **Catalog (Unity Catalog)** : Where data lives, how it’s organized, and who can access it.
    
- **Workspace** : Where you create and organize notebooks and project files.
    
- **Compute** : What runs your queries and notebooks. Needs to be active for work to happen.
    
- **SQL Editor** : Where analysts write SQL and explore data.
    
- **Queries** : Saved SQL queries you can reuse and share.
    
- **Dashboards** : Where queries are turned into visual reports.
    
- **Genie** : AI assistant to explore data using natural language.
    
- **Query History** : Shows what queries were run and helps with debugging or reuse.
    
- **SQL Warehouses** : Dedicated compute for SQL workloads and dashboards.
    
- **Jobs & Pipelines** : Used mainly for automation and production workflows.

#
</details>

[**Workspace UI | Databricks on AWS**](https://docs.databricks.com/aws/en/workspace/)

<!-----------------Tour Into the Databricks Interface----------------->
</details>


## 1.5 Getting Data Into Databricks

<details>
  <summary> Expand </summary>


Before you can **analyze data**, you ***need data inside Databricks***.

There are a few simple ways to do this, depending on where your data lives.

<details>
  <summary> <b> Materials to Read </b> </summary>

- [Data Catalog](https://docs.databricks.com/aws/en/catalogs/)
- [Schema](https://docs.databricks.com/aws/en/schemas/)
- [Volume](https://docs.databricks.com/aws/en/volumes/)
- [Table](https://docs.databricks.com/aws/en/tables/table-overview)
- [View](https://docs.databricks.com/aws/en/views/)

#
</details>

<details>
  <summary> <b> Main Ways to Add Data </b> </summary>

<br/>

1. **Upload a local file** : Best for learning and quick practice.
    
2. **Add data to a Volume** : More organized and closer to real project setups.


<details>
  <summary> How to upload your data as a Data Analyst? </summary>

Go to `Catalog` > `My organization` > `workspace` > `default schema`

- You can either put you data in default schema or you can create your schema and put data inside that schema.

Right Click on `workspace` > Create Schema option > "salesDB" create

Now you have salesDB schema, It is empty now you can put your data inside it.

Generally when you work on any project you generally don't manually upload data to databricks. <br/>
It is just for Data Analysts in order to do quick exploration. But We as Data Engineer we never upload data as like this.
As Data Engineer we connect the data using the Networking and codes and bring everything yo databricks in order to build automated pipelines from the sources. We don't upload data manually to databricks.

Here we will do it manually as in free edition we can't build those automated pipelines to get the data from the sources.

So, There are 2 ways to do it, Hard way and easy way.
1. Click on `New` > 'Add or upload data' > `Create of modify table` | `Upload files to a volume` | Databricks Connectors : ServiceNow, Salesforce, Amazon S3, Dynamic 365 etc | Fivetran Connectors : GoogleDrive, OneDrive, Jira, GitHub, webhooks, Apache Kafka etc |

We have a lot of tools, you can create an account and you can start using the data that is avaialble on those platform. <br/>
But in real projects data engineers should do real automations they don't use this way.

Let's start with `upload files to a volume`
- First thing you have to do is create a `volume` inside you schema like similar to table.
- It is just a folder that you creating on your PC. lets call this `volume` "mydata"
- There are 2 volume type either you can use unity catalog from Databricks  or you can use external valume in case if you want to do something externa in Azure/AWS.
- We here stay with databricks, we're not using any other cloud provider.
- Make sure you're at right `workspace` and correct `schema` > Create the volume.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/b6628a6d-1dfb-40e5-8ae2-64a8b27c0e8a" />
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/1f688c43-f968-4489-b3aa-bf1bde01fb8a" />

So, volume named "mydata" is created it is nothing but a folder and it is in the cloud. And you can put inside it whatever you want like images, videos , csv files etc.

In order to upload things we can click on `Upload to this volume` or `New` and upload your data/datasets.

Make sure the correct destination for your files > 'Upload' | uploaded successfully.

Now in order to check you can go the `catalog > workspace > salesDB > mydata > file1, file2, fileN`

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/cb0c3f21-5ea1-4454-80f8-058cb56cc880" />
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/b404fab7-0879-4ceb-92e7-b186e6d8524f" />

Now question is How to Query the data? <br/>
For that go to `New` > `workspace` > `Create` something called `Notebook` <br/>
- Now we can write SQL query inside the Notebook or 
- if you don't want to do it in Notebook you can go and use `SQL Editor` > `New query` it does the same thing. 

```sql
SELECT * FROM csv./volumes/workspace/salesDB/mydata/dim_customers.csv
```
- start and attach compute and run it.
- Here, we're not using the databricks delta files we're just using the csv files and querying the data. So we're not using the full benefits of databricks.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/f7d8685a-5852-409a-b2be-7ca3c9143dd0" />

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/2096fea2-9156-45d6-a4c7-677600359341" />

But this is a bad to work with your data iniside the databricks.

We should always work with a delta tables, not with volumes, volume is something which is not prepared, it's something that is not clear that's why It is not recommended to work with volumes instead create a delta table.

Creating tables is very easy. <br/>
Go to `New` > 'Add or Upload data' > `Create or modify data` > `upload data` > `create table` <br/>
Databricks doing everything behind the scene like creating a table, creating delta files, and storing everything inside delta files or parquet files. You will not see all those stuffs.

Now when you go to `catalog > workspace > schema > new_table` 


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/87524178-344b-4d29-9bf2-f159720f4a9d" />


So basically we created the table using delta technology open file. Now all the features of `PySpaark`, Multi-processing, parallel processing is going to be unlock on this table bcuz we're using an advanced format.

Of course, we're not seeing the delta files now, you're working with delta tables like tables in any SQL database. Everything back to SQL for you.
Now we're using delta files, using whole platform of multi-processing, everything is in RAM (in memory processing)  All these complex things become very friendly for Data Analyst and that's possible on this Databricks platform. So, We're working on cloud with multi-processing the big data with huge complex queries with fast performance. Now you're not working in simple database, you're woking directly in data lake. So basically we're working directly in scalable system.  

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/ece7d229-e7a2-4e3f-85da-f0f1a49e96c1" />


> Note : Volume is not for Data Analyst, It is something for Data Engineers.


</details>



#
</details>

<details>
  <summary> <b> Real-World Data Projects </b> </summary>

<br/>

In real companies, **data engineers don’t upload files manually**.

We usually connect Databricks directly to source systems like databases, APIs, or cloud storage and automate ingestion with pipelines. 

The **Databricks Free Edition is limited**, so we use file-based methods here to learn the concepts without extra complexity. 
The workflow stays the same. Only the data source changes later.

**Resources**

[Upload files to Databricks | Databricks on AWS](https://docs.databricks.com/aws/en/ingestion/file-upload/)

[What are catalogs in Databricks? | Databricks on AWS](https://docs.databricks.com/aws/en/catalogs/)

#
</details>

<!----------------Getting Data Into Databricks------------------>
</details>

## 1.6 Assignments

<details>
  <summary> Expand </summary>


Go through the tasks below and check them off as you complete them.

- [x] Read and understand what Databricks is → [LINK](https://docs.databricks.com/aws/en/introduction/)

- [x] Explain in your own words what Databricks is 

- [ ] Create a free Databricks account → [LINK](https://www.databricks.com/learn/free-edition)

- [ ] Explore the Databricks UI (don’t worry, you won’t break anything)

- [ ] Get your data into Databricks (Use Files from Analytics Folder)
    - [ ] Upload Data into Volume
        - [ ] Create Volume
        - [ ] Upload Sales Files
        - [ ] Query Data. E.g  ```SELECT * FROM csv.`/Volumes/workspace/default/sales_demo/dim_customers.csv```
         
   - [ ] Upload Data into Catalog Tables
        - [ ] Create Schema
        - [ ] Upload Files as Tables into the new schema
        - [ ] Query Data
     
<!---------------- Assignments ------------------>
</details>
