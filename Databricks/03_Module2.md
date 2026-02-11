# Module 2 : Data Analytics Using Databricks 
- Analytics & Analysts Maturity
- How Data Analysts uses Databricks
- Project : Data Analytics using Databricks

> We're going to focus on Data Analytics part, As data analyst how to use this databricks platform?

## 2.1 Analytics & Analysts Maturity
<details>
  <summary> Expand </summary>

<br/>

When you switch between companies or you join, in each company try to map this picture :

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/8b14640f-3a09-48c3-bf6b-078fa83dbb48" />

It is important to understand where the company is at bcuz different companies have different scenario with data with plaform ans stuffs. <br/>
Some even small companies do advanced stage of processing and some big company at the start of this picture.

So, this picture will help you to understand and build new project in a company.

This is like a roadmap for data analytics. 

> **Raw Data**
<details>
  
Some companies just have `Raw Data` and they might didn't do anything with it. 80% of the companies are such, they're just busy with their products 
and processes. They thinks raw data as extra luxury if you have extra money then may be you can do something with the data.

But Scenario changed this days, all companies understood that without good data, you're doomed especially in the AI. That's why many companies are
currently in the raw data.

</details>

> **Cleansed Data**
<details>
Some companies did understand that raw data is not usable.
So companies start building some data warehouse and data lake for this they hire **data engineers** and they start cleaning their data. 

</details>

> **Standard Reports**
<details>
Once those companies have cleased data, they hires **Data Analysts** to build stand reports like you have excelsheets and you're tracking or monitoring
the whole process using this excel which is not good Instead make a standard report that whole department of the company can use. <br/>
Example : How many order we got yesterday, or last month, last year, increase or drop.

Everything you build in PowerBI, Tableau, they are almost all of them are like you're building standard report for the company.

It is something that company needs a lot bcuz Most of job is done inside excel and no one is building clean standard reports.
That's why many companies hire **Data Analyst** in order to build for them standard reports.

Here companies have huge audiences that's going to use this standard reports like n number of **Business Users**.

Even today a lot of companies still uses excel, powerpoint for presentation in order to build their reports. So they're not using tools like PowerBI, Tableau
yet. So they don't have Data Analyst separately. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/35026ddf-9d28-431e-abd0-a4aa426d4100" />


Now if company want to make themself domain driven or data driven company, You can't just wait on standard reports. <br/>
The thing is standard reports take time to be build from new data for Data Analyst or PI developers. Build a reports will take a weeks or months and as
you have huge audiences (Business users) they will say It is not exactly I need, I need one extra column, one exta filter, new dataset to be inserted and so 
on something different. They always ask for extra stuffs as Data Analyst you will take time to build new report. So you're bottleneck for people.

So somehow you as a Data Analyst have to offer adhoc analysis in the companies. So that Business Users can do his own analysis like those filter and stuffs.
They don't have to wait for anyone from the tech/IT to build the report.

So next level is to Let people build their own reports/insights and you as a IT Data Analyst not bottleneck.

</details>

> **Ad Hoc Reports and OLAP**
<details>
Same goes for nect level not only allow audience(Business users) querying the data but also make them build their own dashboard through self-service BI and
Agile Visualization.

</details>

> **Self-Service BI Agile Visualization**
<details>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/bf35488d-a26f-43b3-9779-8c260026063a" />


If the company id already offering the solutions, like company business users has different option to consuming the data, they can consume my PowerBI reports
or Tableau or something but if they want, they can go and use SQL Editor to do it. 

Note : Very few companies offers thrier business users to play with their data. Like they don't offers like way to do self-service BI. 


As a Data Analyst you always have to answers What happened? Why it happened? where is the bottleneck? How many order happens last month?
Which step is good/bad in the process? 

But if you want to ask about Future, what is going to happens? like Predictions there comes Data Scientists role to answer these questions.
</details>

> **Machine Learning Stuffs : Data Scientists**
<details>
It is very rare. It is going to dream if you have a real data scientist working on the next level.
Companies hire data scientists. They joined and they do some machine learning stuffs(feeding the data to models) and predict the future.
But first Data Scientists will look for data where is data is it raw? So many times data scientist also have to play to role of Data Engineers stuffs while 
feeding the data to their Machine Learning Models.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/51281cb9-dfb2-4a50-944c-33d3570cf0e2" />


We don't have to focus on Machine Learning and data scientists stuffs here.  <br/>


