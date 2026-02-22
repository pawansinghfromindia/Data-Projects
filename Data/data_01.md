# Data and Data Literacy

## What Data Team does and How Data Team works ?

<details>
  <summary> <b> Data Team </b> </summary>

- What's a data analyst ? <br/>
You Answer business Quetions using Data ! <br/>
Bridge between raw data and Real Business Decisions

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/8eae5dd6-0a7e-4787-956f-c809eb3e4497" />

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

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d44d40c0-0ecd-4167-84b8-2cb887ec2a92" />


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

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/45f5bcca-d855-4cd6-9ac2-2e004c82d955" />


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

<img width="832" height="638" alt="image" src="https://github.com/user-attachments/assets/8605ea37-14cc-44fa-ab34-7ffe49eda525" />

#### Phase 1. 

**Collect the Data** i.e. Data Extraction from different Data Sources

<img width="771" height="648" alt="image" src="https://github.com/user-attachments/assets/86b94ecf-b8a7-4d8b-8850-cac0747b7f3a" />


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
<img width="742" height="625" alt="image" src="https://github.com/user-attachments/assets/91f89d88-2873-4670-958e-8783bf610a7c" />
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


<img width="1078" height="568" alt="image" src="https://github.com/user-attachments/assets/26f43167-b7dc-4f2d-91d2-d011d5db76fd" />


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

<img width="805" height="375" alt="image" src="https://github.com/user-attachments/assets/862f4cf4-e61a-4f67-a3ad-2b088c232c73" />


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

<img width="1196" height="562" alt="image" src="https://github.com/user-attachments/assets/bdb85e2f-d839-47af-9798-f78f0f175ad1" />

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


<img width="832" height="383" alt="image" src="https://github.com/user-attachments/assets/70b712c4-39c3-4107-9293-61db6de04141" />


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

<img width="771" height="298" alt="image" src="https://github.com/user-attachments/assets/f4b34070-8435-40fa-9f52-a782f4520832" />

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

<img width="736" height="445" alt="image" src="https://github.com/user-attachments/assets/b6e745d4-f3c9-4d6c-8568-73b9d3a6ffed" />


#
</details>


<!--------------------------------->
<details>
  <summary> <b> AI Agents </b> </summary>

<br/>

We have come so far in the AI/ML field is that we have something called **AI Agents** 

We are now beyond to having only a quick conversation between Business Users and the pre-trained LLMs 

Now users can ask Model many stuffs beyond to just having conversation. Like

- How many customers did left last year.

Basically now we have one AI Agent that is using the pre-trained Model to convert the text or questions asked by business users to SQL Query which will direcly goes/interact with the database and fetch the data and show the result as visualization to end-users.

- Where I can find the customer data in which system in which application.

For this scenarios we can another AI Agent that could use another pre-trained model that is specialized in scanning the document. This time we don't need the company data, we need documentation of company.


<img width="1177" height="688" alt="image" src="https://github.com/user-attachments/assets/40e239cd-e557-44e1-9c52-676031cf628f" />

<br/>

<img width="1161" height="559" alt="image" src="https://github.com/user-attachments/assets/f3c205eb-17e6-4404-a994-b91ba38c8942" />

<br/>



#
</details>



<!--------------------------------->
<details>
  <summary> <b> </b> </summary>

#
</details>
