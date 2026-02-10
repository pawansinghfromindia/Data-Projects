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


#
</details>

<details>
  <summary> <b> What Databricks Is (High-Level) </b>  </summary>


<img width="350" height="218" alt="image" src="https://github.com/user-attachments/assets/5fd3a980-f40c-4f4b-8fc4-a02bac6eb8a0" />

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
  <summary> The real story in companies </summary>

<br/>

> **"Databricks is not used by one team. It is used by many teams, in a specific order."**


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/8e281b17-492c-4123-861d-a04408e78fc3" />


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

<details>
  <summary> <b> Databricks Workspace UI </b>Interfaces </summary>

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