We have to focus here on analysing the data. <br/>
This is not only way to analyze the data. <br/>
A tool like Databricks helps you do those stuffs. But it not does the job for you, you have to clean the data as data engineer and you can do the whole BI
self service thing using Databricks.

</details>

> **Databricks Self-service BI** is amazing tool to use. 

<details>
We can do Data Exploration using Databricks dashboard but for standard report we have to use PowerBI/Tableau which dominates. 

As Data Analyst 80% of your job is building PowerBI/Tableau stuffs. and Ad-hoc Reports and Self-Service is advanced and extra for you that you can do using
Data Bricks.

> Of course we can do whole thing using PowerBI but it is not recommended bcuz we have better options available to do that.
</details>

<details>
  <summary> <b> Level - 1</b>  <code> Excel </code> </summary>

- Bcuz It is easy 80% 0f the companies do this.
- 80% of people are doing manual work and this is very ill way to a company.
- Data Scientists are repeatedly cleaning and using the raw data, same work repeatedly and no real analytics .
- It is limited to database only, not data warehouse or Data lake.
- Here, you only work with small set of data. 


<img width="500" height="207" alt="image" src="https://github.com/user-attachments/assets/24443dbf-5ffa-4315-a548-29074160ddd1" />


That's why need a second layer, Level-2

# 
</details>

<details>
  <summary> <b>Level - 2</b> <code> PowerBI </code>  </summary>

- Companies not using Excel/Powerpoint anymore, they starts using PowerBI where things can be more organized and nicer.
- User powerBI to pull the data and start building reports and visualization.
- Here we're doing everything ***ETL = Extract Transform Load***, all the heavy lifting is happening inside PowerBI. This is still better than excel but
  there are better ways to do this.


<img width="500" height="336" alt="image" src="https://github.com/user-attachments/assets/83bc2546-df39-4ed9-b88d-761a6498574f" />

But extraction and Transformation is not something that is made for PowerBI in big datasets. bcuz on Big Data PowerBI is going to take too long time
to do the data transformations and loading.
  
Even if data gets litter bigger in 1 GB or so it starts, It is going to be out of control to handle in PowerBI

That's why we need another level - 3.

# 
</details>


<details>
  <summary> <b>Level - 3</b> <code> Data Warehouse </code></summary>


- Let's build a data warehouse, It is not build by Data Analyst, They will ask Data Engineers to build it.
- So Data Engineers build automated pipelines to do ETL (Extract Tranform and Load) and you as a Data Analyst connect your PowerBI only to do
  Data Visualization.
- With that you as a Data Analyst reduced your heavy lifting and now you're focusing on answering the business questions asked to you.
- This is a better way than before, bcuz you're not busy wasting time in doing ETL instead of focusing on business and delivering fast reports.
- So, From a month to a week and now you can prepare your reports in days 

<img width="500" height="518" alt="image" src="https://github.com/user-attachments/assets/70297592-f3b4-4e22-8f63-f832d9472fe5" />

So basically It's not the job of Data Analyst to work with raw data.

> Now, We can have ***only Structured data in Data Warehouse*** and in companies we have a lot od interesting data not having the fixed structure 
that's why we need ***Data Lake***.
- Data Warehouse, they're going to die over the time as data gets bigger and bigger.

- As Data gets bigger and bigger the structure of data will change, Data Warehouse can store only structure data, so It will die over time,
  that'w why we need something which can store more than just structure data and that is ***Data Lake***.

- Example if Data Analyst ask Data Engineeras to bring `JSON` data but Data Engineers says wait wait hold on we can't put unstructured data to
  Data Wrehouse bro or if it is asked to bring more big table then Data Engineers can denied that It is already taking 12 hrs to load the data, we can
  bring more big table than this etc etc

- Not only that a lot of Data Analyst things can be rejected by Data Engineers bcuz of Limitations in Data Warehouse.

# 
</details>

<details>
  <summary> <b> Level - 4 </b> Future is <code> Data Lake </code></summary>

- So, Now Data Engineers is going to build ***Data Lake*** using a scalable system Databricks then now for you as Data Analyst not only possibility to work
  with Databricks like you can connect your PowerBI to databricks infrastrucure very fast to work on all kinds of data and huge large tables and also you
  can use databricks to do data explorations on those big tables.

- If you as Data Analyst has reached at this lable like your company is working with databricks and building Data Lakes and you're having skills of doing
  all these stuffs that means you're mastered. You know the best tools. As tool wise you are best rest Mindset is always prevail, only tools don't gurantee
  everything perfect. 

