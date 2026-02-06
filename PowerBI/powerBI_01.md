# PowerBI

<details>
  <summary> Contents </summary>

- Downloading and Installing Microsoft PowerBI Desktop
- A full tour of the Interface of PowerBI
- Building things in PowerBI :
  - Connecting a new data and work with Power Query
  - Build a Data Model
  - Doing DAX Calculations
- Create a Dashboard using PowerBI (a Mini Project)
- Setting up your PowerBI Service Account
- How to publish your project online
- PowerBI Mobile App
  - We can install it on our phone in order to interact with your project.

</details>

> Let's experience the whole ecosystem of the PowerBI end to end (not in details)

We have 3 main tools in PowerBI.
1. **PowerBI Desktop**
2. **PowerBI Service**
3. **PowerBI Mobile**

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d896fe71-d9ad-4a81-8bec-9c4a6d9cd203" />


**PowerBI Roadmap** : 


Let's explore the PowerBI Desktop :

# Step#1 PowerBI Desktop

<details>
  <summary> PowerBI <b> Desktop </b> </summary>

- The most important tool of PowerBI is **PowerBI Desktop**. This is the core of everything.

- We spend most of the time building things using it, It is where we're going to ***connect the data***, ***transform it***,
  ***build the data model*** and at the end ***build visual reports and dashboard***.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/3b74b48c-aca1-4ede-a945-7fb9d21746d1" />

<br/>



### 1. Download and Install PowerBI Desktop

<details>
  <summary> Click here to see the details </summary>
  - Download & Install it locally on your machine
  - This is only for Windows users (Not for macOS or Linux users)
  - If you're macOS users, Still you can use workarounds to install it using a virtual machine or 
  use parallels to create a windows environment where you can install powerBI and then use it like windows users 

We have to ways to download PowerBI Desktop:
1. Google > search "Download PowerBI" > Download the latest version from Microsoft Official website
2. Go to microsofty Store and search for "PowerBI" and download from there.
   (If you goes this ways, It will keep your PowerBI upto date) as Microsoft does a lot of changes release new versions monthly.
   - Install **PowerBI Desktop** not PowerBI Report Builder which is for pageionating.
   - **Get** -> It will download and install on your PC
   - **Open**
   - You will be on landing page of PowerBI Desktop

</details>

### 2. Let's start exploring the interface of PowerBI Desktop

<details>
  <summary> Click here to see the details </summary>

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f43b462b-7efc-4471-85c1-1c7aeca657fa" />

We have like some common data sources that we used to connect data like `Blank report`, `Excel Workbook`, 
`SQL Server`, `oneLake Catalog` etc <br/>
Then some Guide for PowerBI **Getting Started : Intro What is PowerBI**  <br/>
**Recent** files open history <br/>

**Sign In** 
- As we have not created account (SignUp) yet so SignIn is not possible now.
- As of now, we don't have to login, not required! We will create an account once we are about start PowerBI Service. 

Let's go to the **Blank report**

Now we're officially inside the PowerBI Desktop where we can build things.

We can do a lot of things in PowerBI Desktop, not only **buidling reports and dashboards** like 
we can do a lot of **Data Visualization**, **Data Moduling** etc.

So, If you're first time in PowerBI Desktop, It might feel overWhelming for you with all those icons left-right, top-bottoms. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/74b891d6-0441-437e-8697-028656b219c0" />

Don't worry! we will see everything step by step.

**Step by Step : How to navigate between different views in the desktop** 

<img width="100" height="250" alt="image" src="https://github.com/user-attachments/assets/f445fed8-c370-4b95-9e18-9278db45917d" />


- If you go the left side, you see icons like : <br/>
  `Report View` <br/>
  `Table Views` <br/>
Everything is first empty bcuz we don't have data. 
 `Model View` <br/>

  `DAX query View` <br/>
  `TMDL View` <br/>
These 2 are for advanced topic.

For now just focus on first 3 :  `Report View`, `Table Views`  and  `Model View` these are important as of now.

As we're navigationg through PowerBI Desktop, Everything is empty that's bcuz we don't have data and that's why in 
the next step we will have to connect our data into PowerBI and here we will be connecting files to it.

</details>

### 3. Connect Data (Files)

<details>
  <summary> Click here to see the details </summary>

