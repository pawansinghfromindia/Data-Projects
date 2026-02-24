# Data and Data Literacy

## What Data Team does ? 

<details>
  <summary> <b> Data Team </b> </summary>

- What's a data analyst ? <br/>
You Answer business Quetions using Data ! <br/>
Bridge between raw data and Real Business Decisions

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/8eae5dd6-0a7e-4787-956f-c809eb3e4497" />

- What is the role of a data analysts in a data team ? <br/>
In a company we have manager, stakeholders, project leads and their whole job is to make smart decisions by asking critical questions. <br/>

`Que : Which region is underperforming ?` <br/>
`Que : Why're profits down ?` <br/>
`Que : Should we invest here ?` <br/>

Basically they have many challenges in company and they need quick and smart decisions. <br/>
Without using data, they're just guessing, relying on opinions, gut feelings and outdated information left, right, top, down.

> Without **Data**, you're just another person with an opinion ~ William Edwards Deming

If your decision process is based on Opinions, this has high chance to lead to Confusion, Waste of resources and making bad decisions for business.

So, Business decisions work on data. In companies data are scattered everwhere like data is stored in many databases, spreadsheets files or APIs.
Managers don't have time and skills as well to dive into all those different places. So they hires experts specialist Data Analysts.

Query different databases, Spreadsheets data, APIs data, Get the data from everywhere and All those data are messy, so need to be cleaned and structured. 
So do data cleansing, oraganizing data, doing calculations, transformations to get the data ready to answer the business questions.

Once you finding something meaning in data, you start turning the data into insights into a visual reports. bcuz it is way easier to communicate the result 
to stakeholders and business managers using visuals. So once you're ready with data insights, you present it to business managers and stakeholders as a 
**Story** using reports and visuals.

Now Managers got the **Facts** and this time they have answers to the questions using data. Now they're more confident and make better and smarter
decisions for the business.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/d44d40c0-0ecd-4167-84b8-2cb887ec2a92" />


#
</details>



<details>
  <summary> <b> The world that is driven by Data </b> </summary>

### ✨ Teams who works on Data

**1. `Data Architect + Data Engineer`**  works together **to build Data System**

> Data Architect design the data system | Discovering and building blueprint

> Data Engineer builds pipeline and data sytem  so Building and Making things live


**2. `Data Analyst + BI Developers`** works together **to build Reporting System**

> Data Analyst build first version of report | Discovering and building blueprint

> BI Developer brings reports and dashboard into scalable and productive reporting system

**3. `Data Scientist + ML Engineer`** works together **to build an Advanced Analytical System**

> Data Scientist experimenting and training the first version of model | Discovering and building blueprint

> ML Engineers brings the model and deploy it into productive system and offering the results in different services.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/45f5bcca-d855-4cd6-9ac2-2e004c82d955" />


#
</details>

## Data Science 
<!--------------------------------->
<details>
  <summary> <b> What is Data Science ? </b> </summary>

<br/>

**Data Analyst** can only answer business questions that is based on data of **current situation/scenario or history/past scenario**, **NOT FUTURE PREDICTIONS**

Data Analyst can't making something very intelligent in order to predict things in future. Exactly for these scenario where we get more advanced and complex business questions, there we need a Data Expert, Data Specialist in order to solve this problem. Here comes the **Data Scientist**


If the business question is all about the **current situation(Present) or past situation(Past History)** then we need a **Data Analyst** in order to do something called ***Descriptive Analysis*** 

But when Business question is about **future predictions(Future)** then we need a **Data Scientist** in order to do ***Predictive Analysis***


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/08f05f34-fee6-4551-aa39-ef52b8ad486b" />

<br/>

### Descriptive Analysis vs Predictive Analysis

Predictive Analysis is way more complex than Descriptive Analyis.

For Predictive Analysis, we need Intelligence System. So using tools like PowerBI, Tableau will not help here.

Data Scientist solve this problem. but It needs huge amount of data, everything about the custumers that company generates 

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/8605ea37-14cc-44fa-ab34-7ffe49eda525" />

#### Phase 1. 

**Collect the Data** i.e. Data Extraction from different Data Sources

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/86b94ecf-b8a7-4d8b-8850-cac0747b7f3a" />


#### Phase 2.

**Data Cleansing and Data Preparations**
- Merging all those files through JOINs
- Standard Formating
- Replacing NULLs
- Correct the Data Types
- Remove Duplicates
- Remove useless columns 

Not all companies have the below luxury of having Data Engineers and Data Architect Team.
<br/>
<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/91f89d88-2873-4670-958e-8783bf610a7c" />
<br/>

So, With Data Cleansing and Data Preparation we have a perfect dataset that is cleaned and structured and ready for the next step.
Hold on this can't be directly feed to ML Models to predicts the future. 

Before that we have to explore and understand the data i.e. known as Exploratory Data Analysis which is next step.

#### Phase 3.

**Data Exploration** Understand the data which is known as **EDA = Exploratory Data Analysis**

- How Data is distributed ?
- How we can cluster or catagorized customers ?
- Relationship between different measures

All of this happens in Notebook environment on data by Data Scientist. So, It is basically a thinking phase where Data Sceintist look at data ask questions and make notes in order to understand the data. 

Once we have good feeling and confident about data. We move to next step.

Yes we have cleaned and prepared data but the Data itself is **Raw data**. 

**Raw data** means It does not yet like **Information**

We can make/create extra columns(measures/attributes) derive from existing columns. meaning deriving information from the raw data.

|   Raw data  | Raw data    | Features          |
|-------------|-------------|-------------------|
| customer_id | signUp_date | `day_since_signUp`|
| 101         | 2026-01-31  |   100             |
| 102         | 2026-02-20  |   25              |
| 103         | 2026-05-03  |   5               |

- day_since_signUp, Total_spentByCustomer, avg_sessionDuration, etc etc
  
- Basically we're deriving smart columns that doesn't exist on original dataset (raw data).
- Of course, these are not easy to create these smart columns, It requires domain or business knowledge and insights this is known as **Feature Engineering**


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/26f43167-b7dc-4f2d-91d2-d011d5db76fd" />


#### Phase 4.

**Feature Engineering**

> **The process of deriving the useful information from raw data to improve model performance.**

With that we have everything, we're ready to ML.

Step 1 : Split our data into two sets
1. Training Set : from where AI/ML Model is going to learn
2. Test Set : in order to test the performance of output of Model. It is small dataset.

If we train and test on the same dataset, that means you're cheating. That's why we split the dataset.

Step 2. Choose/Pick an algorithm, right one to solve the right problem

Algorithms are set of mathematical steps that describe how to learn from data

Step 3. Once you pick the algorithms, apply it on training dataset.

Combining mathematics with data

Algorithms will go through all of our dataset and start learning from it. This is what we call **Training a model**.

Model is going to start learning patterns. It is going to find connections and relationship between data and start adjusting itself to minimize errors.

At the end, we get something very powerful called a **Trained Model**.

Now we could use this trained model in order to do predictions for new data. 

Output of this trained model will be predictions.

like customers is likely to stay or no this customer might leave soon.

Based on that we label each customer. 

So, Now we have knowledge which needs to be shared to business users.

So, we import everything data and predictions in PowerBI or Tableau and build a visual in order to show a final results. 

It is always better to communicate with business users using PI tools bcuz they are very friendly compared to Visual inside notebook.

Now we go and present result for Business Users and now they have more understanding about what could happen in the future. 

Now Business users will plan action based on that insights.
- they will launch retention campaign for customers
- sends new offers to risky customers
- Reach customers directly

This is the moment for data scientist, He/She can see that He/She is adding value to the company. Not just building fancy model bcuz they could. Instead they're really helping business.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/862f4cf4-e61a-4f67-a3ad-2b088c232c73" />


<br/>

This sounds like a happy ending but is it?

Sadly, we're not done yet.

Whatever we did, We did it manully as well as It's just a proto-typing. 

This is not one time activity, We have to continue those stuffs. 

Of course sources will keep generating new data everyday, may be they're useful information so we have to train the Model again.
So, We have to automate everything and make deployment.

**Model Deployment**

> The process of putting a trained model into production so it can make predictions on real-world data. So we have to put it in real automated system.

Of course this system not run locally on notebook. We have to run it on servers. e.g. Cloud. 

We can use APIs in order to connect internal applications and system in the company to the Model in order to show those scores/predictions at the frontend.

So, the whole is all about to bring everything that we have done manually into  notebook and to deploy it to professional platform that is fully automated, scalable, highly available and secure, connectable to different application at the business. In companies we have **ML Engineers and ML Ops** they does these stuffs, 

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/bdb85e2f-d839-47af-9798-f78f0f175ad1" />

#
</details>




<!--------------------------------->
<details>
  <summary> <b> Classical Machine Learning Process </b> </summary>

- Collecting the data
- Cleaning the data, Preparaing the data
- Data Exploration
- Training the Model
- Deploying into Cloud for production

All of these are known as Classical ML Process.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/70b712c4-39c3-4107-9293-61db6de04141" />


<br/>

Bcuz we're now in 2026, We have entered in world of **Pre-trained Models**

**Pre-trained Models** especially LLM(Large Language Models) like ChatGPT, Claude, Gemini etc they are already trained on massive amount of data on the internet on public data like text, website, documents, etc.

#
</details>


<!--------------------------------->
<details>
  <summary> <b> Pre-trained LLMs </b> </summary>

Bcuz we're now in 2026, We have entered in world of **Pre-trained Models**

**Pre-trained Models** especially LLM(Large Language Models) like ChatGPT, Claude, Gemini etc they are already trained on massive amount of data on the internet on public data like text, website, documents, etc.

They understand Language, Context, reasoning. This is crazy bcuz what we have before is always had to train our models. But these days everything is prepared for us already trained on huge data, so we have advanced model.