<img width="500" height="771" alt="image" src="https://github.com/user-attachments/assets/292330a2-98a1-4d2d-a752-0a34d73d5146" />


So Now we move from level-1 to level-4 where now we can work with very different types of data that we didn't dream before, we can work with big data
and stuff like that.

#
</details>

So, Now companies are forced to move from Excel to PowerBI to Data Warehouse to **Data Lake** and that's bcuz of AI. It's all about AI now.

#
</details>
<!----------  Analytics & Analysts Maturity --------------------->



## 2.2 How Data Analysts uses Databricks
<details>
  <summary> Expand </summary>

<details>

<br/>

In order to let's see How a Data Analyst use databricks in a company

**Databricks in Company's workflow** <br/>
<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/9fab28b9-8f7a-4477-a1cf-67e151adc443" />

</details>

###  a)  Data Analyst Role in Databricks
> Building Reports/Dashboards and Data Explorations

###  b) Data Analytics using SQL Editor(Data Exploration)
> Most Data Analyst do use SQL Editor for Building Reports/Dashboards and Data Explorations as this is easy way.

<details>

> **Dashboard Making**

You as Data Analyst you have the access to prepared final refined data i.e. bronze to silver to ***Gold Layer***.

In the big data projects, you will have a lot of data big tables not just one but many. So as Data Analyst even though you have access to refined
data i.e. ***Gold Layer***, you can't directly start building your PowerBI Reports/dashboard using those tables. It is hard to do so bcuz you don't know
the content of the tables which table/dataset to use,

As a Data Analyst you have to explore the data/tables/datasets. For ***Data Exploration*** you have a lot of tools in databricks like easy option is use
***SQL Editor***. Using just `SQL` you can manage to start exploring the data.

Some time you not only have audience as Business Users, who consumes your reports/dashboard, there are business users known as **Power Business Users** 
who has`SQL` skills so you can take him and bring both of you in SQL Editor and start exploring the data in data lake in order to identify what data 
exactly is needed. 

Both of Data Analyst and Power Business Users can work in SQL Editor together, Data Analyst starts querying from start to end and then share it 
over mail to power business users and then both start working on the same query. <br/>
both of them start discussing that which tables is right to be join with this table to get that exact data and so on. <br/>
This is kind of brainstorming for both of them and to get what exactly is needed. <br/>

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/eea62413-f2c7-4d4c-b0b3-619c44acc5b5" />

<br/>

> **Dashboard Version 1.0**

Both of them ended up with differen queries in order to get the required data.
With that put all those query in one dashboard (first version od dashboard) 

So this is what we do in databricks that put all the queries in dashboard in order to have the first look of our usecase/report.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d4f8cc89-8aa4-448f-97ee-c8855990f371" />


You can make changes until you reach what exactly is needed. <br/>
Once everyone is satisfied and happy with it, like you as Data Analyst, Business Users, Power Users, Managers etc.

This is exactly solve a lot of problems.

Now Next step is, you just have to expose it for audience (standard users)

> **Final Dashboard - PowerBI Report**

Expose the dashboard/reports for audience (standard users) that means convert this Dashboard to a PowerBI Report

<img width="643" height="479" alt="image" src="https://github.com/user-attachments/assets/374e7d60-801a-4446-aeae-e083c76f2573" />

Data Exploration is very important for you as Data Analyst. Most of your time will be spend in exploring data only. 
Suppose you have an `Excel` or `Normal Database`, you're going to have only 5-6 tables that's it but since you're in Big Data, Data Engineers will give you
a lot of tables and you will see 100s of tables which is too much for data analyst. But to honest Data Analyst will works on few final tables which are 
important for reporting not the raw, processing or even all refined table. But since we have a lot of tables as a Data Analyst you will have to be very
good at Data Exlorations. 

</details>

###  b) Data Analytics using Notebooks
> Some of the Data Analyst do use Notebooks for Building Reports/Dashboards and Data Explorations. This is an advanced way.

<details>
  
- There are reasons and benefits attached to using Databricks Notebooks.
- They go crazy they're curious people, want to explore and learn the new things, they don't only want to use `SQL` they also want to use `Python`
- They will not do programming for pipeline but they will use the features of `Pandas` of `PySpark` in order to analyze the Data.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/a659532f-643c-4485-a7ce-0d898457b623" />

</details>

###  d) Data Analytics using Dashboard

###  e) Data Analytics using AI (AI/BI Genie)

<details>
  <summary> AI Genie </summary>

<br/>

We're here not talking about Machine Learning or AI stuffs where AI Model.