**Data (Files)** <br/>
Here, we will connecting data (files) to PowerBI. <br/>
So, of course we have to prepare **dataset** in order to walk through PowerBI <br/>
Download your datasets and put it in a safe space on your disk storage. <br/>
Inside that dataset there is a folders Downloaded DataSet **`datasets`** > `first_dashboard` > `customers.csv, orders.csv` files. <br/>
We're going to use these stuffs to build our first `PowerBI Dashboard`. <br/>

<img width="350" height="122" alt="image" src="https://github.com/user-attachments/assets/8ce7fede-cfdc-4442-b98a-9dabef1caf06" />

**Creating Connection** <br/>
Let's connect them (files) to PowerBI.

In order to get the data, this time go to **PowerBI ribbon**

<img width="350" height="177" alt="image" src="https://github.com/user-attachments/assets/85458b62-bfd7-4b02-80c5-f58c8da88f89" />

here in top we have a lot of icons and sections like Data, Queries and relationships and things might change as we change the views
(Report view, Table view, Model view). You might get slightly different things.

Let's go to the `Model view` and most important is `Get data` here, you find some common data sources like Excel workbook, 
SQL server etc but go to the `More` > Here you will see a full overview of all type of sources that you can connect to the PowerBI. 
You can connect almost anything.

<img width="200" height="100" alt="image" src="https://github.com/user-attachments/assets/acbd03cb-4c9b-4f17-b208-1ca2ea679918" />
<img width="200" height="100" alt="image" src="https://github.com/user-attachments/assets/442811dc-c824-4f18-9dbb-f4d5afc00dd1" />
<img width="200" height="100" alt="image" src="https://github.com/user-attachments/assets/ac702646-dad7-44d1-9f45-9fa7b1a14008" />

For example : 
we can connect a file like an excel, text, csv, json, pdf etc <br/>
we can connect a Database like Oracle, IBM, MySQL, Postgres SQL, **Databricks** <br/>
We can connect cloud services from Azure like Azure Blob Storage, etc <br/>

<img width="200" height="100" alt="image" src="https://github.com/user-attachments/assets/576b1122-8e1c-4342-ba29-422e78778fa5" />
<img width="200" height="100" alt="image" src="https://github.com/user-attachments/assets/1378bf0c-628e-4e43-a7e6-89fc993fd2da" />
<img width="200" height="100" alt="image" src="https://github.com/user-attachments/assets/116e8ddc-ca95-4bed-b74f-27a4a3402beb" />
<img width="200" height="100" alt="image" src="https://github.com/user-attachments/assets/45da0934-cc26-460f-9613-86165cc6f509" />


Since our data is in file. So let's go to the file and since files are prepared in CSV <be/>
Click on `Text/CSV` > Connect <br/>
Navigate to the location where you store the data csv files > select one scv file > You will get a `Preview` before loading.
So, we can see file name, columns data and powerBI is smart enough to detect the datatypes based on the rows. 
Basically It is a first overview of your data if things are wrong you can modify or correct it.<br/>

<img width="200" height="100" alt="image" src="https://github.com/user-attachments/assets/5f7bf96d-0dd3-4f9b-9ab1-e1ea0680bed7" />

Now let's load it and PowerBI start loading the data from the files inside your PowerBI Desktop. <br/>
That means now your data is living inside PowerBI. <br/>
If you do make any changes in your original file you will not see it here in PowerBI.
For that you have to load the modified file again in PowerBI.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/4ad9c98f-a78b-42fa-8e79-1879d85847fd" />
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d3334b29-f2c4-47ec-a034-75a6d4ca2908" />

</details>

### 4. Model View (Data Modeling)

<details>
  <summary> Click here to see the details </summary>

Once the data is loaded, you can see in the `Model View`, we have a new `Card` that you can actually move around. <br/>
This card is just the representation of the table, we just loaded. It just shows the metadata information of your file 
like table_name : customers and column_names : cust_id, cust_name, city, etc. <br/>
If you don't want  to see it you can `Collapse` it or `expand` it.

Now, we will go and get the second file, so load the second file to PowerBI. Do same thing. <br/>
With that now we have second Card, the second table orders. <br/>
You can see both customers and Orders tables are connected. And here there are a lot of details like meaning about the those
relationships. But for now considered those two tables are related to each other.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/1dd0e1e2-39b1-44ae-8353-f0631f67d43d" />

The `1` and `*` relationship between Customers to orders table means customers appearing multiple times inside the orders.
Of course this make sense bcuz each customer can order multiple things which is why multiple rows in orders for customer.

