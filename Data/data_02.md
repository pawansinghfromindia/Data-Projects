# Data and Data Literacy


## What Data Team does ?

> **Data Analyst**

<details>
  <summary> <b> What's a data analyst ? </b> </summary>

<br/>

`- Data analysts Answer business Questions using Data !` <br/>
`- Data analysts are Bridge between raw data and Real Business Decisions`

<img width="250" height="150" alt="image" src="https://github.com/user-attachments/assets/8eae5dd6-0a7e-4787-956f-c809eb3e4497" />

What is the role of a data analysts in a data team ? <br/>
In a company we have manager, stakeholders, project leads and their whole job is to make smart decisions by asking critical questions. <br/>

`Q : Which region is underperforming ?` <br/>
`Q : Why're profits down ?` <br/>
`Q : Should we invest here ?` <br/>

Basically they have many challenges in company and they need quick and smart decisions. <br/>
Without using data, they're just guessing, relying on opinions, gut feelings and outdated information left, right, top, down.

#
</details>

> Without **Data**, you're just another person with an opinion ~ William Edwards Deming
<details>
  <summary> <b> Data and Decisions based on Data, Story using Data Visualization </b> </summary>

<br/>

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

<img width="1191" height="608" alt="image" src="https://github.com/user-attachments/assets/3331b498-5dbc-49cd-a1b6-a8efc21dc039" />


<br/>

Here, We have issue, This might work for small and meduim businesses. 

#
</details>

## How Data Team works in big companies?

<details>
  <summary> <b> How Big company works with data ?</b> </summary>

<br/>

This setup (Data Sources like DDAPI, databases, csv, excelsheet SQL Query, data pull, transformation, aggregation, Excelsheet, PowerBI/Tableau Report Data-Analyst Business Answers, Business Questions, Managers, Stakeholders) won't work for a big, modern company.

Why ? bcuz Big, modern company generates big data and It's going to be really hard for data analysts to manually extract the data for analysis bcuz you need huge data and your request take hours and even days to get the data, It might crash in the middle ans sometime impossible to get all the data. 

`No Data -> No Analysis -> No Answers for business Questions -> Managers/Business users can't wait for weeks to get answers from Data Analysts.` 

So Company need to scale up things, so they hire new peoples like : **Data Architect**, **Data Engineers**, **Data Analysts**, **BI Developers**, **Data Scientists** etc.

#
</details>

> **Data Architect**
<details>
  <summary>  What's a data architect ? </summary>

It's similar to an architect of a building **who design a blueprint of a scalable data system**.

- Organize data into multiple layers (Madellian Architecture):
- [x] **Bronze Layer** : Raw Data
- [x] **Silver Layer** : Clean Data (Transformation Data Cleansing and Data Preparation) 
- [x] **Gold Layer** /Business Layer : Final Structured Optimized Data (Transformation Business Rules) 

So, all what a **Data Architect** does is ***designing the scalable data system***. But they're not the one who are building it. 

<img width="851" height="642" alt="image" src="https://github.com/user-attachments/assets/6e7e5468-6c3f-4541-8ecb-833f9c7953b3" />

<br/>
For building, company hires experts called them **Data Engineers**.

#
</details>

> **Data Engineer**
<details>
  <summary>  What's a data engineer ? </summary>

Data Engineers build something called ***Data Pipelines***. It is all about to connect to multiple source systems and move the data from sources to the new data system automatically as well as smooth and quick. 

So basically bring data to ***Bronze Layer***(keeping the data as it is) from there move the data to ***Silver Layer*** (Data Cleansing, Data Preparation, Data Standarization and Strucuring) for business layer i.e. ***Gold Layer*** (Data Modeling which is highly organized and optimized model that is perfect for quick analysis).

With that we have a process that runs automatically from the ***source system*** until the final ***Gold Layer***. This process run everyday, very fast and in some scenarios as a stream like real live data.

<img width="832" height="630" alt="image" src="https://github.com/user-attachments/assets/8b8eab52-56a7-41ef-b4b2-c50a88391a75" />

<br/>
After that comes companies hires **Data Analysts**.

#
</details>

> **Data Analyst**
<details> 
  <summary> What's a data analyst ? </summary>

Thanks to Data Architect and Data Engineer, Data Analyst's life become way easier now. 

No more nightmare for pulling the data manually from the Source systems. <br/>
No more need to Excel Spreadsheet list. 

Now everything is prepared for Data Analyst to BE FAST in ASWERING THE BUSINESS QUESTIONS, Data Analyat will go the Gold Layer which is a business layer where data is already ready, Data Analyst just need the SQL Query, querying the data model in order to explore the data
and find answers for all the business questions.

`Speed up the whole process, Quick Answers to business questions`

Once find the answers to business questions, build a visual reports and tell a story for managers/business users.

<img width="1201" height="539" alt="image" src="https://github.com/user-attachments/assets/20a2f2da-6952-4e9c-a92a-5b9c3351c508" />

<br/>

Still here an issue is there, One-Time Reports for Ad Hoc Questions.
Since, ad-hoc questions, so ad-hoc query so everything is one-time from queries to visual reports. 

<img width="1001" height="561" alt="image" src="https://github.com/user-attachments/assets/2f66e1eb-dadc-43cc-8f92-be731d507c12" />

<br/>
Out of those reports some of them are very useful and incredibles values which are not just for one time and one manager but for many people across the company are interested in those reports. 

So, New business users want those reports everyday. Nightmare is going to comeback where Data Analysts have to run same queries and generate the same visual reports and send these reports to users everyday. This is a waste of time and stress on Data Analysts.
That's why companies hire **Business Intelligent Developers**

#
</details>

> **BI Developers**
<details>
  <summary> What's a business intelligence deveoper ? </summary>

Data Analyst says to BI Developer to automate the report that he/she build.

BI Developers automate the reports and make it visible for business users. 
- [x] **First** BI Developers will ***build an environment like a `Server`*** where dashboards and reports are live 27x7. <br/>
      This must be secure and access management. Sometime all the data is available for everyone in the company.

- [x] **Second** Once Reporting Server is created, BI Developers take everything the report, logic and build from it something called ***Interactive Dashboard***. <br/>
      This dashboard is going to be connected with Gold Layer data model so that it runs everyday automatically so that dashboard and reports get fresh data. 

Once everything is live users(business users, managers) start requesting access to the reports and dashboard data.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/ada7d45f-d2ad-4d78-9182-99f96f337ee9" />


<br/>

🧑‍💻 ***Difference between Data Analysts vs BI Developer jobs***

- Data Analyst is the one who bring the first reports and insights and once a visual report gets very important for business.
- The BI Developer is the one who is reponsible for making these reports accessible, scallable, everyday 24x7 with refresh data for business users.
 
#
</details>

> **Everything is highly automated and scalable**. So that data flow from the sources into the different layers of data systems and also automatic flow to reporting servers and refresh the data.