Here we're talking about AI Genie It is introduced recently and it is future of How to work with data as Data Analyst ?

> **DatabricksIQ**

Databricks is very smart they let you add data. Inside the catalog they store a lot of information they a store everything about your data metadata.
So they keep training everything happening on their platform.
They know which table is the most important table in the whole company, they know all the queries you're doing, they are stored somewhere in databricks,
they know dashboard that just created, they know the catalog itself by comments, tags and other stuffs.

They feed all those data and train their AI models on it.

With that Databricks AI becomes smart enough to answer business questions using LLM and they have their own models they build like GBT the one who converts
plain english to SQL.


</details>


<details>
  <summary> <b> Databricks HandsOn </b> </summary>


<br/>

> **Loading the Data into Databricks**

Open databricks using your web-browser, Since we're usings Compute/Servers/Machine which are on cloud.

Open Unity Catalog or Catalog, It is what similar like Database for normal Dabase. <be/>
Basically Catalog is database for Data Lake.

We as Data Analyst doesn't work with `volume`, Data Engineers do work with it.

So Let's create a table by uploading if for learning purpose, otherwise in companies we gave Data Sources from where we get the data through automated
pipelines created by Data Engineers. 

Unity Catalog of Databricks has a lot of amazing things. We have something called **Metadata**
- in databases metadata is like just description of the tables and columns and few other stuffs like indexes, etc
- But in databricks they went to a next level of the metadata.
- They knew that metadata is core of any AI use cases in the future. That's why they focus a lot on offering a lot of features inside
 metadata or catalog so that they used AI to learn on the usage on the metadata.

**What is metadata?** <br/>
Data about data is metadata. <br/>
example : name, columns, datatype, comments, tags.
- The more you add content in the metadata of databricks, the smarter the platform is going to be bcuz It is going to use all those metadata to teach AI
  to fine-tune the AI Model that later you're going to use AI Model to chat with your data using AI.

- The whole mindset changes as we work with Databricks Catalog,  before Catalog we just used to add comments for nice info added for the project team to
  to understand what it is. But now we add comments not only for us but for AI also. It becomes more important now than Data Moduling  

**Table** has a lot of things in Catalog : Overview, Sample data, Details, Permission, Policies, History, Lineage, Insight, Quality etc 

In real Projects AI has no clue about those columns in a dataset bcuz those are cryptical names. There you have to read a lot of documentations in order to
understand the columns. So there you have to put descriptions so that AI will use it later.

***Histroy of Table*** is an amazing thing you can see full version of your table, you can access whole history of the table. 
You can see log of everything happend in table by whom, at what time, what changed everything. which is not possible in normal database. That's bcuz
here delta tables use Open format of table. 
```sql
DESCRIBE HISTORY table_name;   
SELECT * FROM table_name VERSION AS OF 5; 
RESTORE TABLE your_table TO VERSION AS OF 5;   
```

In Quality, we can add quality checks like How many nulls etc etc. 


> **Once you have Data, you can explore data in SQL Editor**

- The results you get only first 1000 rows only, bcuz there are deault limit to it, if you want to see full data remove the limit.

- Also while Querying, You have 2 options either you give the full path of the table or configure it to based on schema.

Without Configuration
```sql
SELECT *
FROM workspace.schema_name.table_name;
```
After Configuration
```sql
SELECT *
FROM schema_name.table_name;

-- OR even 

SELECT *
FROM table_name;
```

While using the databricks, you start your day with one tab and ended up by at 20 tabs.

> **Data Exloration using databricks SQL Editor**

We can do multiple Queries and not only result can be download as csv, even and many other formats, but also you can share this query in your project team
and multiple people can work on it at the same time.

You can see **Visualization** of your Query data, here there are a lot of options but it is not as powerful as PowerBI/Tableau.

You can also add these different visualization to ***dashboard***.
Each time we do query and find insights about data we add the visualization to dashboard and once we find the insights after data exploration and of those
visuals at place in Dashboard, now we can share this dashboard with others. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/a13138e7-a63d-4bdd-b1f1-219c5566f0f8" /> <br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/7ee1473a-01e7-42ce-9baa-3b538ff0d993" /> <br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/8021bc63-d56e-4c16-acd9-9309a59af5e8" /> <br/>

We're basically here <br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d585b235-1349-4c25-ac45-7b11b6729cbd" />

Now if we go and give to standard users they might not like it bcuz it is not powerful as PowerBI/Tableau.  They demand we need logo, filters stuffs,
colors etc etc, here it is very simple. 