By the way, If you don't have any link(relationship). You can always create/drop it by Drag and Drop. And you will get a new window
to describe the relationship between those 2 tables.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/8d170173-1068-460b-b5f9-807a5ceac374" />
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d6e3d88f-0631-4818-9d3c-5be66f15d16d" />

Let's leave it as default. PowerBI is smart enough to detect the right cardinality and other details. So `Save` it.

So we can here in the middle space, It is where we can change stuffs and build things. And in the right side we can find two pens.
1. **Properties** : It shows you more details on where you're currently clicking. 
e.g. : <br/>
If we click in the middle on Relationship Link, It will shows us details about relationship between tables. <br/>
If we click on the table it shows us more information details about table like table name, descriptions <br/> 
If we click on table column it shows detail information about the column like column name, data type etc

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/cb4c00bf-f465-48f3-8178-3efde46c84af" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/684aa838-3f30-4e8f-9d4b-94500576c513" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/0ed06dda-802d-4902-a3b3-898e02b625a6" />
<br/>

2. **Data** : It shows like overview of all your data. <br/>
This is specially very helpful to navigate through data. <br/>
Especially when we have like big Data Model like a lot tables, columns there you might get lost and you're unable to find what you
are searching for. Here in this data section you can see a nice hierarchy like 2 tables and columns inside each table and also seacrh
for the column you are looking for directly.

**Tables** : 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/c21321d2-e3bf-4ab9-8503-940fd20d6449" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/289bb2ef-b6aa-4ce6-b543-c4feb9c45468" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d0f0bc22-1f46-481b-8dc5-3556e2528ad1" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d4c2773d-0249-4497-bd4e-11ed68c21a9c" />
<br/>

**Model** : There is another view of the Model, we will deep dive to this later.

> **Model View**
> - It is where you build your data model.
> - You can create tables and their relationships and organize everything.
> - This is one of the strongest features in PowerBI where we can do advanced things in **Data Modeling** compare to other products.

</details>


### 5. Table View (Inspect)

<details>
  <summary> Click here to see the details </summary>

We have completed connection of our data (files) into PowerBI and also see the Model View. <br/>
Next is let's start reviewing our data using the `Table View` and after that we will do Data Transformation using `DAX`

You might be wondering where is the data? we're only seeing the Table Cards (Table_names, Columns and Relationships).

If I would like to see the content of those tables. How can I do that?
- For that we go to another view we call it `Table View`

> **Table View**
> - Table view will open as a window inside your tables to check all your contents and data and make sure it's clean and loaded
    correctly. 

Let's go over `Table View` click on it and now PowerBI is going to show you the row data inside your tables exactly as it received it
from the files. If you have multiple tables in right side we have options to switch the table. <br/>
So you can switch between the tables data just by clicking on the tables in the right side Data section. <br/>

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/81de71f3-b78e-40d8-a288-8aefff9ab542" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/e810bdeb-34cc-4e77-ad08-d4e2e33d7761" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/4067e9c0-fc07-48ed-b0a0-84396519b2b6" />
<br/>

What we usually do here is to check the data before we go to the last step to the visualizations. <br/>
e.g : 
- check whether the data types of the columns are correct or not 
- Are there any missing values?
- Are the format of columns like date, numbers are correct?

Basically we're checking and inspecting to make sure everything is clean otherwise we have to take actions. <br/>
That means we have to data transformations, data clean up and preparations.

Let's see our Order data. Here order_id data is okay but order_date column's data is not okay It's very long. <br/>
So we can make it shorter. In order to fix the order_date format, what we can do is Select the column and
as we clicked on it we have completely a new menu called `Columns toolas` and we have a lot of actions that we can take on the menu. <br/>
e.g. : Like rename the column, change the data_type, we can format it this is what we need here. just select the shorter format click on it. <br/>
Now we have the correct format of order_date columns in our PowerBI Data. This is what exactly the purpose of this tab, you take an action, 
you change something and immediately you see your row data transforming. So, It is very simple. <br/>
Check the other columns so every other columns is looking good, at the end the sales column which contains long numbers which is difficult to read.
Let's make a change and transform it. As It is a whole number now we can take different actions on this data type and make it. <br/>
So, Basically It depends to datatype you will get different options, we can see this in thousand seperator. Now we have dot for the thousand
which is nice and easy to read.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/79425f9b-b681-4088-870e-2bf56296af0b" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/1de010dd-51c1-4603-a5f7-5e0fb1e164dd" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/c3eabf71-acd6-49ad-a4c3-40ddba326719" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/7744f4e8-e948-422f-b565-3cd5dd4937fc" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/e0afd311-8f63-421f-aec5-73b975dc565a" />
<br/>

