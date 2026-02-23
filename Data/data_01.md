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

`Q : Which region is underperforming ?` <br/>
`Q : Why're profits down ?` <br/>
`Q : Should we invest here ?` <br/>

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


<img width="1188" height="647" alt="image" src="https://github.com/user-attachments/assets/79ebc37e-25d5-4568-9869-97cdead33adc" />


### SQL vs NoSQL

Based on all of those five database we can catagorize/group them in 2 types :

1. SQL : `Relational database`

2. NoSQL : `Column-based database`, `Key-value based database`, `Document database`, `Graph database`


<img width="1102" height="659" alt="image" src="https://github.com/user-attachments/assets/50aa4778-4298-41cc-8f0e-a48a1b2ec09c" />


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


<img width="1189" height="652" alt="image" src="https://github.com/user-attachments/assets/3efa55b7-5b7d-4ab7-b107-7f3129fa93a8" />


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Types of SQL Commands </b> </summary>


#
</details>


<!------------------------------------>
<details>
  <summary> <b> </b> </summary>


#
</details>


<!------------------------------------>
<details>
  <summary> <b> </b> </summary>


#
</details>