You might think that those pre-trained model. So isn't they will be very generic ?

Well that's true but most of the Pre-trained models, they allows us to do fine tunning. 
So, we can pick one of those pre-trained model and train it or we can say fine-tune it with the company data to make it more advanced and smart with your domain(business)

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/f4b34070-8435-40fa-9f52-a782f4520832" />

Why we need all those LLM ?

Think like this if each time stackholders/business users/managers needs a new report or new information from model.
Isn't is bad that each time you jump and get the data from Model, put it in PowerBI and present it for stakeholder/Users. This is really slow and hectic.

Instead of doing that we let the Stakeholders/Business Users having chat with the model and users could start conversation like why are customer leaving, summarize all the feedback from cancelled users etc.

Basically Stakeholder/Business users can chat with the model and this is way better than each time waiting for PowerBI Report and for this we could use those pre-tarined model the LLMs.

#
</details>


<!--------------------------------->
<details>
  <summary> <b> Data Scientists Job is danger ? </b> </summary>

<br/>

Scary this is If we have all those Pre-trained Models (LLMs) Why do we have even Data Scientist.

Yes, It is understandable that we need Data Scientists in order to train models. But if we have pre-trained model why do we need them.

Whatever we discuss till now, they are Industrial Data Scientist. 

BUT <br/>
Data Scientists who trained those Pre-trained models are Researchers who works in massive engineering teams of big tech giant companies like Google, OpenAI, Anthropic, Meta, Amazon and they do amazing work of bringing those pre-trained models in the market.

But we still need those Industrial Data Scientists for one important reason is All those LLMs pre-trained models. They're trained on public data and most of the companies they don't bring the data in public they internally. They all have internal confidential and secure secret data. So, there will be a lot of business problems are there that depends on the company's data.

Company protects their data, so we ended up in a situation where companies need to hire data scientists in the industry. So Industrial data scientists they either fine-tuned the pre-trained models or in many scenarios they do have to train the Model from scratch to be specific to a company domain.

That's why Data Scientists in the industry is still relevant. They have a lot of things to do bcuz they suddenly exposed to all those pre-trained new models.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/b6e745d4-f3c9-4d6c-8568-73b9d3a6ffed" />


#
</details>


<!--------------------------------->
<details>
  <summary> <b> AI Agents and Super AI Agents</b> </summary>

<br/>

We have come so far in the AI/ML field is that we have something called **AI Agents** 

We are now beyond to having only a quick conversation between Business Users and the pre-trained LLMs 

Now users can ask Model many stuffs beyond to just having conversation. Like

- How many customers did left last year.

Basically now we have one AI Agent that is using the pre-trained Model to convert the text or questions asked by business users to SQL Query which will direcly goes/interact with the database and fetch the data and show the result as visualization to end-users.

- Where I can find the customer data in which system in which application.

For this scenarios we can another AI Agent that could use another pre-trained model that is specialized in scanning the document. This time we don't need the company data, we need documentation of company.

Now if the customer ask something about future, predictions and all stuffs like how many customers will leave next year, then we can use an **AI Agent** that connects to our Model that we trained from scratch.

So, We have a lot of AI Agents that are connecting to different Models for different data and data-sources.

So, Of course, We have to orchestrate all those stuffs and connect everything and that's why we're going to have like a manager AI Agent that is a top level agent, which get the prompt from users and decide which agent and which model are involve and then respond back to the users by using actions like send emails. 

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/2d3a50c4-3773-46e2-944b-f1c305643c42" />

<br/>


### What is AI good at ?

- Pattern recognition
- Automation
- Repetitive tasks

Databricks, Snoflakes platforms are making everything just drag and drop for everything.

Now Business Users can now query data in plain English and get accurate result automatically based on AI Agents which are trained on the same datasets. So, No Data Analyst, No Data Engineers need to write query and translate it to business users.

#
</details>


## Data Engineering 
<!--------------------------------->
<details>
  <summary> <b> What is Data Engineering ? </b> </summary>

<br/>

Que : What **Data Engineers do** ? <br/>
Ans : What Data Engineers do is : 
- [ ] Data Engineers don't build Apps.
- [ ] Data Engineers don't build Software.
- [x] Data Engineers do just **build Data Pipelines** <br/>
      Pipeline that pulls the data, clean it, transform it, load it and keep running everyday.

### Role of Data Engineer
- Building ETL pipelines
- Writing SQL transformation
- Cleaning Data
- Moving data from point A to point B
- Scheduling jobs
- Monitoring pipelines


**Data Engineering** is like engine room behind every data driven company. <br/>
And **Data Engineers** are the one who do move the data from source to target, transform and store massive amount of data. <br/>

They do not build shiny dashboard or front-end, As a Data Engineer, you work behind the scene where you're exposed to hidden complex important data of the company and your job is to bring it to a suitable platform so that other can do smart thing with data like answer business questions.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/b810edb4-7747-4342-a2b0-ac38bc0dc3a6" />


#
</details>


<!--------------------------------->
<details>
  <summary> <b> What is a Data Pipeline ? </b> </summary>

<br/>

At a very high level, a data pipeline is just a flow where data comes in from the data sources and they go through few transformation steps where we clean, prepare and enhance the data, once data is ready we load the data to the target table.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/2e4c243d-e0cd-4988-9c05-5a08fc9210f0" />

<br/>
<br/>

It is not a rocket science, as a data engineer. We have to build only this data pipeline and in order to build this we use Python and then other people (business users) start using this prepared data in order to build **analytical use cases** like dashboard reporting or **AI/ML use cases** like training the AI Model.

So this is the big picture of data-pipeline.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/13f5ff50-93be-4ecd-9e7c-ca1e0483d1c8" />

<br/>

### Data Sources

The sources of data could be different technologies like :
Data from `Databases`, Data Stored in `files`, May be data is provided as a stream using `Kafka`, Data could be live in APIs so, `API` could be data source.

- [x] **1. `Databases`** : Structured data like transaction data, Customer records, ERP systems

- [x] **2. `Flat files`** : Data exports, Logs, Third-party data feeds in CSV, Excel, JSON, XML

- [x] **3. `APIs` and `Web Services`** : Semi-structured data(often real-time) like Weather data, Payment gateways, Social media data

- [x] **4. `Cloud storage` and `data lakes`** : Amazon S3, Azure Blob Storage, Google Cloud Storage<br/>
    Use cases : Big data pipelines, Log archives, Machine learning datasets

- [x] **5. `Streaming sources`** : Apache Kafka, IoT sensors, Clickstream data <br/>
    Use cases : Real-time analytics, Fraud detection, Monitoring systems

So, we can have different sources of data.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/fdf2ee84-649a-46cd-8c69-042e13ed6727" />



#
</details>

<!--------------------------------->
<details>
  <summary> Step 1.<b> Extract and Load </b> </summary>

The very first step in our data-pipeline is **Extract and Load** where everything starts.

It is very simple, in this step we have to connect to the data sources and start reading the data and loading it into our system.

Here, We're just taking one copy of data from sources and putting it in our system.  <br/>
Nothing big, Nothing smart, No complex thing, No transformation.

In order to do this step in data-pipeline, we as data engineer write `python` scripts/codes.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/f26b9373-4ecb-4b8b-8921-165cea07997c" />


#
</details>


<!--------------------------------->
<details>
  <summary> Step 2.<b> Transformation (Data Cleansing, Data Preparation) </b> </summary>

This step is all about **cleaning up data, enhancing it and preparing it** for the next step.

We take the raw data, start transforming it like :
- Handling Missing Values i.e. Replacing NULLs
- Removing Duplicates
- Fixing the data type
- Handling the dates, text
- Standardizing the format like Renaming table, columns

Basically we're doing data cleansing and data enhancement on top of raw data.

In order to so transformations (Data Cleansing and Data Preparation), we use `python` main script as well as we can also write add-on like creating a config file, a logging, a data quality check files and so on.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/940956cd-aaeb-4e6b-bd77-d1da05b0b92b" />

<br/>
<br/>

So far what we have done is, The 1st step we just brough the data in and in 2nd step just clean up data and 3rd and last step is do transformtion where apply business logic.

#
</details>

<!--------------------------------->
<details>
  <summary> Step 3.<b> Transformation (Business Logic) </b> </summary>

The last step in our data-pipeline is Transformations(Business rules and logics). 

We take the data that we have cleaned and prepared and start doing things like :
- Joining the Data together (`JOIN`, `UNION`, `MERGE`)
- Doing data aggregations (`COUNT`, `SUM`, `AVG`, `MAX`, `MIN`)
- Start applying the business logic i.e. Business Transformation

Basically we are tranforming the data by applying the business logic to prepare a final data product for Data Analytics to answer the business questions as well as for AI/ML use cases.

In order to do that we write main `python` script and we also have some add-ons files like config files, logging and data-quality checks files

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/e59b7fbc-26d9-4b7a-9ee4-568a477b5d06" />


### Summary of Data-Pipeline
As Data Engineer, our job is not that hard, we just have to build the data-pipeline where it has mainly 3 steps, **Extract and Load** where we bring the data from sources into our system without applying any transformation or logic and next is take the raw data and start **Transformations(Data Cleansing and Data Preparation)** to enhance and prepare the data for last step **Transformation(Business Logic)** where we transform the data by applying the business logic and prepare a final product for Analytics and AI/ML use cases. 

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/f5f9e35a-935e-452a-bc21-8f0e55b1ed79" />


#
</details>


## Business Intelligence (BI)
<!--------------------------------->
<details>
  <summary> <b> What is Business Intelligence Power BI</b> </summary>

In every industry and business, everyone(Managers, Stakeholders, Project Lead) at the top have the same mission.
All of them need to make smart decisions and that too correct and fast to grow and make profit for oragnizations/company.

Business Question like :
- Which region falling behind?
- Why profits are dropping last month, years?
- Where to invest(put) money next ?
- Why customers leaving ?