Similarly we can switch the table from orders to customers and do transformation if required. <br/>
Here in this customer table, everything looks good but in score column we have missing values, empty stuffs we call them `nulls`. 
So, the value is unknown and this makes an issue when we do aggregations and stuffs on visualization. So, we have to clean up that may be replacing
those unknowns(nulls) with a zero. If customer has no score means customer has zero score. <br/>

If click on score column and check the actions, 
we don't have something that help us to replace the empty with 0. buz it depends on datatype and format. <br/>
We can't do that in PowerBI. <br/>
Here we have 2 options either we use the ***`DAX` the formula language in PowerBI used to create calculations and custom logic in your
model*** or use the ***`Power Query` used to clean shape and prepare your data before loading it into the model*** 

**DAX**
> DAX is the formula language in PowerBI used to create calulations and custom logic in your model.

> It is a programming language in PowerBI where you write a syntax or code in order to do some kind of calculations to repair something or
create something new.

**Power Query**
> Power Query is used to clean, shape, and prepare your data before loading it into the model.

> It is tool from PowerBI which is really easy in order to do data cleaning.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/fb996245-fedf-4972-9d2c-2e50b6b6643a" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/93eca42e-e924-4b11-88d6-7ea7af91e590" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/124139ef-2837-413c-b5a8-fde60718cc61" />
<br/>
  
</details>

### 6. DAX (Data Transformation) `f(x)`

<details>
  <summary> Click here to see the details </summary>

**DAX**
> DAX is the formula language in PowerBI used to create calulations and custom logic in your model.

> It is a programming language in PowerBI where you write a syntax or code in order to do some kind of calculations to repair something or
create something new.

Let's try the `DAX`. 
- In order to do that let's click on the table name over right side of Data section.
- Now either you go back to ripple, you will see the `Table tools` in which we have something called `New Column` or if you just right click
  on the table name you will see `New Column` click on it,
- It will create a new column named with `column` and we have a place to put our calculation or formula.
- Now we're going to use a function called `COALESCE()` which replaces `NULL` values with a new value.
(PowerBI is powerful enough to suggest & explain what the function does). It needs 2 arguments the column which needs to be manipulated and
value with it replaces with like `clean_score = COALESCE(Customers[score], 0)`
- With that powerBI will do 2 things: 1. create a new column 2. values of this column will be output of the given formula.
- Once you apply the formula and hit enter the new column will created with the new values. Now we don't have any missing values in the column.
- This column is shown in data > table with highlighting this column is created by us, was not in original value from scv file.

With that we have better data for Analysis.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/95b9609e-363e-4e60-bdc6-06cc94c7977b" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/8f11273c-46dd-4264-8aac-d4d911d1ee83" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/5ed2332a-3bcd-40a1-82ab-70944da7b299" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f1228bee-7986-47c5-80fa-205fe1d103d9" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/dceed789-b3e7-450f-93d2-07e254055556" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/c5c26933-dff1-400f-8d11-50734d878510" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/fda53d32-fe1a-4fae-a1bc-0ebca187d5a1" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/1b71a5f7-e4ff-4356-a4f5-7bc3242e0dfe" />
<br/>

With that we have learned how to review our data using `Table View` and how to do basic data transformation using `DAX`

Now we will see next another very important component i.e. Power Query for data clean up and data preparation.

</details>

### 7. Power Query (Clean up and Prepare) 

<details>
  <summary> Click here to see the details </summary>

**Power Query**
> Power Query is used to clean, shape, and prepare your data before loading it into the model.

> It is tool from PowerBI which is really easy in order to do data cleaning.

Question is **Where we can find the Power Query?** <br/>
Well, we an open it only in ribbon if you go to `Home` then we have something called `Transform data` then list of few things like 
`Transform data | Data Source Setting` we need `Transform data` when we click on it we will get a new window called `Power Query editor`. 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/852a2575-58ec-469b-a9bb-a33a83b2898c" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/e5a83faf-68d9-4536-a53e-3151501b16be" />


Now the Question is **What is Power Query?** <br/>
It is the first steps that we do to clean up and prepare data before it even goes to PowerBI.

You might get confused that we can do data transformationa and clean up using **DAX**.<br/>
**Why do we need Power Query?** <br/> 