This Databricks dashboards oare only for small group of people and teams for exploring the data and understanding how to solve the business issues.
That's why we don't expose Databricks kind of dashboard to big audience(Standard users). 

It is very expensive also, each time you do query, It is going to use resources of databricks that is on cloud server of Azure/AWS/GCP for which you have
to pay for it. So, if you give this dashboard to huge audience, each click will cost you bcuz you pay as you use. It's not like PowerBI you put the data
in datasets and import mode kind of stuffs and for calculations you're not paying.

Everything happens here in databricks has a price, companies pays for it. That's why we do use databricks dashboard for exploration purpose not exposing
it to huge audience. 


There is another way to do all the stuffs what we did through Databricks SQL Editor and then use dashboard.

Like as a Data Analyst, If you don't want to write Queries, you just want to build a dashboard. 

Simply as a PowerBI Guy. I want to explore the data and build a nice dashboard. 

Go directly to the Dashboard.
- It will open a brand new dashboard
- Like any other tool, For this you need data first
- Here you have different options either you upload the data like a powerBI or select the table you want or write query

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/50365138-ac06-4a45-a0e9-0336d439cbc7" />


#
</details>



#
</details>
<!---------- How Data Analysts uses Databricks --------------------->

<!---------- How Data Analysts uses Databricks --------------------->

## 2.3 How Data Analysts Work Using Databricks

<details>
  <summary>  Expand  </summary>

### 1. Exploring the Lakehouse with SQL

Data analysts today have direct access to a full data lakehouse with many curated tables. Their first step is usually exploration. 
They spend time writing SQL queries in the Databricks SQL Editor to understand the data, validate assumptions, and explore patterns.

At this stage, the focus is not reporting, but learning what the data can and cannot answer.


### 2. Collaboration with Business Users

Data analysts often work closely with business users who understand the domain and can write SQL themselves.
Together, they refine queries, validate logic, and make sure the right data is being used to answer the real business questions.

This collaboration helps avoid building insights on incorrect or misunderstood data.


### 3. Draft Insights with Databricks Dashboards

Once the analyst gains confidence in the data and queries, they usually create draft dashboards directly in Databricks.
These dashboards are used internally to share findings, discuss results with colleagues, and iterate quickly.

At this stage, dashboards are exploratory and collaborative, not final products.


### 4. Production Reporting with Power BI

When the queries and dashboards consistently answer the business questions and the results look correct and stable, analysts move to Power BI. 
There, they build standard reports designed for a large audience of standard users.

These reports are polished, governed, and rolled out across the organization.


### 5. AI and Natural Language Analytics

A newer and powerful step is AI. Analysts can expose relevant, trusted datasets to AI tools like Genie.
This allows standard users to ask questions using natural language instead of SQL, directly on top of governed data.

This reduces dependency on analysts for every question and makes analytics more accessible.


## Key Takeaway

Databricks enables data analysts to move from exploration to collaboration, from draft insights to enterprise reporting, and 
now even to AI-driven analytics, all on top of the same trusted data foundation.

#
</details>
<!----------  How Data Analysts Work Using Databricks ----------------->

## 2.4 Project: Data Analytics using Databricks i.e. Assignment

<details>
  <summary>  Expand  </summary>

In this project, you will build a **complete Data Lakehouse** from scratch using **Databricks** and the **Medallion Architecture**.

You will start with raw data and step by step transform it into clean, reliable, and business-ready datasets using the **Bronze, Silver, and Gold** 
layers. This is how modern data platforms are built in real companies.

You won’t just write code. You will design architecture, improve data quality, model data for analytics, and automate everything with pipelines and jobs.

By the end, you will have a production-style Lakehouse you can confidently showcase and extend further.

Let’s build it the right way.

#### Project Phases & Guide

<details>
  <summary> <b> Phase1 - Project Initialization </b> </summary>

<br/>

> Goal: Preparation steps before building the Lakehouse.
 