All of these are critical business questions and they need answers. <br/>
In order to get answers, if they don't have data then only they can guess based on opinions and gut feelings in order to finding the answer.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/6a568f3a-c817-4c6e-b84b-2ba97a377c4b" />

<br/>

<br/>

> **without Data you are just another person with opinion**. - Willian Edwards Deming

That's why most of the companies, try to find the answers of business questions using the companies data. <br/>
There needs a **Data Analyst** in order to find the answers of business questions using the data. <br/>
To do this, companies need a tool, if not then they use spreadsheet(Excel file).

At the end present the business answers using numbers, charts in visuals by telling the stories.
and manager and stakeholders use that in order to make critical business decisions.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/08a7c87e-5611-4605-811d-bf146b72e5b2" />


<br/>

In real world this is not how things work. <br/>

**Drawback** 
- [x] 1. Manual Work
- [x] 2. Outdated
- [x] 3. No Refresh
- [x] 4. Not handle Big Data (Huge amount of data)
- [x] 5. No supports of Modern Technology like cloud, APIs, Stream Kafka
- [x] 6. Can't collaborate as team grows to handle big data
- [x] 7. Data Security concerns
- [x] 8. No Access Control over data
- [x] 9. Chaos/Disaster like No single point of truth for data


Bcuz entire process is manual like connecting to the sources, exporting files, merging sheets, cleaning rows. <br/>
It sounds easy but it's really painful consume times like weeks or months sometimes. <br/>
So, It might be lead to old data which lead to bad decisions by manager/stakeholders which cost the companies. 


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/2ca80325-533c-409a-8303-5d7731d89cd3" />


### Solution of above chaos 

**Companies can't rely on Spreadsheet(Excel file) to do analysis anymore** <br/>
Instead companies need a standard process, a platform to do whole things in one place and we call this standard process and sytem as **Business Intelligence (BI)**  


A Business Intelligence is the whole process of working with data.
- Collecting the data from sources
- Cleaning up the data
- Preparing and organizing it
- Turn the data into visuals so that people can understand what's going on and make better decisions

<img width="467" height="270" alt="image" src="https://github.com/user-attachments/assets/724bcf28-0bb5-4c16-9e3e-d717440ac987" />

<br/>

So, Basically BI is the full workflow from start to finish.
BI is not just making visuals with numbers and charts, It is way more than that.

Of Course, we need a tool or platform in order to do Business Intelligence. We have 2 very famous platforms
1. **PowerBI**
2. **tableau**

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/321c1e7c-5408-4538-bef5-22724bce7cac" />



#
</details>


<!--------------------------------->
<details>
  <summary> <b> PowerBI vs Tableau </b> </summary>

### History of **PowerBI**

PowerBI didn't start as a giant platform.

Everythings begins inside the excel.

Microsoft has tools like **Power Query** and **Power Pivot** hidden inside excel. These tools were very powerful but the thing was Excel itself was not able to handle modern big data.

At the same time other platforms like **Tableau** started becoming very popular.  

<img width="350" height="200" alt="image" src="https://github.com/user-attachments/assets/7fc98318-edc4-4088-9511-34106d786f8c" />


<br/>

As **Tableau** become popular that's bcuz It offers a clear and easy way to do **Data Visualization**. That's microsoft understood that they need compeletely new they can't keep adding stuffs to Excel. So they started taking strong part of Excel and turn them into a new product focus on **Data Analysis** and that idea become **PowerBI** in 2015.

Since 2015 until now Microsoft keep pushing and improving the PowerBI month after month with better visuals, more connectors, improving the performance, deep integration of PowerBI with Microsoft Ecosystem.

They introduced **Microsoft Fabric** and **Copilot** in PowerBI. So over the time **PowerBI** grew into a full Business Intelligence Platform or Data Analytics Platform.

Now PowerBI became one of the main competitor for Tableau. Both of them are the top tools in the world of Business Intelligence and Data Analyics.

<br/>

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/b1eaa75e-30d1-4965-999e-ca4123301f12" />


#
</details>



<!--------------------------------->
<details>
  <summary> <b> PowerBI </b> </summary>


We have another name for PowerBI that is **Data Visualization Tool**.

It is a process of turning raw data and boring numbers into visuals and charts like bar, line, pie, heat maps etc just to make it easier for human to understand the complex raw data instantly.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/19b632d7-c321-40b8-986e-ca6bfa78f84c" />


Bcuz Humans are visual creatures. If we see a picture of a tree we understand right away. But if we read the word tree, human brain first process it and then turn it into visuals. So visuals skips the extra step of reading which makes it easier for human brain.

So Visuals are processed way faster than reading a text or looking to numbers. Not only that Human brains remember it longer.
We keep small part of what we hear, a bit more what we read but most of what we see.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/df163e6b-1638-4216-98bf-4e187d5633b3" />



This is the power of visual and Data Visualization are very powerful bcuz we understand the information faster, see the pattern, problems instantly.
We can use visual to explain our ideas. We can tell a story. With that others can make better decisions.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/b1b19a0b-07fe-4e38-b19a-19f5a16c267c" />


Exactly for that tools like PowerBI focuses on data visualization.

#
</details>

<!--------------------------------->
<details>
  <summary> <b> What is inside PowerBI ? How it actually works ?  </b> </summary>

<br/>

Once we Connect the source data to PowerBI.

PowerBI is divided into 5 components and each of them has its own clear job.

**1. Power Query**

➞ This is where we clean up data, remove mistakes, duplicates, fix format etc

- [x] Remove Nulls,
- [x] Remove duplicates
- [x] Fix the format
- [x] Rename columns

> **Power Query is all about preparing the data**.

**2. Data Modeling**

➞  Once everything is cleared, it's time to structure and organize our data.

> Data Modeling is all about how we connect our tables to each other.

This is every important to make everything accurate, organized and fast.

**3. DAX**

➞ DAX (Data Analysis Expressions) is a formula language in Power BI used to create custom calculations for measures, calculated columns, and tables.  It enables advanced data analysis beyond basic aggregations.

> **DAX is all about using calculations and maths in order to build the business logic that we need for the next step**.

Everything (Power Query, Data Modeling, DAX) done so far is like hidden. It is in background of the PowerBI.

Now, It's first time we're going to build something that end users are going to see Visuals.

**4. Visuals**

➞ Here we're going to build all those charts, big numbers, tables, filters, slicer everything just in order to tell stories using data.

> **Visuals is all about building reports and dashboard**.

Once everything is ready we go to the last component in order to share and publish what we have built.


**5. Publish and Share**

➞ At the end what we have build we publish it or share it so that people(business users) can view report and dashboard, interact with it and make smart business decisions based on that.

> **Publish is all about sharing our created visuals to business users to consume**

### Summary of PowerBI

These are the 5 block/components inside PowerBI that we use in order to build something in PowerBI.

It looks like a process, a simple pipeline.

Bring the data in, Clean it, Module it, Organize it, Visualize it and at the end share it, publish it.

We can do whole thing in just one platform PowerBI.

<img width="600" height="350" alt="image" src="https://github.com/user-attachments/assets/24346e3c-c6a5-469d-8ec9-e17f1b1711ba" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> PowerBI Ecosystem </b> </summary>

PowerBI in itself is not just one thing rather it is multiple things.

Microsoft offers multiple tools and each of them has its own job.

### 1. PowerBI Desktop App

This is the app that we install locally on our PC.

Not meant for MacOS or Linux unless you're using some extra workaround like Window Virtual Machine.

PowerBI Desktop is where we spent most of our time building things.

It is basically the engine of PowerBI. Everything we do here like Power Query, Data Moduling, DAX, Visuals all of these whole processess we do inside the PowerBI Desktop.

Everything the data, the modules, the reports, the visuals are going to be stored in one single file (PowerBI file `.pbix`) locally on our PC.

We can share this PowerBI file `.pbix` directly with others .

<img width="600" height="350" alt="image" src="https://github.com/user-attachments/assets/accc355e-994e-4205-9f8f-807c6f711191" />

<br/>
<br/>

But in companies, we don't share the PowerBI file directly instead we publish everything that we have build to a new tool **PowerBI Service**

### 2. PowerBI Service

So we publish everything that we have build on our **PowerBI Desktop App** to a new tool **PowerBI Service**.

Once we publish our report or dashboard from **PowerBI Desktop** to the **PowerBI Service**, Now all those reports/dashboard will be live there.

Now End users, Consumers (Business Users) can access all the reports and dashboard that are published is by just opening it in Browsers and start viewing and interact with reports/dashboard like start filtering things, checking numbers and see the visuals.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/d500fe44-e278-432f-b9d7-c3f4e16f3ed4" />

<br/>
<br/>

Of course, if there are top managers who don't have time to open their laptop, No problem!
We have another tool **PowerBI Mobile App**. They can install it and start interacting with reports/dashboard through PowerBI Mobile App.

### 3. PowerBI Mobile

Of course, if there are top managers who don't have time to open their laptop, No problem! 

**PowerBI Mobile App** is there download install it on your Mobile Phone in order to connect to report/dashboard that are published on PowerBI Services(Cloud).

Now you can start interacting with the reports/dashboards.



<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/9303fbf6-c111-487d-af61-c73d3c82d2f4" />

### Summary of PowerBI Ecosystem

A **PowerBI Desktop App**, where we build things, **PowerBI Service**, a cloud service where we host, publish and share reports/dashboards to easily interact with any Web Browser, last is **PowerBI Mobile App** to interact with published reports/dashboard through mobile phones/tablet. 


PowerBI is not only limited to **Data Analyst, BI Developers**.

**Data Engineers** who build data pipelines, they can also use PowerBI in order to make dashboard to monitor the data system health like check Data Quality issue and make sure whether everything is loaded correctly the way it should.
So Data Engineers use PowerBI to monitor internally the whole system.