**DAX** happens way after in the process and It is more focus on the mathematical and analytical formula then clean up the data. <br/>
**Power Query** is specialized in clean up the data before it goes to next step.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/ed7c6c3b-4eb4-4cfc-a0de-f40d71598711" />

Here we will not talk about each and every function, we will see it later on. <br/>
We have first name and last name columns both are seperated.<br/>
Let's merge the first name and last name through Power Query that's the requirement we have that merge both columns in one column i.e
customer_name. <br/>
So for both columns how can we so that `ctrl + select` > you will an action called `Merge Columns`. <br/>
If you click on it then `Merge Columns` will pop up and ask for seperator and new column name. <br/>
Now both of the columns disappear and now we have a new column named customer_name is there. <br/>

That's it we transform our data using Power Query.
In real project we do a lot of transformations sometime we might get lost where am I now, what am I changing that's why we have something
nice in the right side Properties section something called `Applied Steps`. <br/>
Each time we do anything to our data, PowerBI is going to record those steps in the Applied steps windows.

We have few default steps automatically created in Applied Steps which were created when we loaded the data into PowerBI.
Like : **Source**, which is created when we loaded the data into PowerBI, next one **Promoted Header**, first row of file is promoted as header

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/c5ed3184-d452-40a1-8f5c-33c7c74d5b40" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/67db0c73-8873-47cc-a032-4f575a7bc406" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f1cd947e-4b47-443a-8779-27b66419154a" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/5557581a-bb33-4063-883a-d63bab1abcd1" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f6820658-f6e1-4242-b352-c26232b88702" />


**Note : Make sure to save your work "Close and Apply"** otherwise if you directly closed the data transformations will not be saved! 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/8d5044fe-5ce8-4ad7-b796-9cfeec418f0a" />

Once you're done, PowerBI had done few transformations and now you can see the customer_name column and we don't have any first_name and last_name
columns in your Power Query Editor `Home > Data Transformation`.
Same thing if you switch back to  `Model View`, there you will not see those first_name and last_name column, you will see customer_name. <br/>
Basically transformations is done everywhere in PowerBI.

</details>


⚠️ **Saving the whole work is important**
<details>
  <summary>  How to Save your whole work ? </summary>

<br/>

So Before doing any other work, Save our whole work what we have done in our PowerBI like Loading the file and transforming the data etc etc. <br/>
How to do it? <br/>
It's simple. Go to `File` > `Save as` choose the location where you want to save > `My First DashBoard` the type of data is `.pbix` extension file.
which is a PoweBI file. We have different types of PowerBI Files, use the default one `.pbix` bcuz it holds everything like Data, Model, Visuals.
Like project with only data, only model or only visual or everything. <br/>
Then save our work, now we have our newly created PowerBI file. <br/>
Now we can share our work with others like put it on Github or share it with your team member etc etc

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/cbefb1c8-10fc-4bcc-945e-2671cbb3c2b2" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/7d2667d7-c6ae-46f3-84f4-c7294d3b3986" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/889f2e47-f6ab-414e-a303-d06eaad50330" />
<br/>
<img width="350" height="350" alt="image" src="https://github.com/user-attachments/assets/5961deda-a147-41e3-94be-07ad9d054735" />

With that we have covered a very important component in PowerBI i.e. Power Query to clean up and prepare the data before entering PowerBI.

Next Step is most interesting one, we're going to build visuals : the reports and dashboards! <br/>
We will do that using Report View.

</details>

### 8. Report View (Data Visualization)  

<details>
  <summary> Click here to see the details </summary>

<br/>

**Data Visualization** <br/>
Everything we have done so far by connecting the data, data modeling and preparing and transforming the data, all those stuffs are actually 
invisible for the end users.

It is something that we do in background as preparation before we do visualization.

It is only this part where we build the visualization which is going to visible for end users. <br/>
Most of end user thinks why is it taking so much time to create visualization bcuz we have to go through all those phases before we start building
any report or dashboard.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/46759e89-764b-4e2c-8ab4-7671ca0ae1f6" />


Let's jump and start building our 1st Dashboard.