- [ ]  **Design the architecture**
    - [ ]  Read Databricks reference for the project → [**LINK**](https://docs.databricks.com/aws/en/lakehouse/medallion)
    - [ ]  Draw the data lakehouse architecture using draw.io or similar → [**LINK**](https://www.drawio.com/)
- [ ]  **Create GitHub repository** → [**LINK**](https://github.com/)
- [ ]  **Connect GitHub to Databricks using URL (**Workspace → Create → Git Folder)
- [ ]  **Create Lakehouse schemas (Unity Catalog) using**UI or SQL**:** `bronze` `silver` `gold`**
- [ ]  **Create a volume inside bronze schema** `raw_sources`
- [ ]  Upload the 6 CSV files from engineering folder into the Bronze volume → [**LINK**]()

> Result: Project is ready to start building Bronze, Silver, and Gold layers.

# 
</details>

<details>
  <summary> <b> Phase2 - Building Bronze Layer </b> </summary>

<br/>

> Goal: Build the Bronze layer by ingesting all raw CSV files into Delta tables without any kind of transformations.


- [ ]  Create a folder in the repository called `bronze` to store all scripts inside it
- [ ]  **Create Bronze notebook**
- [ ]  **Initial ingestion (manual)** For each of the 6 CSV files:
    - [ ]  Read the CSV into a DataFrame
    - [ ]  Write the DataFrame to a table in the Bronze schema using overwrite mode, and use a source-system prefix in the table name
           for example `erp_` or `crm_`) to clearly identify where the data comes from.
    - [ ]  Run the script and query the bronze table to verify it is loaded correctly
- [ ]  Run the whole notebook to see if everything works successfully.
- [ ]  Commit & Push your changes to the GitHub repository

**Bonus Advanced Task**

**Code review &** Identify repeated logic

- Create a dictionary to store file paths and table names
- Loop through the dictionary to ingest all files

> Result: All 6 raw source files are ingested into dedicated Bronze tables with no transformations applied.

# 
</details>

<details>
  <summary> <b> Phase3 - Building Silver Layer </b> </summary>

<br/>

>  Goal: It is time to clean and transform our bronze data and load the clean results into silver layer.
> This is usually the most time consuming phase of the project and the fun part!

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


**Bonus Advanced Task**

- Review all 6 Silver notebooks and identify repeated code
- Reduce repetition by:
    - Using a config file with loops, or
    - Creating reusable Python functions

**Result:** Cleaner, scalable code and a strong step toward senior data engineering.

> Result: All Bronze tables are transformed into analytics-ready Silver tables with validated data quality and standardized structure.

# 
</details>

<details>
  <summary> <b> Phase4 - Building Gold Layer </b> </summary>

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


> Result: All Silver tables are transformed into business-ready Gold tables designed for analytics and reporting.

# 
</details>

<details>
  <summary> <b> Phase5 - Building the Pipeline </b> </summary>

<br/>

> Goal: Automate the end-to-end Lakehouse flow so data is processed reliably from Bronze to Silver to Gold.


### Current Setup

- 1 Bronze notebook
- 6 Silver transformation notebooks
- 3 Gold notebooks (dimensions and facts)

To run each layer cleanly, we introduce **orchestration notebooks** that act as single entry points.


- [ ]  **Create Orchestration Notebooks**
    - [ ]  Silver orchestration: Create one Silver orchestration notebook that triggers all 6 Silver notebooks in sequence.
           Use **`dbutils.notebook.run`** to run notebookes.
    - [ ]  Silver orchestration: Create one Gold orchestration notebook that triggers all 6 Silver notebooks in sequence.
           Use **`dbutils.notebook.run`** to run notebookes.


- [ ]  **Create a Databricks Job**
    - [ ]  Go to **Databricks → Jobs & Pipelines** then create Create a new Job
    - [ ]  Create a new Job and Give it a clear name, for example: `loading_bike_data_lakehouse`
    - [ ]  Add three Tasks:
        
        <img width="881" height="170" alt="image" src="https://github.com/user-attachments/assets/47ef2b39-5a76-4c46-8566-4215607db127" />
        
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




#
</details>
<!----------  Project: Data Analytics using Databricks i.e. Assignment ----------------->

### Congratulations

You’ve just built a complete **Data Lakehouse**.

This is **Lakehouse 1.0** and it represents the core foundation of real data engineering work.


### Portfolio & Career Tip

You can confidently use this project as a **portfolio project**. You have my permission to do so.

If you share it on **GitHub** or **LinkedIn**, I would appreciate it if you give credit to the original source.

If you are **preparing for job interviews**, make sure you practice explaining this project:

- Why you designed the Lakehouse this way
- How data flows from Bronze to Silver to Gold
- How you ensured data quality and scalability
- How you automated everything with pipelines

Being able to clearly explain this project can be a **strong differentiator** and may be one of the reasons a company decides to hire you.

This is real, practical data engineering work.



### Next Steps!

From here, you can take your Lakehouse to the next level by adding more advanced capabilities, such as:

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

Strong foundations first, then continuous improvement.