**Data Scientists** also use PowerBI in order to share their work with non-tech business users what they have built models, predictions and ML solutions. Bcuz they can't share noteboks and code. So they use PowerBI to share the work bcuz it is simple and easy for bisiness users.
PowerBI is easy way to explain the complex thing.

**Business Analysts** also ended up using PowerBI like what happened, why it happened and what should happen next. So they use it for business insights for conversation and discussions.

**People use it for Personal Work**
Not only for Work, a lot of people use PowerBI for personal life at home. Like they use it in order to track their spending, Budgeting, for investement.

Anytime If you have numbers, and you would like to make visuals you can use powerBI.
Example : people use it for Youtube stuffs to analyze and track things.

It just works for everyone.

<img width="600" height="350" alt="image" src="https://github.com/user-attachments/assets/17c50751-fb21-45e0-b7e2-1e473d013e7e" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> War/Debate of PowerBI vs Tableau </b> </summary>


### Endless war of which BI tool is better PowerBI or Tableau

Both are good!

We can utilize both of them in a project at the same time.

**Why PowerBI ?**

Why some project teams tends to use PowerBI instead of Tableau is bcuz :

1. It fits your daily work tools like Microsoft Products like Outlook, Teams, Excel, PowePoint, SharePoint.
So, PowerBI feels natural bcuz It fits looks like PowerPoint, Excel etc.
It is already connected to all those tools without any extra steps.

2. It is very easy to switch from Excel to PowerBI bcuz you already know DAX. The interface of PowerBI looks like Excel and charts and dashboard looks similar. We have already a background to switch to PowerBI.

3. PowerBI is more affordable. It costs less than other tools. All the companies trying to cut cost. One of the major cost in each budget of company is actually licenses. So this is the winning factor why companies utilize PowerBI

4. Inside PowerBI a lot of things like Data Cleanup and Data Preparation using Power Query. Unlike Tableau which offer a second tool like Tableau Prep in order to prepare the data. But with PowerBI Desktop we have everything in one place which makes easier not have to jump between the tools to do the whole process.

5. Data Modeling inside PowerBI is really strong. There are a lot of features and advanced stuffs that we can do as we moduling the data compared to Tableau which is very limited on how we build the Data Model which is a clear win for PowerBI. Inside PowerBI we can make strong data model which will be flexible and fast with PowerBI. 

6. Microsoft focuses on these products like they release new updates every months by adding new features, new visuals, new connectors. So PowerBI Tool is keep growing really very fast.

These are the reasons why we use PowerBI over Tableau. <br/>
Major reasons are It is cheaper than other tools, Intergrated everywhere in Microsoft Ecosystem, Familiar Interfaces to Excel. <br/>
Hence PowerBI is very popular and widely used.

<img width="600" height="350" alt="image" src="https://github.com/user-attachments/assets/434cbb9f-0299-40af-8474-a4c8db898f59" />


### PowerBI is great, but not perfect !

There are some scenarios where **PowerBI** is limited compared to other tools like **Tableau**

**Drawbacks of PowerBI**

1. We can't use for Very complex visuals

If you're building operational reports where you have some basic charts - a line a bar, a pie, some tables, filters, slicers then PowerBI is more than enough.

But If things get advanced and complex like If you're **data scientist** and making `dot plot` or some advanced data insights about data, It is way easier to use Tableau which is also faster.

2. There are limitations in PowerBI, If you're using scattered chart in PowerBI, you're limited only to few thousands of data points which is disaster if you have a lot of data so find the outliers of 1000s of data-point is not possible in PowerBI. This is where Tableau comes where it doesn't forced any limitations of data-points

3. We can't use PowerBI Desktop for MacOS users, you must need to have virtual Window Machine in order to work with PowerBI. 


<img width="600" height="350" alt="image" src="https://github.com/user-attachments/assets/5919274f-4f24-4b84-8419-6d489b095d0f" />



These are the limitations of PowerBI.

This is the reason we sometime use both PowerBI and Tableau in a project at the same time.

- For Basic Operational Reports and Standard Reports that goes to managers and leaders. We utilize PowerBI which is more than enough. 80% of requirements of reports fits into those 2 categories (Basic Operational Reports and Standard Reports).

- Only for complex or advanced analytics that are usually prepared by advanced Data Analysts or Data Scientists. We use Tableau bcuz It is faster for big data as well as offers to create highly customized charts. Not everyone use it 

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/f15a1ddb-0778-4350-be9b-3ca53cfa7ded" />


#
</details>


<!------------------------------------>
<details>
  <summary> <b>  Summary of PowerBI </b> </summary>

<br/>

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/e7ec287c-68c4-43f6-9bd2-4367125a2084" />


#
</details>

## SQL
<!------------------------------------>
<details>
  <summary> <b> What is SQL ? </b> </summary>

<br/>

Everything generate data and data is everywhere.

**Your Profile**
| Keys         | Values |
|--------------|--------|
| First_Name   | Brahma |
|  Middle_Name | Visnu  |
|  Last_Name   | Mahesh |
| Age          | 21     |
| Gender       | Male/Female  |
| DOB          | '2050-01-01' |
| Address      | 108, Heaven, Galaxy | 
| Mobile Num   | +91 9876543210 |
| Aadhar_ID    | 1234 5678 9101 |
| Passport     | IND101BHARAT   |
| Driving_License | 100001010101 |
| Pancard         | ITC19101   |

Your phone, tablet, PC, Laptop, car, smart watch, health wearables, Home CCTV, IOT devices, drones, bank finance statement, health insurance, salary, school bills, hospital bill, electricity bills, water bills etc all of them generated data.

Que **Where do we store data ?**

We store a lot of our data diaries, folders and files, spreadsheets, text. Basically we stores them in different files and folders.

This is for us personal, how about companies ?

Companies have a lot of things that generates massive huge amount of data like the products that they produces, the customers, retailers, vendors, sales information etc.

Que : **How do companies handle the data ?** How do they store it.

Of course, they can't use like us simple .txt, .excel file. They need something bigger, stronger, smarter and efficient.
This is where the concept of **Database** comes into the picture.


<img width="600" height="350" alt="image" src="https://github.com/user-attachments/assets/e347dc30-22b5-4fd3-ab3c-a68e852b24a2" />


### Database

Database is like a container for storing data.
But instead of just dimping files into folders, Database organizes the data so that it is easy to access, manage and search.

**Why do companies use database ?** 

Can't we files like what we use personally, No Companies can't !

e.g. <br/>
Suppose you have to find the total spending in your data <br/>
In order to find the cost, you have to open each of those files one by one and searching for the cost, combining the data. <br/>
It is going to be very long and messy process.

On the otherhand of we use database to store our data and if ask the same question. It is going to be very easy. <br/>
All what you have to do is talk to the database to ask questions and database is going to answer your queries with results.

**How do we talk to database ?**

We use `SQL` (Structured Query Language). <br/>
`SQL` is the language that we use in order to talk to the database.

This process is very fast and way better than having the data stored in different files.

Also, why companies use database is that bcuz in database we can handle huge amount of data. 
like Millions of rows and 100s of columns, your files can't handle big data it will break.

It is safe and secure to use database to store important and critical the data. And we can control who can access what.

So, It is more professional to store the data inside a database.

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/a3045198-f083-4d76-8561-a54d27e532bc" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> What is DBMS ? </b> </summary>

<br/>

In Companies/Oraganizations we have our data inside the Database. Then we have multiple people with multiple roles who work with data, they write different SQL queries in order to talk to the data.

Not only that where only oraganization employees interact with database. We can build a website or an application that as well interact with database by sending different SQL Queries. Of course It depends on how many people are interacting with application or website. It might generate massive amount of SQL Queries that send to the database.

We can also have tools in order to do data visualization where we have like dashboards or reports may be created using PowerBI or Tableau. It is used by Business Users and Stackholders/Managers in order to make decisions. <br/>
Those tools are connected to the database and they creates SQL Queries.


<img width="600" height="350" alt="image" src="https://github.com/user-attachments/assets/02732914-568c-4cd6-8563-9a04501e41d9" />



So, We can see here, we have a lot of interactions with the database from Peoples, to Applications to tools. And all of them are generating SQL Queries in order to interact with the database.

But **Database is just a container/storage**. So we need something a software that manage all those requests that's why we have something called **Database Management System (DBMS)**.

DBMS is a software that manages all those different requests to the database and It makes a priority which SQL Query is executed first, also manage the security (whether SQL Query is allowed to be executed).

> **DBMS is a software that manages database**

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/193c8f61-03e5-4907-b562-a14d192d625c" />

<br/>

We can have DBMS download and install on our PC run it for persona use. We have our data stored in a contained(Storage) i.e. Hardware on our PC also we have DBMS Software so now we can interact with our data on our PC locally.

But in companies we have huge data for that we need hardware(Container/Storage) i.e. Database. We already have a DBMS software. So for Hardware company use something called `SERVER`.

Server is like a very powerful PC and It is live 24x7. So, It is always availble.

Here, Companies decides whether to use Server inside the company or to use Cloud Server in order to store data inside database and run DBMS

- **Database** is a container/storage to store data
- **SQL** is the language to interact with the Database
- **DBMS** is manager who manages the database
- **Server** is the physical machine where database lives.


<img width="600" height="350" alt="image" src="https://github.com/user-attachments/assets/636d5444-a294-4c0c-8aea-9f736315f84f" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Types of Databases </b> </summary>

There are different types of Databases

**1. Relational Database**

It is very simple like spreadsheets where we have **tables - columns, rows**

There are relationships between the tables to describe how they relate to each other, that'w why we call it **Relational Database**

- [x] **Microsoft SQL Server**
- [x] **MySQL**
- [x] **PostgreSQL**


**2. Key-Value Database**