The first most important part is in the middle i.e. `Canvas` in this white area you're going to be adding the visuals. <br/>
Next moving on next, the most critical part in this interface is in the right side > we have 3 things  `Filters`, `Visualizations`, `Data` <br/>
Most important one is `Visualizations`. <br/>
In `Visualizations`, we have 2 tabs 1. `Build Visuals` 2. `format the visuals` <br/>
Let's go to `Build Visuals` here we have different types if visuals. <br/>
To pick one click on it. e.g. bar chart -> you can see in white area now we have like a box, you can drag it and put it wherever you want.This
visual is now empty, we don't have anything inside it yet. In order to fill the visual. <br/>
Go to area right side below the Build Visual. But that will only appear if we click on the visual in canva. <br/>
So in order to configure the visual we have to click on it and then we have to fill those info like `Y-axis`, `X-axis` etc to build the visual. 
<br/>
How to fill those informations, It ask you to **add data field here**  So go to the **data** section and start selecting what do you want 
drag and drop from data to those Add data fields. <br/>

E.g. We want to see product_name from the orders table on y-axis.

> Note : Usually when we build visuals, it needs dimensions and measures.

If we want to see total sales for the product names so put data sales and drag and drop to x-axis.


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f483d98e-32c0-45be-8631-da961e7279f5" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/51768f25-8f5b-4440-89be-60f6a719fd71" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/4a43971a-b711-4158-8e0f-ae5e06f7fe40" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/77a098fb-455f-42d1-81f7-a7d3f0d290f2" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/ce779b07-db5b-40d2-8753-b76897a3a84d" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/f9d04424-1d3d-4412-96b0-12bc37862668" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/5341fbf0-e078-4179-bad7-553c268f7fab" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/657bceef-d8db-4739-8c81-505c5c6bb4c4" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/2a5f9f4b-6d62-4ccd-b951-37f57c68012e" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/870bda9c-c255-4d1f-9ca7-cadc63fcd2c1" />

So with that we have created our first chart in PowerBI like by just drag and drop. <br/>
We can see all the products and amount of sales for each product using Bar chart

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/42a5424a-92ce-46e9-a891-1e1f5f67a030" />

With that we have done the first step **Build the Visual**.
Usually in next step we can go and format it like change the color, fonts , add borders, transparency and add like some enhancement to it. <br/>
Like for example change the Data Label. if you switch it on, you will start seeing numbers on the end of each bar.

<img width="350" height="350" alt="image" src="https://github.com/user-attachments/assets/953b47c4-1e00-466f-926a-a06e241a0a58" />

Not only we can change the visuals, we can also change the title of the whole visual or if you don't want title at all switch it off. <br/>
So we have a lot of options to format our chart.

<img width="350" height="350" alt="image" src="https://github.com/user-attachments/assets/2796ba81-fbf8-4bdf-9baf-1ff1c16e9728" />


Let's build another visuals bcuz usually Reports or Dashboards have like different visuals one for product wise total sales.
another visual for month wise total sales etc etc.

This time try **Donut Chart**, click on it, it is empty as we don't have anything. <br/>
Let's start building it. It needs a legends and values, which is different from what we have in Bar chart.<br/>
Let's take again sales and put in on values, But I would like to split the donut by the product_category. <br/>
So if we go, drag and drop it to the legends our donut is splitted by categories. <br/>
Now we can see most sales comes from Laptop categoty and we can see the values by percentage. <br/>

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/29ed9238-eec2-4cdb-8594-00ff795d1e49" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/9e9a5128-c89a-4254-bd5e-9d5df97aecd4" />


Now Let's go and add carts this is really easy to configure it only needs one field. <br/>
For example if we see big numbers of our business. <br/>
How many orders we have in the data? 
Suppose It says first_order_id, we don't need that. We would like to see whole aggregation on that column like how many orders. <br/>
If we go and click arrow over here, then go to count. <br/>
Now you can see 100 orders (aggregated data) in our business 

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/ce94f34c-3868-4328-a6ec-7345188e79ff" />
<br/>
<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/da555e93-3e0f-4713-9232-fc582ee438f3" />


If we want same thing again so we can also copy and paste it instead of again creatinng it and change the fields out there.
Like suppose we want to see all customers aggregated here in a cart.

</details>


</details>
<!-------------- Step#1 PowerBI Desktop ------------------->

# Step#2 PowerBI Services

<details>
  <summary> PowerBI <b> Services </b> </summary>

<br/>

</details>


<!-------------- Step#2 PowerBI Services ------------------->

# Step#3 PowerBI Mobile App

<details>
  <summary> PowerBI <b> Mobile App </b> </summary>

<br/>

</details>

<!--------------  Step#3 PowerBI Mobile App ------------------->