This type of database is organized completely different  where we have pairs of keys and values.

It is like a big dictionary where we have a word like key and definition as value.

- [x] Redis
- [x] Amazon Dynamo DB


**3. Column-based Database**

This is also important, instead of grouping the data by the rows this type of databases group the data into columns that's why it is called as **Column-based database**.

This is very advanced database in order to handle huge amount of data where the main purpose is search for data.

- [x] Apache Cassandra
- [x] Amazon Redshift

**4. Graph Database**

The main focus here is the **relationship between the objects**.

Here main idea is how to connect my data points

- [x] Neo4j

**5. Document Database**

In the document database, data is stored entire document where the structure of the data is not that important. 

But what is important here is **to fit everything in one page/document**.

- [x] MongoDB


<img width="600" height="500" alt="image" src="https://github.com/user-attachments/assets/79ebc37e-25d5-4568-9869-97cdead33adc" />


### SQL vs NoSQL

Based on all of those five database we can catagorize/group them in 2 types :

1. SQL : `Relational database`

2. NoSQL : `Column-based database`, `Key-value based database`, `Document database`, `Graph database`


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/50aa4778-4298-41cc-8f0e-a48a1b2ec09c" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Database Structure </b> </summary>

<br/>

Databases are very structured and organized.

It has following hierachy

`Server` > `Databases` > `Schemas` > `tables | rows and columns` > `cell`



Starting point is **`Server`** It is a very powerful PC. It is where database lives.

Inside it we can have multiple databases. 
e.g. salesDB, employeesDB.

So, a server can host multiple databases.

Database is a container/storage where ou data is stored.  

In each `Database` we can have multiple `Schemas`.

Schema is like a category or logical container that we can use it in order to group up related object.

e.g. If we have 100s of tables so we can group/split all of them in different categories.

It helps us to organize our tables or objects in the database.

In each `Schema` we can have multiple objects like `tables`

A `table` is like a spreadsheet. It organizes our data into columns(fields) and rows(records).

Each records represent one customer/person.

Each table has one important columns like `Primary Key`

It is always very important to have one unique identifier for each row.

We use it for different purposes in order to indentify one specific row or combine it with another table etc.

Primary key is like finger-print which is unique. No 2 rows can have same ids.

Overlapping between the columns and rows, we have a single value known as `Cell`

Each `cell` stores specific data type.

Data type is like what kind of data we're storing Number, Integer, decimal, Text, Char, Varchar, Date and Time.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/3efa55b7-5b7d-4ab7-b107-7f3129fa93a8" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Types of SQL Commands </b> </summary>

Let's say we have a database, this database is empty.

First thing we do is to write anything in database, we create a brand new table, insert data into it, delete it, drop it ans others things we do  in the database using different commands.

We have different Families of different commands.

### DDL (Data Definition Language)

`CREATE`

`ALTER`

`DROP`

`TRUNCATE`

`RENAME`

### DML (Data Manipulation Language)

`INSERT`

`UPDATE`

`DELETE`


### DQL (Data Query Language)

`SELECT`

### DCL (Data Control Language)

`GRANT`

`REVOKE`


### TCL (Transaction Control Language)

`COMMIT`

`SAVEPOINT`

`ROLLBACK`


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/205cc786-7cf7-4c5c-8e62-54cd66b3f36c" />


#
</details>


<!------------------------------------>
<details>
  <summary> <b> Why to learn SQL ? </b> </summary>

1. In order to interact with data in database

2. High Demand of SQL Skills for any data related job.

3. Industry Standards to use SQL


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/77dbac6e-380e-4cf2-9266-9e4f6921cc88" />


#
</details>


<!------------------------------------>
<details>
  <summary> <b> Summary of SQL, Database, DBMS </b> </summary>


With that we have a clear understanding What is SQL, Why we need it?, What is database, DBMS, Server and DBMS Types, SQL Commands and How things are organizes in databases. 

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/1744c78d-714f-4414-9828-c73f65789169" />


#
</details>

## Python

<!------------------------------------>
<details>
  <summary> <b> What is Python ? </b> </summary>

### What is programming language 

Imagine that you want to give your computer a task and you say - Hey Computer, Please calculate 5 + 5.


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/a7cab605-dce0-4aa9-a131-693d2b1c1f53" />


Computer will not understand what are you talking about? and nothing is going to happen.

We can't use the natural human language in order to give tasks to computer/PC. Instead we have to give instructions to computer/PC in a language which computer understand it.

Python
```py
print(5 + 5)
```

> **Program** : A set of instructions that is written in a language that computer understand.

Not all languages are meant for everyone. Some are meant for people and others are made for machines.

Natural Languages : `English`, `Hindi`, `Spanish`, `Japanese`, `Urdu`, `Arabi`

Programming Lanuages 

- High Level Languages : `C/C++`, `Java`, `Python`, `JavaScript`

- Low Level Languages : `Assembly`, `C`, `RUST`, `GO`

- Machine Languages :  Binary Languages `0s1s`

This is how machine works, we have abstraction between Human and Machine in order to hide the complexity.


<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/79c4162e-5cc5-4a35-ad27-0c759d9b0d11" />


#
</details>


<!------------------------------------>
<details>
  <summary> <b> How Python Works ? </b> </summary>

Let's say you open a **Code Editor** like VSCode and start writing `Python` code inside a  file extension `.py`.

Here, you're basically writing a source code.

Once you run your code, the computer can't immediately execute your instructions bcuz it's high-level language(code). Computer need a lower level code.

So What will happens is we have something called **Compiler/Interpreter** in Python. It will compile/interpret our python code and translate it into another code that is **byte code** with the extension `.pyc` i.e Python Compiled. This happens automatically, we will not even notice it.

What happen here is the compiler/Interpreter of Python translates the high-level language Python Code to a low-level language byte code. It is really hard to understand byte code compared to Python code.

Our Python code is not executed yet, Python Interpreter/Compiler just did translation.

Before anything to be executed what happens is Python might link some **libraries**. It is like pre-written chunks of code that helps your code to do something specific like woking with files, handling data, printing on console and so on. Basically some predefine functions and classes are written already.

Now Python has everything byte code, libraries and now python will run byte code using something called **Python Virtual Machine**. It is like a software that understand the byte code of python and take care of running it.

Python virtual machine finally convert your instructions into Machine codes 0s 1s bcuz computer can only understand 0s 1s. Once it run, you will see the result whatever you program is designed to do.

All those 3 steps (Compile, Translate and Execute) we called them **Python Interpreter**. It is like a toolbox that handles everything needed to run a python code.


<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/62377796-5d6e-4089-8bd3-3a588903c2c9" />


#
</details>


<!------------------------------------>
<details>
  <summary> <b> Why Python ?</b> </summary>

### Why to learn Python in the first place ?

There are many languages out there in market then why millions of people choose to learn Python!

1. Python is very powerful at the same time very simple.

You can build things in less number of lines compared to other languages like Java.

Java
```java
import java.io.*;

public class Main{
    public static void main(String[] args){
        try {
             BufferedReader reader = new BufferedReader(new FileReader("file.txt"));
             String line;
             while((line = reader.readLine()) != null){
                  System.out.println(line);
             }
             reader.close();
        }
        catch(IOException e) {
            e.printStackTrace();
        }
    }

}
```
Python
```py
with open("file.txt") as f :
     for line in f:
         print(line)
```

2. Python is used literally everywhere.

We can use it to build everything.

e.g. : to build Websites, to build Applocation, to automate tasks, to work with data, to build games, to control robots. 

In whatever direction you will go in tech, you will find python.

3. Python has huge community.

There are 1000s of developers and experts are there to help you by sharing the knowledge across the platform.

This type of community makes language alive.

4. When it comes to AI, Python is leading the way.

Almost everything you hear about like ChatGPT, Image Generation, Self-driving car models. It's build with Python. bcuz Python has an incredible ecosystem for AI/ML.

Because of these reason Python is one of the most in-demand popular programming language in the worls right now. If you're interested in future Python is the right language.

Python is easy to learn, has incredible use cases, shaping the future with AI, has huge community support!

<img width="1188" height="675" alt="image" src="https://github.com/user-attachments/assets/b98b0d76-448c-429b-9e17-e5e3e32edd2c" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Python Roadmap </b> </summary>

Learning Python is like a journey, and every journey needs a roadmap.

Everyone starts from same place Student, Developers, Experts, Instructor, Data Engineer, Web, AI, Gaming Developer.

**Beginner Level**

Start as beginner by How to write a simple code, understand variables, datatypes, control flow in code, functions(organizing your code into small re-usable blocks)

**Intermediate Level**

How to handle errors and Exceptions, structure your code using OOP, how to split your project into modules, how to work with files etc.

Making your code more professional like a real developer.

**Advanced Level**

Start learning advanced techniques like outside of our code in order to connect ourself with APIs in order to grab data from the internet, how to test your code, how to scrap website to collect the data automatically.

At this level you start doing real project and solving real problems.

**What next**

We can't keep learning everything. It's impossible.

Now make sure about the direction/path which you want to follow.

Choose/Pick the path/direction that match your interest and career goals.
- Data Engineering : pySpark, ETL, Automation with Python
- Data Science : Panda, NumPy, Plotly
- AI and ML : PyTorch, Transformer, TensorFlow
- Web Development : Flask, django, Requests



<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/5af8d097-8188-4d3a-ae93-8e6a7f6b2450" />


#
</details>


## GitHub
<!------------------------------------>
<details>
  <summary> <b> What is GitHub ? </b> </summary>

If you're new to Git, Don't worry! It is simpler than it sounds.

It is all about a safe place where you can put your codes that you're developing and you will have possibility to track eeverything happenes to the code. As well as you can use it in order to collaborate with your team and if something goes wrong you can always rollback.


<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/8309a905-dafe-4f53-85b2-fde59dd58a50" />


#
</details>


## Data Architecture
<!------------------------------------>
<details>
  <summary> <b> What is Data Architecture ? </b> </summary>

Designing the data architecture is exactly like building a house.

Before construction start, an architect design a plan, a blueprint for the house.

How many rooms will be there, how the rooms will be connected, how to make house functional, safe, secure, wonderful, scalable.

Without blueprint/plan builders might create something unstable, in-efficient, un-livable.

Same goes for Data Projects.

A Data Architect is like a house architect. They design how your data will flow, integrate and be accessible. So as data architect we have to make sure that Data Warehouse is not only functioning well but also scalable, easy to maintain, safe and secure.

So the role of Data Architect is to brainstorming and designing the architecture of data warehouse.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/70808a9f-c68b-4178-8ec6-e851ac894901" />


### Different approaches in order to design a Data Architecture

First step of building a data architecture is to make a very important decision to choose between 4 major types :

### Approach #0. To build a `Database`.

<details>
  
<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/00a3bdc6-d83e-43d8-a298-c60e91382735" />

</details>

### **Approach #1. To build a `Data warehouse`**.

- It is very suitable if you have **only Structured data** and your business want **to build a solid foundation for Reporting and Business Intelligence**

<details>

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/e606dcb1-7b5b-4847-9724-db4c04a02931" />

</details>

### **Approach #2 To build a `Data Lake`**.

- Data Lake is way more flexible than a Data Warehouse where you can store **not only structured data but also semi and un-structured data**.

- We usually use this approach if we have mix type of data. Like Database tables, logs, images, videos and your business want to **focus not only on Reporting but also Advanced Analytics or Machine Learning**.

- It is not that organized like Data Warehouse.

- If Data Lake is too much un-organized, It can turn into **Data Swamp**. This is where we need next approach

> A data swamp is a poorly managed data lake that has become disorganized, unusable, and inaccessible due to lack of governance, metadata, and data quality controls.

<details>

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/10489860-ff14-4faa-b67d-c8ceb3129cda" />

</details>

### **Approach #3 To build a `Data Lakehouse`**

- Data Lakehouse is mix between Data Warehouse and Data Lake.

- You get the flexibility of having structured, sem-structured and Un-structured data from the data lake but you still want to structured and organized your data like we do in the Data Warehouse.

- This is very modern way on how to build Data Architecture, this is favorite way of building **Data Management System** for most of the Data Architect.

The last and very recent approach is to build a Data Mesh

<details>

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/a20ab414-6566-4fdd-a89c-30cc5346981d" />

</details>

### **Approach #4 To build a `Data Mesh`**

- This is little bit different.

- Instead of having centralized Data Management System, make it de-centralized.

- The idea of **Data Mesh is to make Data Management System de-centralized**. Bcuz we can't have one centralized Data Management System because if it is centralized then it means so bottlenecks. 

So, Instead We **have multiple departments, multiple domains** where each of them is building a data product and sharing it with others.

<details>
  
<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/580b4637-e689-4fde-ac64-0af98a975508" />

</details>

> Pick one of those aprroaches in your project based on requirement.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/78920182-43e4-4470-8b49-259f104fcf5a" />

### Summary

| Feature    | Database   | Warehouse  | Lake  | Lakehouse | Mesh           |
| ---------- | ---------- | ---------- | ----- | --------- | -------------- |
| Workload   | OLTP       | OLAP       | Mixed | Mixed     | Organizational |
| Schema     | Write      | Write      | Read  | Hybrid    | Domain-driven  |
| Data type  | Structured | Structured | All   | All       | All            |
| Real-time  | Yes        | Limited    | Yes   | Yes       | Depends        |
| Governance | Strong     | Strong     | Weak  | Strong    | Federated      |


#
</details>

<!------------------------------------>
<details>
  <summary> <b> How to build a Data Warehouse ? </b> </summary>

<br/>

There are 4 different approaches on how to build a Data Warehouse :

### Aprroach #1. 🏗️ Top-Down Approach (Inmon Method)

We have a data sources, 

the first layer we start with **Staging** where the raw data is landing.

the next layer we organize our data in something called **Enterprize Data Warehouse** where we module the data using the 3NF(How to structure and normalize tables). Basically we're building a new data model from multiple sources.

the third layer is called **Data Marts** where we take small subset of data warehouse and design it in a way that is ready to be consumed from reporting. It focus on only one topic like either customers or sales or products.

After that we connect our BI tools like PowerBI/tableau to the Data Marts.

<img width="800" height="173" alt="image" src="https://github.com/user-attachments/assets/3425b8b8-ac65-4f5a-b61a-814299cc0164" />

<br/>

With that we have 3 layers to prepare the data before reporting.

### Aprroach #2. 🧩 Bottom-Up Approach (Kimball Method)

According to Kimball, building the **Enterprize Data Warehouse(EDW)** is wasting of time. So what we can do is jumpt immediately from the **stage layer** to the final **data marts**. Bcuz building **Enterprize Data Warehouse(EDW)** is a big struggle and waste of a lot of time.

To focus on only building the data marts quickly as possible. So, It is faster approach than inmon.

But with the data, you might get Chaos in the data marts bcuz focus is not on the big picture rather you are focusing on short terms where you might repeating the same transformations and integrations in different data marts.

So, There is a **trade-off between the Speed and Consistent Data Warehouse**

<img width="800" height="312" alt="image" src="https://github.com/user-attachments/assets/fbe45c6d-8f28-42e2-9161-b8027d5835ab" />



### Aprroach #3. ⚖️ Data Vault Approach

We still have Staging and Data Marts but it says we still need a **central data warehouse** in the middle but in this middle layer we will have to bring more standards and rules.

So, We split this middle layer(Enterprize Data Warehouse) into 2 layers :
1. Raw Vaults
2. Business Vaults

In the raw vault, we will have original data but in the business vault we will have all the business rules and transformations that prepares the data for data marts.

So Data Vault is very similar to Inmon(Top-down approach) but it brings more standards and rules to Middle(Enterprize Data Warehouse) layer.

<img width="800" height="451" alt="image" src="https://github.com/user-attachments/assets/b7f4289f-812e-4d7d-83de-80736dc68ff9" />


### Aprroach #4. 🚀 Medallion Architecture

It is very easy to understand and to build. It says we have to build 3 layers Bronze, Silver and Gold.

The **Bronze Layer** is very similar to Stage layer bcuz we have to understand that Having the original data as it is helps a lot Traceability and finding issues.

Next we have **Silver Layer** It is where we do transformations like Data Cleansing, Data Enhancement and Data Preparation but we don't apply yet any business rules and logic.

The last is **Gold Layer**, It is very similar to the Data Marts but here unlike Data Marts we build different types of Objects not only for Reporting but as well for Machine Learning for AI and many different purposes. Here we have business ready objects that we share as a data products.

<img width="800" height="613" alt="image" src="https://github.com/user-attachments/assets/61a453aa-c446-474a-bbf5-9c1ddc4d7780" />


<br/>

These are the 4 approches that we use in order to build Data Warehouse. As a Data Architect, you have to pick one of these when you start your projects.

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/a44cb95c-cb3c-40f4-8dc6-176e9a797bb1" />


#
</details>

## Data Warehouse
<!------------------------------------>
<details>
  <summary> <b> What is Data Warehouse ? </b> </summary>

- What is exactly a Data Warehouse ?
- Why companies try to build such data data management system ?

### Data Warehouse

Father of Data Warehouse is **Bill Inmon**

Bill Inmon, his Definition a Data Warehouse is:
> "A **subject-oriented**, **integrated**, **time-variant**, and **non-volatile** collection of data in **support of management’s decision-making process**."

> - **Subject-oriented** → organized around business subjects (sales, customer, finance)
> - **Integrated** → data from multiple sources is unified
> - **Time-variant** → stores historical data
> - **Non-volatile** → data is read-heavy, not frequently updated and deleted


#
</details>

<!------------------------------------>
<details>
  <summary> <b>  A Scenarios where a company don't have a real data management </b> </summary>

**Scenario - 1** <br/>
Let's consider a scenarios where a company don't have a real data management.

It will have a lot of issues :
- [ ] **Waste of resources and time** (Collecting data from different sources and transforming it)
- [ ] Multiple reports from multiple data analysts with multiple data sources creates chaos hard to make decisions based on these data
- [ ] **Manual Process** is slow and stressful
- [ ] More Employees, **More Human Error** chances in reporting leads to bad decisions
- [ ] **Can't handle big data**
- [ ] **No Integrated Report** bcuz from multiple sources will be chaotic, time consuming and full of risks.

See this picture if a company is working without a proper data management like Data Warehouse, Data Lake, Data Lakehouses.
That's why in order to make real and smart decisions, companies need a data management.

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/01037cd2-581b-4e42-b4e8-beaad4dbec82" />

<br/>

#
</details>


<!------------------------------------>
<details>
  <summary> <b> A Scenario where a company has a data management </b> </summary>

**Scenario - 2** <br/>
Let's see a scenario where a company has a data management.

Here Data Team will not collecting data manually, rather they use ETL components. 

**ETL = Extract Transform and Load** : It is process in order to extract the data from different data sources and then apply multiple transformations on those sources and at the end loads the data to data warehouse. This will be single point of truth for analysis and reporting.

All your reports is going to be consuming the data from the data warehouse which is a single point of truth. 

With that we can create multiple reports as well as create integrated reports from multiple sources.

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/e278de62-230c-4fd6-ada1-8b2af4e6e7ab" />

<br/>

- [x] Create Integrated Reports from multiple sources
- [x] Whole process is automated and organized
- [x] Reduces Human Errors 
- [x] Fast and Efficient
- [x] Integrated data and Historical data access
- [x] Handle Big Data 

#
</details>


## ETL
<!------------------------------------>
<details>
  <summary> <b> What is ETL ? </b> </summary>

<br/>

| `Data Sources` | `Historical Data` or `Increamenal Data` |
|----------------|-----------------------------------------|
| `Extract`      | Indentify the data and Pull it out from source to `Target`          |
| `Transform`    | `Data Cleansing`, `Data Preparation` and `Business Rules and Logic` |
| `Load`         | final `data products` for Analytics and AI/ML Use cases  |

ETL in nutshell, First Extract the raw data, then transform it into something meaningful and finally load it to a target where it is going to make a difference for Data Analytic (Standard Business Analytics + Advanced Analytics) like Business Intelligence and AI/ML use cases.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/7d3da39d-846b-4cac-8d3e-20c4fd26d76d" />

<br/>

In real projects we don't have only source and target. So, Data Architecture can decides to have multiple layers depends on design whether building a Data Warehouse or a Data Lake or a Data Lakehouse or a Data Mesh.

Usually there are different ways on how to load the data between all those layers.

In order to load data from one layer to another layer there are multiple ways on How to use the ETL Process.

<img width="800" height="350" alt="image" src="https://github.com/user-attachments/assets/ec4c61ed-bf3d-4c9c-8fcc-422995acc282" />

#
</details>

<!------------------------------------>
<details>
  <summary> Step 0.<b> Data Sources </b> </summary>

### Data Sources

Companies data exists in **Source Systems** what we want to do is to get the data from the sources and move it to the **Target**.

Here, Source and Targets could be Database tables.

First step is to specify which data we have to load from the sources.

Of course, if we can load everything at a time which is known as **Loading Historical Data**.

Another is to load the data incremently this is knowns as **Loading Incremental Data**.

<details>
  <img width="800" height="350" alt="image" src="https://github.com/user-attachments/assets/b572edaa-39fa-40d5-a221-ba74d182af17" />
</details>

#
</details>

<!------------------------------------>
<details>
  <summary> Step 1.<b> Extract </b> </summary>

### Extract

In Incremental Load, we specify the subset of data from source in order to prepare and load it to the target. 

This step in ETL we call it **Extract**. 

Here we're just indentifying the data we need. 

We pull it out and don't change anything, It is going to be as it is one to one copy like source system.

> Extract has only one task to identify the data that we have to pull out from the source and to not change anything.

<details>
  <img width="800" height="350" alt="image" src="https://github.com/user-attachments/assets/acf63230-0b18-429e-b326-e6044d33e669" />
</details>

#
</details>
<!------------------------------------>
<details>
  <summary> Step 2.<b> Transform </b> </summary>

### Transform

We will take the Extracted data and do some manipulations which is what we called **Transformations**. 

This process is really heavy weight lifting. <br/>
Here, We're going to do **Data Cleansing**, **Data Enhancement**, **Data Preparation**, **Data Integration**, **Data Normalization** in order to change the shape of data.

- Formating
- Renaming tables and columns
- Handling Nulls, Replacing it
- Handling Data types of each columns in each tables
- Standardization of data
- Data Normalization (Structuring the tables)

> In Tranformation, we take the original data and reshape it, transform it into the exact format that we need for Analysis and Reporting.

<details>
  <img width="800" height="350" alt="image" src="https://github.com/user-attachments/assets/49c88473-d21b-4b87-ba92-a30e24bc109c" />
</details>

#
</details>
<!------------------------------------>
<details>
  <summary> Step 3.<b> Load </b> </summary>

### Load

This is the last step in ETL, where we load.

In this step, we take the transformed new data and insert into the target.

It is very simple we take the prepared data from transformation and move it, load it into its final destination, the target for example a data warehouse.

<details>
  <img width="800" height="350" alt="image" src="https://github.com/user-attachments/assets/5498a1c7-96cf-47c3-98c8-a47bf0f029a5" />
</details>

#
</details>


## Data Modeling
<!------------------------------------>
<details>
  <summary> <b> What is Data Modeling ? </b> </summary>

Usually Data Source system delivers raw data which is un-oraganized, messy and not very useful in its current states.

Data Modeling is the process of taking raw data and then organize it, structure it in meaningful way.

So What we do in Data Modeling is putting the data in a new friendly and easy to understand objects (tables) like customers, orders, products etc and each of them is focused on specific information. 

What is very important in data modeling is we're going to describe the relationship between those objects (tables) by connecting them using lines what we call it as **Logical Data Model**

Data Model makes it really **easy to understand our data, relationship between them and processes behind them**.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/402e53cf-508b-47d8-af81-bc1cff2ea5c8" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Conceptual Data Model, Logical Data Model, Physical Data Model  </b> </summary>

3 stages/ways to draw a Data Model

### Stage #1 Conceptual Data Model

Here the focus is only on the entity(tables).

Like Customer, Orders, Products etc

We don't go in details at all, like we don't specify any columns(attributes) inside those entity(table). We just want to focus on what are the different entities(tables) that we have as well as their relationship between them.

> Conceptual Data Model don't go in details, It just gives the big picture.

<img width="150" height="250" alt="image" src="https://github.com/user-attachments/assets/7e8902db-76d0-4a85-a57b-62820c95f2f7" />


### Stage #2 Logical Data Model

In the second stage, we build the Logical data model.

Here, we start **specifying the what are the different columns(attributes) that we can find in each table(entity/object)**.

Like in customers : customer_id, first_name, last_name, gender etc

Here we still the relationship between those entities(tables).

Here we also make is clear which column will be **primary keys** and so on.

Here, we have more details but we don't describe a lot of details for each column and **not worry how exactly we can store those tables in the database**.

<img width="150" height="250" alt="image" src="https://github.com/user-attachments/assets/672a6ee0-f723-4b7b-b5c7-da1060b15165" />


### Stage #3 Physical Data Model

Third and last stage of Data Modeling is we build the Physical Data Model.

This is where **everything gets ready before creating it in the database**.

Here, We will have **to add all the technical details** like 
- Adding for each column(attributes) data types
- Length of each each data type
- many others database techniques and details

<img width="150" height="250" alt="image" src="https://github.com/user-attachments/assets/13288b07-e1c9-46d7-bb7e-882263d6e3c6" />

### Summary

**Conceptual Data Model** gives us **Big Picture**.

**Logical Data Model** dive into details of what data we need i.e. **Blue Print**.

**Physical Data Model** prepares everything for the **Implementation in the database**.

In projects, We only draw Conceptual and Logical data models bcuz drawing/building a Physical Data Model needs a lot of efforts and time.
There are many tools like Databricks, they automatically generates those Physical Models for you.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/d3bc198e-f0bc-4038-9fc9-62d5b5c74b0d" />

#
</details>

<!------------------------------------>
<details>
  <summary> Theory : <b> Star Schema vs Snowflake Schema</b> </summary>

For Analytics and especially for Data Warehousing and Business Intelligence, We need a special Data Model which is **optimized for Reporting and Analytics**. It should be **Flexible**, **Scalable** and **easy to understand**.

For that we have 2 special Data Model :

**1. Star Schema**

It has a central fact table in the middle and surrounded by dimesions tables.

A fact table contains transactions, events and Dimesions tables contains descriptive information.

The relationship between fact table in the middle and dimensions tables around it forms like a **Star Shape**. That's why we call it Star Schema.

<img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/ea1cb156-919f-46c2-80dd-20c6d863ab4e" />

<br/>

<br/>

**2. Snowflake Schema**

It is very similar to Star Schema. Here also we have a fact table in the middle which is surrounded by dimesion tables.

But big difference is that we **break the dimensions into smaller sub-dimension tables**.

As we're extending the dimesion tables, the shape of this data model looks like **Snowflake**.

<img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/163c7792-6300-4475-93e2-e1c32303030b" />


### Compare Star Schema and Snowflake Data Model

Start Schema looks easier, So It is usually easy to understand, easy to query. It is perfect for Analysis.

But Star Schema has one issue, Dimension might contain duplicates and your dimensions get bigger with time.

Snowflake Schema is more complex, you need a lot of efforts to understand schema and qyery something.

But main advantage here in Snowflake Schema is It comes with Normalizations as we're breaking those redundancies into small tables. You optimize the storage.

But these days who care about storage.

> **Star Schema** is very commonly used across the project, It's perfect for Reporting using PowerBI.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/f1b3c6e5-225a-446a-8671-2a49414c2399" />

#
</details>

<!------------------------------------>
<details>
  <summary> <b> Dimensions vs Facts </b> </summary>

DIMENSION   

It contains Descriptive information(categories) that give context to the data.

Product_Info (product_id, product_name, category, etc )

**Who? What? Where?**

FACT

It contains Qualitative informations. They are events like transactions. 

It contains 3 important information :
1. Multiple Ids from multiple dimensions
2. Data Information
3. Measures and Numbers

If you see all these type of data in tables, there are fact tables.

**How much? How many?**

#
</details>

## Dimensions and Measures
<!------------------------------------>
<details>
  <summary> The Secret <b> Dimensions and Measures </b> </summary>

A trick to analyze any datasets is to look at them by dividing into **Measure** and **Dimension**

You can generates endless amount of insights from any project from any datasets.

How to do this?

When we look at any datasets, we see tables with multiple columns and rows.

Here, We have to see data always in 2 categories either  a **Dimension** or a **Measure**.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/fed403bc-5dc6-44f8-9c03-3b51f7368bd1" />


Question is My column is a dimension or a measure ?

In order to assign it into either of these 2 categories, 
you have to ask the 1st Questions :

Is Data Type = Number ?
- If it is **NO** like it is string, date or any other data type that means It's a dimension.
- If It is **YES** then ask 2nd Question

Does it make sense to Agggregate it?
- If answer is **YES** then It is a Measure
- Else It is a Dimension

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/17e7bf14-aba6-430f-b350-210803e0b369" />


<br/>

Example :

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/341bb1c5-e201-4ab2-9077-071ebe047e4c" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Why do we need Dimensions and Measures ? </b> </summary>

- We need dimensions to group up our data by something.

- How much?, How many? Here we always need to aggregate/calculate the data for that we need measure.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/49e13491-a5da-44e8-89c8-1740f62a557f" />


#
</details>


## Separation of Concern(SoC)
<!------------------------------------>
<details>
  <summary> <b> What is Separation of concerns ?</b> </summary>

This is the secret that each Data Architect must know.

As we're designing the architecture, we have to make sure to break down the complex system into smaller, independent part.

Each part is responsible for a specific task. 

Here comes a magic, the component of your architecture must not be duplicated. We can't have 2 parts doing the same thing.

The idea here is **to not mix everything**. 

This is one of the biggest mistake in you see in every project.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/2b61f51c-0e7d-4f25-9790-dd4cc9bf8124" />

So, A good architecture, follow this concept/principle.

Real World Example in a data project :

We have defined a unique set of task in each layer(bronze, Silver, Gold).

Each layer has its own unique set of tasks, we do not allow to do task of Bronze layer in Silver layer vice-versa.
Bcuz we have decided and made a standard rules for that.

> **As a Data Architect you must have to this mindset of Seperation of Concern to be in Top 1%**.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/0e2da6da-0321-4245-9988-120a92a87497" />


### Standard Operating Procedure (SoP)

We also have some defined SOPs in order to make everything Standard.


#
</details>



## Data Catalog

<!------------------------------------>
<details>
  <summary> <b> What is Data Catalog ? </b> </summary>

<br/>

We have a Data Model, and we build something called a Data Product.

We will be sharing the data products with different types of users (Data Analyst, Data Scientist, Business users etc).

There is something that every data product must need that is **Data Catalog**.

Data Catalog is a document that describe everything about your Data Model (the schema, the tables, the columns, relationship between tables).

With that we make our data product very crystle clear for everyone who wants to use it, derive more insights from our data projects easily.
Data Catalogs saves time otherwise each users keep asking about the same data product everytime.

- What is this table?
- What does mean by this columns?
- How to connect Table A with Table B?

You have to keep repeating yourself and explaining the same stuffs over and over again.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/7bc05a40-82a7-49fe-ac47-89fda58e0b1e" />

<br/>

Instead, We prepare a Data Catalog, a Data Model and deliver everything together to the users to save your time and energy.
So, It is a best investment and best practices.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/5651888d-33f5-45af-a262-11bccf8cc818" />


#
</details>

## AI Engineering
<!------------------------------------>
<details>
  <summary> <b> What is an AI Engineer ? </b> </summary>

**AI Engineer** is someone who builds Systems that use AI to solve real business problems.

- [ ] You're not building ChatGPT/Gemini/Claude or you're training a data Model.

- [x] You're **building an AI System**.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/28cea1dc-3d92-44a1-96fd-05c330382a50" />

<br/>

What is inside an AI System?

Inside AI System, you will find the following components :

- You will be connecting AI Models like `OpenAI Models` from **Hugging face**

- You will be connecting company data, databases, files, documents.

- You will be connecting Company's tools and Apps like Email, Internal Services tools and other stuffs.

- You will be connecting the Interfaces where the users are going to interact with the AI System.

> **Basically You're just connecting stuffs in one place, Your main job is to make everything correct, secure, fas, scalable and cost efficient**

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f7f3217c-5ef2-49a3-bfa8-d90b5ecc3314" />

#
</details>


## Prompt Engineering

<!------------------------------------>
<details>
  <summary> <b> What is Prompt Engineering ?</b> </summary>

<br/>

Most people think **Prompt Engineering** is just like you're typing something to ask LLM Models like ChatGPT or Google Gemini or DeepSeek and hoping for best answers.

But It's not that simple. There is a skill behind it.

It's all about how you communicate with a Model so that It understand exactly what you want and how to get a tailored answers exactly How you expect?

Meaning, We have to give a detailed clear instructions and Context.

We have to tell the Model Who it is? and What its role and Show examples of results that you want.

Each time you get an answer from AI, You can review it and improve your prompts step by step.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/c40f4cca-47fb-498d-b0fe-55135d6dff15" />


#
</details>


<!------------------------------------>
<details>
  <summary> <b> What is OpenAI API ?</b> </summary>

<br/>

**API** is let us interact with the same Model but with one big difference inside your own app, inside your own website, inside your products.

With that you're building like a ChatBot Assistance inside your tools.

It is very simple to do. It is just few lines of Python. You send a prompt, you get a response and you will display it wherever you want.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d0e9a0b8-1bec-44c1-a500-ecea4f52fc97" />


#
</details>


<!------------------------------------>
<details>
  <summary> <b> What is Hugging Face ?</b> </summary>

<br/>

As we build our AI System, We can notice that we can't rely completely on OpenAI bcuz actually they're closed source. That means we have no control over the Model, We can't see how exactly it works.

We have to pay a lot for using Tokens every time. And if you're not using Cloud services like Azure/AWS/GCP your company data will leave your environment and this is huge problem for many businesses.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/a463f2d7-abac-4aa9-bb83-60682e53fdd4" />

<br/>

This is where the **Hugging Face** comes into the picture.

Click Here [**Hugging Face**](https://huggingface.co/)

It is the biggest community library for AI Models. There are already more than 2 millions model over there. and best thing is most of them are free. You can go and find model for almost any problem that you might encountered.

As a Data Science Industry, As of now we don't have model trained on anything from Scratch..

All what we have to do is just find the right Model for your business use case and fine-tune it.

The big advantage with Hugging Face is that we can download the models locally at your machine and you can deploy it anywhere you want.
With that you stay in your control and you can use sensitive data for the model bcuz nothing is leaving your envirnment as well you reduce the cost.


<img width="500" height="3500" alt="image" src="https://github.com/user-attachments/assets/af72396f-3bdb-4030-9f80-4f5fe111e7f2" />


#
</details>


<!------------------------------------>
<details>
  <summary> <b> What is Langchain ? </b> </summary>

<br/>

Now we can talk to AI Model, we can write good prompts, we can build cool demos, but this is not enough to build AI System bcuz you need to connect everything together. This is where **LangChain** comes in.

We can use **LangChain** in order to orchestrate the whole process to connect all the models that we need (the tools, the memory) as well as our business logic.

AI can take multiple steps in order to complete a full task. This is exactly what AI System does.
It is not just like One Prompt and one Answers.

Click Here [**LongChain**](https://www.langchain.com/)

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/80811b76-b4ff-44f5-9616-87cf1eff3900" />



#
</details>


<!------------------------------------>
<details>
  <summary> <b> What is RAG ? </b> </summary>

### RAG = Retrival Augmented Generation

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/0fdbc6e1-f3d5-4748-a65c-e41a52f057cc" />

<br/>

The issue is that all the AI Models are actually pre-trained using public data.

But of course, the companies data are protected not available publicly which means AI Models have no idea about the companies data.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/a923c0ea-c118-42fa-b37b-fa96e2e3e105" />


<br/>

So, we have somehow to connect company's data to the AI Model, Here comes the concept of **RAG(Retrieve Augment and Generation**

**How it works ?**

First we take all the companies data, files and PDFs and you want to store them into something called Vector Database.

All what we have to do is turn a text into something fancy **Embedding**(It is just representing the token(word which is text) with numbers and then load and store all those embedding inside the vector database.

Once User ask a question, It is going to turn into embedding and System is going to start comparing and searching for the closest match using Semantic Search.

Once it finds the right information, the LLM Model is going to turn it into response.

So, It's all about adding memory to the LLM Model to use your real data instead of relying on what models were pre-trained on.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/88a14d89-d352-4304-b295-60bd6b80cd83" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> What is AI Agents ?</b> </summary>

<br/>

We all use AI ChatBots like ChatGPT, we write prompts and it gives us text in reponse.

But this is not enough, Companies want more than a nice answers on the screen. They want an AI that actually gets the works done.

This is exactly why we have **AI Agents**.

The AI Agent does first thinking and then it is going to take a real actions.

e.g. : Talking to database, updating records, calling an API, triggering a workflow.

It is also great in order to automate a lot of boring task that we normally do at work like reading the incoming emails, responding to it, createing a summary a meeting, creating those boring Jira and Service Now Tickets.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/b3c81016-6fb0-4172-b396-91b5f1236505" />


<br/>

It is way more that just a chat with AI.
#
</details>

<!------------------------------------>
<details>
  <summary> <b> What  is MCP ?</b> </summary>

### MCP = Model Context Protocol

AI Agents can only take real actions like checking emails, querying database, calling an API only if they are connected to the external sources.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/6b52c4fb-5da0-4c88-bbc4-be705b9b26c0" />

<br/>

Here, There are 2 big problems :
1. If we connect our AI Agents to the production database, this is risky.
2. We have a lot of external systems and we will be ended up building Connectors  for each tool which takes a lot of times and efforts in order to create a new connectors each time, we are connecting a new system to the AI Agents

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/f2e7e6dc-a2bf-47a2-96f0-0e06412d231e" />

<br/>


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/8f3892c0-d982-4dc9-bac9-086afea53a31" />

<br/>

This is exactly why we have **MCP**.

MCP fixes those issues.

We are going to Add a safe and standard layer between our AI Agents and Our Sources.

This has a a lot of benefits :
- [x] We can plug and play any system to our AI Agents wuthout creating each time a new connectors.
- [x] Using this layer gives us full control on how the AI os going to interact with our sources where we can add a lot of policies in order to protect our external sources.

Using MCP Servers and Protocol, It is going to make everything like faster. We can connect a lot of things as well as feel safe connecting AI Agents to our sources.

<br/>

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/9dfd51cf-3a08-44d4-9e1a-3461cf5afdd9" />


#
</details>

<!------------------------------------>
