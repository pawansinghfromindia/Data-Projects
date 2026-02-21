#  DBMS 🚀

## 1. Introduction to Databases

<details>
  <summary> <b> What is a Database ? </b> </summary>

### ⚡ What is Data ?

> Data is a collection of raw facts and figures that can be processed to produce meaningful information.

📌 **Examples of data**                     

| Numbers : 85, -1, 0, 1, 10100 | Text, char, String : "Ram", " ", 'a' | Dates : 21-02-2026 | 
|-------------------------------|--------------------------------------|--------------------|
| Measurements : 37°C           | Characters : 'A', 'z'     | Media : Images, Videos, Audio |
| Tables, Rows, columns,Objects | .csv, .excelsheet, binary files | etc                     |

📌 **Types of data**
|  1. Qualitative data          | 2. Quantitative data         |
|-------------------------------|------------------------------|
| Descriptive                   | Numerical                    |
| Example : color, name, gender | Example : marks, age, salary |

📌 **Data vs Information**
| Data          | Information                      |
| ------------- | -------------------------------- |
| Raw facts     | Processed and meaningful         |
| Unorganized   | Organized                        |
| Example: `85` | Example: “Rahul scored 85 marks” |


Every possible communication is data transmission, data is the most crucial part of the computer world


### ⚡ Database

Database is the **collection of organized data that is structured or unstructured**. 

The database's primary goal is ***to store a huge amount of data***.

Data can then be ***accessed, managed, updated, regulated, and organized*** efficiently. 

For writing and retrieving data, most databases utilize ***structured query language (SQL)***. 

Data is mostly managed by **DBAs**, **Data Scientists**, **Data Engineers**, **Data analysts**, **BI Developers** and
consumed by **Business Users**.

Examples of some databases: `MySQL`, `SQL Server`, `PostgreSQL`, `Oracle`, `MongoDB` etc.


### ⚡ Why Use a Database ?

> We use a database to efficiently store, organize, secure, and retrieve large amounts of data
while ensuring consistency and reliability.

1. **Organized data storage** : structured form (tables, rows, columns)
2. **Fast data retrieval** : quickly search and filter data using queries.
3. **Data consistency & integrity** : no duplicate, primary keys constraints
4. **Security** : authentication, authorization, role-based access, encryption
5. **Multi-user access (concurrency)** : access data at the same time without corruption
6. **Transaction management (ACID)** : Atomicity, Consistency, Isolation, Durability
7. **Backup & recovery** : recover data after crashes, power failure, system errors


#
</details>
<!------------------------------------>
<details>
  <summary> <b> What is DBMS (Database Management System)?</b> </summary>

> A Database Management System (DBMS) is a specialized software application crafted for the purpose of efficiently organizing, storing, and retrieving data in a structured format.

Empowers users to seamlessly create, update, and retrieve information from a database,

Provides robust tools for overseeing security measures and access controls within the database environment.

### 🧩 Key Features of DBMS
DBMS encompasses essential features crucial for efficient data management

**1. Data Modeling**

DBMS facilitates the creation and modification of data models, defining the structure and relationships within the database.

**2. Data Storage and Retrieval**

Responsible for storing and retrieving data, DBMS provides diverse methods for efficient searching and querying.

**3. Concurrency Control**

DBMS includes mechanisms ensuring concurrent access, allowing multiple users to interact with the data simultaneously without conflicts.

**4. Data Integrity and Security**

Tools within DBMS enforce data integrity and security constraints, validating data values and implementing access controls.

**5. Backup and Recovery**

DBMS offers mechanisms for data backup and recovery, safeguarding against system failures and ensuring business continuity.

**6. Classification of DBMS**

- Relational Database Management System (**RDBMS**)
  - Organizes data in tables with rows and columns.
  - Establishes relationships between tables using primary and foreign keys.
  - Example : `MySQL`, `Oracle`, `PostgreSQL`, `SQL Server`, `mariaDB` etc

- Non-Relational Database Management System (**NoSQL**)
  - Organizes data in diverse structures like key-value pairs, documents, graphs, or column-based formats.
  - Tailored to handle large-scale, high-performance scenarios efficiently.
  - Example : `MongoDB`, `SQLite`, `Redis`, `Cassandra`, `Elasticsearch`


### 📦 Use Cases of DBMS
DBMS is used in a variety of applications and industries to efficiently manage and organize data.

- **Business Operations**
- **Customer Interaction:]**
- **E-commerce**
- **Educational Institutions**

### ⚡Advantages of DBMS

- **secure** due to the authentication and user authorization and **reliable** in storing the data
- offers functionality to remove and **minimize the data redundancy** with the help of **normalization** techniques
- provides **different data views for different users**.
- facilitates to take **backup and recover the lost data** in DBMS
- **ACID properties ensure healthy transactions**
- can be **integrated with Python, Java, or any other programming language** 





#
</details>
<!------------------------------------>
<details>
  <summary> <b> Types of Databases </b> </summary>

### 🧬 Evolution of Database (DBMS)

**1. File System (Pre-1960s)** 📁 <br/>
`Data stored in separate files, Each application managed its own data. led to the need for DBMS` 

**2. Hierarchical Database (1960s)** 🌳 <br/>
`Structure : Tree-like (parent → child) e.g. : One-to-many relationship`

**3. Network Database (1970s)** 🕸️ <br/>
`Structure : Graph-like (records connected by links) e.g. : Supports many-to-many relationships` 

**4. Relational Database (1970s–Present)** 🗄️ <br/>
`Structure : Tables (rows & columns) e.g. : MySQL, Oracle, PostgreSQL, SQL Server`

**5. Object-Oriented Database (1980s–1990s)** 🧩 <br/>
`Store data as objects (like OOP) e.g. Supports inheritance Encapsulation, Complex data types`

**6. NoSQL Databases (2000s–Present)** 🚀 <br/>
`Key–Value, Document, Column-family, Graph e.g. : MongoDB, Cassandra, Redis, HBase`

**7. NewSQL / Distributed SQL (Modern)** ⚡ <br/>
`SQL consistency + NoSQL scalability e.g. : Google Spanner, TiDB`



<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/8c81200b-3d95-426f-9cc1-ae40dee7f75b" />

<br/>


###  RDBMS 🆚 NoSQL

| Feature           | **RDBMS**                             | **NoSQL**                                |
| ----------------- | ------------------------------------- | ---------------------------------------- |
|                   | **Relational Database Management System** | **Not Only SQL**                             |
| Data model        | Tables (rows & columns)                   | Key–Value, Document, Column, Graph       |
| Schema            | Fixed (predefined)                        | Flexible / dynamic                       |
| Data type         | Structured data                           | Structured + Semi + Unstructured         |
| Scalability       | Vertical scaling (scale-up)               | Horizontal scaling (scale-out)           |
| ACID support      | ✅ Strong ACID                           | ⚠️ Usually BASE (some support ACID)      |
| Query language    | SQL                                       | No standard query language               |
| Joins             | ✅ Supported                             | ❌ Limited / avoided                      |
| Consistency       | Strong consistency                        | Eventual consistency (common)            |
| Performance       | Good for complex queries                  | Excellent for big data & high throughput |
| Best for          | Banking, ERP, OLTP                        | Big data, real-time apps, social media   |
| Design complexity | Easier to design                          | Requires careful data modeling           |
| Examples          | MySQL, Oracle, PostgreSQL                 | MongoDB, Cassandra, Redis                |


#
</details>
<!------------------------------------>
<details>
  <summary> <b> DBMS Architecture </b> </summary>

- DBMS Architecture is crucial for efficient data management and system performance.

- It involves the database's design, development, and maintenance, determining how users interact with and access the system. 

### 🥉 Types of DBMS Architecture

> **One-Tier Architecture** (Single-tier)

User directly interacts with the database

> **Two-Tier Architecture** (Client–Server)

Client talks to database server directly

> **Three-Tier Architecture**

Separates system into three layers.

🧱 Three Layers

**1. Presentation Layer** (Client/UI)

What it does is **Shows interface to user** and **Takes input**

Examples : `Web browser, Mobile app, Frontend UI`


**2. Application Layer** (Business Logic), brain of the app

What it does is **Processes requests**, **Applies business rules**, **Validates data** and **Talks to DBMS**

Examples : `Java backend, Node.js server, Python API`


**3. Database Layer**

What it does **Stores data**, **Executes queries** and **Manages transactions**

Examples : `MySQL, PostgreSQL, Oracle, MongoDB`


Why Three-Tier Architecture is Best is bcuz of **High security, Highly scalable, Easy maintenance, Better performance, Reusable business logic**
That’s why almost all modern apps use it.

<img width="377" height="575" alt="image" src="https://github.com/user-attachments/assets/36ed1ec4-c220-41a1-a65c-8c978d0197ad" />


#
</details>
<!------------------------------------>
<details>
  <summary> <b> Relational and Non Relational Databases </b> </summary>

<br/>

Deciphering the distinctions between relational and non-relational databases is crucial.

<details>
  <summary> <b> - Relational Databases </b> </summary>

<br/>

A relational database or relational database management system(RDBMS) stores data in the form of a table. 

The ***table consists of rows(records) and columns(fields)***, and in a relational database.

Each table has a special column that contains only distinct and unique values that are called **primary key**. <br/>
This primary key is used to define the relationship between the tables. Similarly we have **Foreign key**

The most widely and popular way of interacting with a relational database is **SQL(Structural Query Language)**, which allows access, filter, and modify data.

### Popular Relational Database
- MySQL
- Oracle Database
- Microsoft SQL Server
- PostgreSQL
- SQLite
- MariaDB

### Advantages of Relational Databases

> **ACID Compliance**

4 properties, i.e., Atomicity, Consistency, Isolation, and Durability.

The ACID properties, in totality, provide a mechanism to ensure correctness and consistency of a database in a way such that each transaction is a group of operations that acts a single unit, produces consistent results, acts in isolation from other operations and updates that it makes are durably stored.

**Atomicity** : It refers to the integrity of the database transaction <br/>
Each transaction is considered as one unit, and either runs to completion or is not executed at all

**Consistency** : It refers to the correctness of a database. <br/>
 Integrity constraints must be maintained so that the database is consistent before and after the transaction. 

 **Isolation** : It refers to the ability to concurrently process multiple transactions in a way that one does not affect another. <br/>
Changes occurring in a particular transaction will not be visible to any other transaction until that particular change in that transaction is written to memory or has been committed. 

**Durability** : This property ensures that once the transaction has completed execution, the updates and modifications to the database are stored in and written to disk and they persist even if a system failure occurs.



> **Normalization**

Normalization is a database design technique that **reduces data redundancy** and eliminates undesirable characteristics like **Insertion, Update, and Deletion Anomalies**.

Normalization rules divide larger tables into smaller tables. Their purpose is to eliminate redundant data and ensure data is stored logically.


> **Data Accuracy**

**Tables** consist of **primary and foreign keys**, which ensures that no duplicate data is present in data. 

> **High Security**

In a relational database, we can divide the data among tables, and we can divide the tables as confidential or not.

We can make our data (large volume of data) safe by making some tables as confidential and some as public depending on the access given.


### Disadvantages of Relational Databases

**Loss of Information**

Data might loss during migration from one system to another.

**Expensive**

**Slow Performance**

#
</details>


<details>
  <summary> <b> - Non-Relational Database </b> </summary>

<br/>

**Non-Relational Databases** are also called **No-SQL databases**, that doesn't require any table, fields, or records.

NoSQL databases are completely different from SQL databases and work differently. <br/>
It has to ***deal with semi-structured or unstructured data***.

Rather than containing tables, it consists of files within various folders. <br/>
They can possess any kind of data, whether JSON, XML, etc. <br/>
So, **creating and managing data in NoSQL is easy and faster**.

Example : **Facebook(Meta)** is a very popular example of using NoSQL databases.


### Types of Non-relational database

- Documents Databases.

- Graph Databases.

- Wide Column Databases.

- Key-value Databases.

### Popular Non Relational Database (NoSQL)

e.g. : **MongoDB** | **Apache Cassandra** | **Redis** | **Neo4** etc

<img width="317" height="102" alt="image" src="https://github.com/user-attachments/assets/0e439bef-05a1-438d-a759-1bcd6599d3f7" /> 
<img width="317" height="102" alt="image" src="https://github.com/user-attachments/assets/91c219d9-28c3-42be-88a8-c01499b87e13" />
<br/>
<img width="317" height="102" alt="image" src="https://github.com/user-attachments/assets/e3c44127-04f9-4ffd-80ae-510212ffa8c2" />
<img width="317" height="102" alt="image" src="https://github.com/user-attachments/assets/ec1786c3-dadd-49f4-acde-5e29d3b14569" />


### Advantages of Non-Relational Databases

**Structured + Unstructured Data**, **Large Data & Cheap** and **Performance & Fast**

can store both structured and unstructured

can scale to accommodate any type of data while maintaining a low cost.

#
</details>



#
</details>


---

## 2. Data Models in DBMS


<details>
  <summary> <b> Data Models in DBMS </b> </summary>

### Data Model

Without a defined data model, there is a **risk of data inconsistency and redundancy**, which can **lead to poor data quality**.

A data model **helps organize, define, and access data within a DBMS by providing a clear structure that acts as a blueprint for efficient data management**. 

Data models in DBMS help to understand the design at the conceptual, physical, and logical levels as it provides a clear picture of the data making it easier for developers to create a physical database.

There are many types of data models that are used in the industry. 

At the conceptual level, a conceptual data model is a high-level, abstract representation that captures business requirements, key entities, and relationships without technical details, making it useful for stakeholder communication.

### Types of Data Models in DBMS

<details>
  <summary> 1. <b> Hierarchical Model </b> </summary>

<br/>

Hierarchical data model is one of the oldest data models, where **data is organized in a hierarchical tree-like structure**.

In such a structure, each record in DBMS is represented as a node, where a parent node organizes and connects to its child nodes, establishing a clear **parent-to-child hierarchy**. 

A parent record can have multiple child records, but each child record has only one parent record,

The drawback of Hierarchical data model is we can only have **one too many relationships** under this model, **not many to many**
Hence the hierarchical data model is very rarely used nowadays.


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/66d6664d-8493-4151-b861-c1f0bd385318" />


</details>

<details>
  <summary> 2. <b> Network Model </b> </summary>

<br/>

A network data model is a flexible way to represent complex relationships between data entities.

A network model is **nothing but a generalization of the hierarchical data model** as this data model allows **many to many relationships**; therefore, in this model, a record can also have more than one parent.


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/4769a72e-4870-407b-9650-ae6d153dc7cd" />


</details>


<details>
  <summary> 3. <b> Entity-Relationship Model (ER Model)</b> </summary>

<br/>

An Entity-Relationship model is a high-level data model that describes the structure of the database in a pictorial form which is known as ER-diagram. 

In simple words, an ER diagram is used **to represent logical structure of the database easily**.

ER model develops a conceptual view of the data. Hence it can be **used as a blueprint to implement the database** in the future.

Developers can easily understand the system just by looking at ER diagram. 


### Let's see ER-Diagram

> **Entity**

- Anything that has an independent existence about which we collect the data. 
- They are represented as **rectangles** in the ER diagram.
- For example - Car, house, employee.

> **Entity Set**

- A **set of the same type of entities** is known as an entity set.
- For example - Set of students studying in a college

> **Attributes**

- **Properties that define entities** are called attributes.
- They are represented by an **ellipse shape** in the ER diagram.

> **Relationships**

- A relationship in DBMS is used to **describe the association between entities**.
- They are represented as **diamond or rhombus shapes** in the ER diagram.


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/8c2be74f-56f1-44ca-9dda-934082f25021" />


</details>

<details>
  <summary> 4. <b> Relational Model </b> </summary>

<br/>


</details>

<details>
  <summary> 5. <b> Object-Oriented Data model </b> </summary>

<br/>

</details>

<details>
  <summary> 6. <b> Object + Relational Data Model </b> </summary>

<br/>

**Object-relational data model** is an ***integration of the object-oriented model and the relational model***. 

Since it inherits properties from both of the models it supports objects, classes, etc like object-oriented models, and tabular structures like the relational model.

It provides data structures and operations used in the relational model and also provides features of object-oriented models like classes, inheritance, etc.


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/cc31de33-0de1-4e74-8c08-cd9fe7a1a4e0" />

<br/>

The only drawback of this data model is that it is complex and quite difficult to handle.

</details>

<details>
  <summary> <b> Data Modeling Abstraction Levels </b> </summary>

<br/>

Data modeling abstraction levels are fundamental in designing and managing a database’s logical structure. 

By breaking down the process into different levels, database designers can focus on specific aspects of the data, making it easier to organize, represent, and implement complex data systems. 

> **1. Conceptual Level**

The focus is on defining what data needs to be stored and how different data entities relate to each other, without worrying about how the data will be physically stored or accessed. 

Typically represented using Entity-Relationship (ER) diagrams, which visually map out entities, their attributes, and the relationships between them. 

Ensures that the database model accurately reflects the business requirements and provides a clear foundation for further design.

> **2. Logical Level**

The conceptual design is translated into a logical structure that can be implemented in a database management system.

Focus to organizing data into tables, defining columns, specifying data types, and establishing relationships such as primary and foreign keys. 

Ensures that the logical structure of the database supports the required data access patterns and maintains data integrity.

> **3. Physical Level**

Abstraction to deal with how data is actually stored on disk and accessed by the system. 

Involves decisions about data storage formats, indexing, partitioning, and other performance optimizations. 

Ensuring efficient data storage and retrieval 

Essential for optimizing performance, scalability, and reliability in large-scale data environments. 

</details>

<details>
  <summary> <b> Applications of Data Models </b> </summary>

Data models play a vital role in a wide range of applications across the data industry, from designing robust databases to powering advanced analytics and business intelligence solutions.

In database design, data models serve as blueprints for creating relational data models, hierarchical models, and other types of data models. 

Data model helps ensure data integrity, minimizes data redundancy, and supports efficient data access.

Data models in data warehousing, to define how large volumes of data from different sources are integrated and stored for analysis. Using models like the `star schema or snowflake schema`, organizations can design data warehouses that support fast and flexible reporting. <br/>
This enables businesses **to analyze trends, monitor performance, and make data-driven decisions.***

</details>

> Data models in DBMS are used to represent the logical structure of the database.

> Several types of data models exist with their own advantages and limitations.

> ER model, Relational model, and Object-oriented model are among the most popular data models in DBMS.

#
</details>
<!------------------------------------>
<details>
  <summary> <b> Relational Model in DBMS </b> </summary>

<br/>

> Relational Model is the most widely accepted data model. 

In this model, the database is represented as a collection of relations in the form of rows and columns of a two-dimensional table. 

The overall structure and organization of these relations is defined by the database schema, which acts as the structural blueprint specifying how data is organized, related, and constrained within the database. 

The relational model in DBMS is a data model that stores information in the form of tables (relations) consisting of rows (tuples) and columns (attributes), where data is accessed and managed using SQL.

Each table represents a real-world entity, and relationships between tables are maintained using keys.

Table = Rows + Columns
| Student_Id	| Name	| Dept   | Age  |
|-------------|-------|--------|------|
| 101	        | Mohan	| CSE    | 20   |
| 102	        | Rohan	| ECE    | 21   |
| 103	        | Manoj	| IT     | 20   |
| 104	        | Saroj |	ME     | 18   |

The relation is the STUDENT table

Each tuple is a row such as (101, Mohan, 20, CSE)

Attributes are Student_ID, Name, Age, and Dept

Domains define allowed values (Age must be numeric, Dept must be valid)

This structured format allows efficient querying and easy updates.


| Term	         |  Meaning                                   |
|----------------|--------------------------------------------|
| Relation       |	A table that stores data                  |
| Tuple or field | A single row in a table                    |
| Attribute      |	A column in a table                       |
| Domain	       | The set of allowed values for an attribute |
| Schema	       | The logical structure of a relation        |


#
</details>
<!------------------------------------>
<details>
  <summary> <b> Relational Model Constraints </b> </summary>


<br/>

Integrity constraints in Relational Data Model are 
- `Primary keys`,
- `Foreign keys`,
- `NOT NULL`,
- `UNIQUE`,
- `CHECK` 

These rules ensure data accuracy and integrity, preventing issues such as duplicate records, invalid references, or missing critical information.

#
</details>
<!------------------------------------>
<details>
  <summary> <b> DBMS Keys: Primary, Candidate, Super, and Foreign Key </b> </summary>


### 🔑 Keys

Keys are used to uniquely identify any record or row of data from the table. 

It is also used to establish and identify relationships between tables.

Keys are of different types eg: Super key, Candidate key, Primary Key, Foreign key, etc.

### 🎯 What are keys in DBMS?

Keys in DBMS are introduced to avoid redundancy in data. 

Keys in DBMS can be single or a group of attributes that uniquely identify the records. 

Using all attributes as a key is less efficient than choosing the minimum combination of attributes that provide the same result.

### 🎯 Why do we need DBMS Keys?

Keys in DBMS help ensure data integrity and consistency by uniquely identifying each record in a table.


#### 🎯 Types of DBMS Keys

Mainly we’ve 8 different keys in DBMS. 

- `Super Key`
- `Candidate Key`
- `Primary Key`
- `Alternate Key`
- `Foreign Key`
- `Composite Key`
- `Compound Key`
- `Surrogate Key`

| enroll_id | student_id | roll_no | email                             | course_id | semester | dept_id |
| --------- | ---------- | ------- | --------------------------------- | --------- | -------- | ------- |
| 1         | 101        | CS001   | [a@gmail.com](mailto:a@gmail.com) | C101      | 1        | D10     |
| 2         | 102        | CS002   | [b@gmail.com](mailto:b@gmail.com) | C102      | 1        | D20     |
| 3         | 101        | CS001   | [a@gmail.com](mailto:a@gmail.com) | C103      | 2        | D10     |


🔑 **1. Super Key**

Everything we learned above is nothing but a super key.

A super key is a set of all the keys (with single or multiple attributes) which can uniquely identify the records of the table.

| A	   | B	  | C    |
|------|------|------|
|      |     	|      |
|      |     	|      |


We’ve 3 attributes, A, B, and C

A possible set : ABC, AB, AC, BC, A, B, C

we can use any of those to identify the record.

It’s a good choice to go with a single value, we can fetch all other values whereas, in other available keys, we should know 2 or 3 attributes beforehand to fetch values of all other attributes. Keep this in mind.

🔑 **2. Candidate key**

From all the super keys available, the candidate key is the one whose proper subset is not a super key.

Given ABC key, we’re saying if we find its proper subset, i.e., {A, B, C, AB, AC, BC} and any of them can be a key, then ABC can’t become a candidate key.

AB, which comes from the proper subset of ABC, is also a key. Therefore, ABC is not a candidate key.

Therefore, at last, we found that A is the ONLY candidate key available for the above schema.

we can also have multiple candidate keys. 


🔑 **3. Primary key**

We learned to find candidate keys from a set of super keys. 

Now, the primary key is nothing but a candidate key which has given the right to be called the primary key.

All other candidate keys can also be used as a primary key, but the database administrator (or you) can choose a single key out of those to be a primary key. 

We can use the primary key to uniquely identify the records of a table.


🔑 **4. Alternate key**

We learned the primary key is nothing but a candidate key given primary key rights. 

But what do we call all other candidate keys? <br/>
Yes, you’re right. We call them alternate keys. 

Alternate keys are nothing but candidate keys that don’t get rights of the primary key.

🔑 **5. Foreign key**

In order to relate 2 tables with each other, we use the foreign key. 

We make the primary key of a table as a foreign key in another table of interest.


🔑 **6. Composite key** 

When we make a primary key which consists of 2 columns(attributes), it is referred  as a composite key.

```sql
(student_id, course_id, semester)
```


🔑 **7. Compound key**

Composite key made specifically of foreign keys.

student_id (FK)

course_id (FK)

🔑 **8. Unique key**

Unique key looks very similar to primary key but they’re not and have a very different usage altogether. 

Once we set an attribute as a unique key then its column value should be unique, although only ONE value could be `NULL` on the otherhand Primary Key can't be `NULL`.

A unique key can be applied to multiple columns (attributes), not just one like in the primary key. 

And we can even modify the unique key column (attribute), which is not possible in the case of the primary key.


🔑 **9. Surrogate key**

A surrogate key is a unique identifier that uniquely identifies the object or entity. 

Surrogate key is Artificial/system-generated key.

```sql
enroll_id (AUTO_INCREMENT)
```

It is used for representing the existence of data analysis. 

It represents an outside entity as a database object but is not visible to the user and application.




**Summary**
|                                 Keys                                                           |
|------------------------------------------------------------------------------------------------|
| Super Key → Any unique column out of all columns                                               |
| Candidate Key → Minimal unique column who is not in proper subset of Super keys                |
| Primary Key→ Chosen candidate keys froma all candidate keys                                    |
| Alternate Key → Remaining candidates who didn't get selected as Primary Key                    |
| Foreign Key → References another table out of 2 related table                                  |
| Composite Key → when we make a key (PK) by combining Multiple columns                          |
| Unique Key → Similar to primary key but not, it can be multiple, can modify, can hold one Null |
| Surrogate Key → Artificial/system-generated key from unique keys                               |


---

#
</details>

<!------------------------------------>
<details>
  <summary> <b> Relational Calculus in DBMS </b> </summary>

<br/>

Relational calculus, a **non-procedural query language** in database management systems, guides users on what data is needed without specifying how to obtain it.


Before understanding Relational calculus in DBMS, we need to understand **Procedural Language** and **Declarative Langauge**.

> **Procedural Language**

- Those Languages which clearly define how to get the required results from the Database are called Procedural Language.
- Relational algebra is a Procedural Language.

> **Declarative Language** 

- Those Language that only cares about What to get from the database without getting into how to get the results are called Declarative Language.
-  Relational Calculus is a Declarative Language.

So Relational Calculus is a Declarative Language that uses Predicate Logic or First-Order Logic to determine the results from Database.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/911c8cb4-e73a-445c-8c56-5295a72f5da8" />


**Tuple Relational Calculus (TRC)**

Tuple Relational Calculus in DBMS uses a tuple variable (t) that goes to each row of the table and checks if the predicate is true or false for the given row. 

Depending on the given predicate condition, it returns the row or part of the row.

Syntax :
```
{t \| P(t)}   
```
Where t is the tuple variable that runs over every Row, and P(t) is the predicate logic expression or condition.

| Customer_id	| Name	| Zip code |
|-------------|-------|----------|
| 1	          | Rohit	| 12345    |
| 2	          | Rahul	| 13245    |
| 3	          | Rohit	| 56789    |
| 4           |	Amit	| 12345    |

Example 1: Write a TRC query to get all the data of customers whose zip code is 12345.

TRC Query:
```
{t \| t ∈ Customer ∧ t.Zipcode = 12345}

--OR

 {t \| Customer(t) ∧ t[Zipcode] = 12345 }
```
| Customer_id	| Name	| Zip code |
|-------------|-------|----------|
| 1	          | Rohit	| 12345    |
| 4.	        | Amit	| 12345    |


**Domain Relational Calculus (DRC)**

Domain Relational Calculus uses domain Variables to get the column values required from the database based on the predicate expression or condition.

Syntax:
```
{<x1,x2,x3,x4...> \| P(x1,x2,x3,x4...)} 
```
where, `<x1,x2,x3,x4...>` are domain variables used to get the column values required, 
and `P(x1,x2,x3...)` is predicate expression or condition.


Example 1: Write a DRC query to get the data of all customers with Zip code 12345.

DRC query: 
```
{<x1,x2,x3> \| <x1,x2> ∈ Customer ∧ x3 = 12345 }
```

**Summary of Relational Calculus**
- Relational Calculus in DBMS tells us what we want from the database and not how to get that.

- Relational Calculus is a Declarative Language.

- TRC uses tuple variable and checks every Row with the Predicate expression condition.

- DRC uses domain variables and returns the required attribute or column based on the condition.

- For any requirement both, TRC and DRC can be written.

- TRC and DRC queries can give more than one tuple or attribute in the result.

#
</details>

<!------------------------------------>
<details>
  <summary> <b> Relational Algebra in DBMS </b> </summary>

<br/>

Relational algebra in DBMS is a **procedural query language**. <br/>
Queries in relational algebra are performed using **operators**.  <br/>
Relational Algebra is the fundamental block for modern language SQL and modern Database Management Systems such as 
`Oracle Database`, `Mircosoft SQL Server`, `IBM Db2`, etc.


Relational Algebra in DBMS is ***a theoretical model which is the fundamental block for SQL***. 

It comprises different ***mathematics operations***.

Operations are divided into two main categories: **Basic** and **Derived**.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/478e517b-5fe9-4355-bdb7-50423428c787" />



Basic consists of six Operations: `SELECT`, `PROJECT`, `UNION`, `SET DIFFERENCE`, `CARTESIAN PRODUCT`, `RENAME`.

Derived Consist of three Operations: `JOINS`, `INTERSECTION`, `DIVISION`.

Joins are of two types: 
- Inner Join
   - Theta Join
   - Equi Join
   - Natural Join
- Outer Join
  -  Left Outer Join
  -  Right Outer Join
  -  Full Outer Join.

### 🎯 Basic Operations

- **Select (σ)** is used to retrieve tuples(rows) based on certain conditions.

- **Project (∏)** is used to retrieve attributes(columns) from the relation.

- **Union (∪)** is used to retrieve all the tuples from two relations.

- **Set Difference (-)** is used to retrieve the tuples which are present in R but not in S(R-S).

- **Cartesian product (X)** is used to combine each tuple from the first relation with each tuple from the second relation.

- **Rename (ρ)** is used to rename the output relation.



### 🎯 Derived Operations

- **Theta Join (θ)** combines two relations based on a condition.

- **Equi Join** is a type of Theta Join where only equality condition (=) is used.

- **Natural Join (⋈)** combines two relations based on a common attribute (preferably foreign key).

- **Left Outer Join (⟕)** returns the matching tuples and tuples which are only present in the left relation.

- **Right Outer Join (⟖)** returns the matching tuples and tuples which are only present in the right relation.

- **Full Outer Join (⟗)** returns all the tuples present in the left and right relations.


#
</details>

<!------------------------------------>
<details>
  <summary> <b> SQL Commands: DDL, DML, DCL, TCL, DQL </b> </summary>

### 🚀 DDL(Data Definition Language)

DL commands are used to create and modify the structure of a database and database objects. 

These commands are `CREATE`, `DROP`, `ALTER`, `TRUNCATE`, and `RENAME`.

```sql
-- CREATE
CREATE DATABASE database_name;

CREATE TABLE table_name(
    first_name varchar(20),
    age INT
);

-- DROP
DROP TABLE table_name;

DROP DATABASE database_name;

-- ALTER
ALTER TABLE table_name
ADD column_name data_type;

ALTER TABLE table_name
DROP COLUMN column_name;

ALTER table_name MODIFY column
first_name varchar(25);


-- TRUNCATE
TRUNCATE TABLE table_name;
SELECT * FROM table_name;

-- RENAME
RENAME TABLE table_name TO new_table_name;
```

### 🚀 Data Manipulation Language (DML)

DML is used for inserting, deleting, and updating data in a database. 

It is used to retrieve and manipulate data in a relational database. 

It includes `INSERT`, `UPDATE`, and `DELETE`.

```sql
-- INSERT
INSERT INTO table_name
(col1, col2, ...)
VALUES(val1, val2, ...)

-- UPDATE
UPDATE table_name
SET column1 = val1,
column2 = val2,
...
WHERE CLAUSE;

UPDATE table_name
SET age = age + 1;


-- DELETE
DELETE FROM table_name
WHERE CLAUSE;

```

### 🚀 Data Query Language (DQL)

DQL commands are used for fetching data from a relational database. 

They perform read-only queries of data.

`SELECT` is equivalent to the **projection operation** in relational algebra

```sql
-- SELECT
SELECT
     column1 as c1,
     column2 as c2,
     column3,
     .......
FROM table_name;

SELECT * FROM table_name;

SELECT * FROM table_name WHERE age>20;

SELECT * FROM table_name WHERE like "Ram";

```

### 🚀 Data Control Language (DCL)

DCL is used to access the stored data. 

It is used to `revoke` and `grant` the user the required access to a database.

<img width="626" height="607" alt="image" src="https://github.com/user-attachments/assets/f4744bfa-1aab-4768-a7fb-aacc1375bf3f" />

> **`GRANT`**

GRANT is a command used to provide access or privileges on the database objects to the users.

1. Granting `SELECT` Privilege to user on a table 
```sql
GRANT SELECT
ON tableName
TO 'userName'@'localhost';
```

2. Granting multiple privileges to a user
```sql
GRANT SELECT, INSERT, DELETE, UPDATE
ON tableName
TO 'userName'@'localhost';
```

3. Granting all the privileges to a user
```sql
GRANT ALL
ON tableName
TO 'userName'@'localhost';
```

4. Granting a privilege to all users
```sql
GRANT SELECT
ON tableName
TO '*'@'localhost';
```

> **`REVOKE`**

Once you have granted privileges, you may need to revoke some or all of these privileges. 

To do this, you can run a revoke command. 

You can revoke any combination of `SELECT, INSERT, UPDATE, DELETE, REFERENCES, ALTER, or ALL`.

```sql
REVOKE privileges
ON object
FROM user;
```

```sql
REVOKE DELETE
ON tableName
FROM userName;
```

```sql
REVOKE ALL
ON tableName
FROM userName;
```


### 🚀 Transaction Control Language (TCL)

TCL includes statements that are used to manage the changes that are made from DML statements. 

It enhances the transactional nature of SQL. 

The TCL commands in SQL are : `COMMIT`, `ROLLBACK`, `SAVEPOINT`

**1. `COMMIT`**

It's a SQL command used in the transaction tables or database to make the current transaction or database statement permanent.

If we have successfully executed the transaction statement or a simple database query, we want to make the changes permanent.
We need to perform the commit command to save the changes, and these changes become permanent for all users. 

```sql
COMMIT;
```


**2. `ROLLBACK`**

Undo any changes made to the database. 

`ROLLBACK` is the SQL command that is used for reverting changes performed by a transaction.

When a `ROLLBACK` command is issued it reverts all the changes since the last `COMMIT` or `ROLLBACK`.

```sql
ROLLBACK;
```

**3. `SAVEPOINT`**

`SAVEPOINT` command creates a point in your transaction to which you can roll back. 

It is a command in SQL that is used with the rollback command. 

It is a command in Transaction Control Language that is used to mark the transaction in a table.

```sql
SAVEPOINT some_name;
```

#
</details>

<!------------------------------------>
<details>
  <summary> <b> Integrity Constraints in DBMS </b> </summary>

<br/>

In Database Management Systems, integrity constraints are pre-defined set of rules that are applied on the table fields(columns) or relations **to ensure that the overall validity, integrity, and consistency** of the data present in the database table.


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/7c3babf5-063b-43e1-aab5-ebbcfc2f3d96" />


Constraints are rules that ensure data accuracy, consistency, and integrity in a relational database.

> **Primary Key**

A primary key uniquely identifies each tuple in a relation and cannot be NULL.    

Example : Student_ID uniquely identifies each student.

> **Foreign Key**

A foreign key establishes a relationship between two relations by referencing a primary key.    

Example : Student_ID in a COURSE table referencing STUDENT(Student_ID).

> **Domain Constraint**

Ensures that attribute values belong to a defined domain.    

Example : Age must be a positive integer.

> **Entity Integrity Constraint**

Ensures that the primary key value cannot be NULL.   

Example : A student record without Student_ID is invalid.

> **Referential Integrity constraint**

Ensures foreign key values correspond to existing primary key values.    

Example : A course cannot reference a non-existent student.


Integrity constraints in Relational Data Model are 
- `Primary keys`,
- `Foreign keys`,
- `NOT NULL`,
- `UNIQUE`,
- `CHECK` 

These rules ensure data accuracy and integrity, preventing issues such as duplicate records, invalid references, or missing critical information.


#
</details>

<details>
  <summary> <b> Disadvantages of the Relational Model </b> </summary>

<br/>

**1. Performance issues with very large joins**

When data is spread across many related tables, queries often require ***multiple joins***. 

As the database grows, these joins can become computationally expensive, leading to slower performance, especially in complex reporting or analytics.

**2. Rigid schema that is hard to modify**

Relational databases require a **predefined schema**.

Changing the structure (adding/removing columns or tables) often requires:
- [x] Schema migrations
- [x] Updating dependent applications
- [x] Possible downtime

This makes the model less flexible when requirements change frequently.

**3. Not suitable for unstructured data like images or videos**

Relational databases are designed for structured, tabular data not unstructured data such as :
- [x] Images
- [x] Videos
- [x] Audio files
- [x] Social media content

Such data is better handled by **NoSQL databases** or object storage systems, which are built for flexible and large-scale unstructured data.

</details>

<details>
  <summary> <b> Applications of the Relational Model </b> </summary>

<br/>

commonly used in systems where data accuracy, consistency, and reliability are extremely important.

#### ⚡ 1. Banking Systems
Banks handle highly sensitive data such as customer details, account balances, and transactions.    

The relational model ensures:

- **Data integrity through constraints** (no invalid or duplicate records)

- **ACID properties** for safe transactions

- Accurate relationships between customers, accounts, and transactions

This makes it ideal for handling financial operations where errors are unacceptable.


#### ⚡ 2. University Databases
Universities manage structured data like students, courses, faculty, grades, and attendance.    

The relational model helps by:

- Clearly defining relationships (student–course–faculty)

- Ensuring consistency of academic records

- Making it easy to query data for reports, results, and administration


#### ⚡ 3. Inventory Management Systems
Inventory systems track products, suppliers, stock levels, and orders.    

Using a relational model allows:

- Accurate stock updates

- Prevention of data anomalies (such as negative stock)

- Easy reporting on sales, purchases, and inventory status

This ensures smooth supply chain operations.

#### ⚡ 4. Enterprise and ERP Applications
Enterprise Resource Planning (ERP) systems integrate data across departments such as HR, finance, sales, and operations.   

The relational model:

- Maintains strong relationships between multiple business entities

- Ensures data consistency across the organization

- Supports complex queries and analytics needed for decision-making

Its consistency and structure make it ideal for mission-critical applications.

</details>

---

## 3. Normalization in DBMS

<!------------------------------------>
<details>
  <summary> <b> Functional Dependency in DBMS </b> </summary>

<br/>

- A **functional dependency** is **a relationship between columns(attributes) where one column(attribute) uniquely determines another**.

- If you know column A and can uniquely find column B, then A → B means A determines B.

### 🧩 Types of Functional Dependency

1. Trivial Functional Dependency

When right side is part of left side.
```
(student_id, name) → name
```

2. Non-Trivial Functional Dependency

Right side is NOT part of left side.
```
student_id → email
```

3. Fully Functional Dependency

When column(attribute) depends on entire composite key, not part of it.

```
(student_id, course_id) → grade

grade depends on both columns → Fully FD
```

4. Partial Dependency

When attribute depends on part of composite key.
```
student_id → student_name

In a table whose PK is (student_id, course_id)
```

5. Transitive Dependency

When dependency is indirect.
```
IF :
      student_id → dept_id
      dept_id → dept_name
THEN :
      student_id → dept_name
```


> It helps in maintaining the quality of data in the database, and the core concepts behind **database normalization** are based on functional dependencies.


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Decomposition in DBMS </b> </summary>

<br/>

- Decomposition is the process of breaking an original relation into multiple sub relations.

- Decomposition helps to remove anomalies, redundancy, and other problems in a DBMS.

- Decomposition can be lossy or lossless.

- **An ideal decomposition should be lossless join decomposition and dependency preserving**.

**Lossless Join Decomposition**

1. `union `
2. `intersection`

**Lossy Decomposition**
1. `primary key`

#
</details>

<!------------------------------------>
<details>
  <summary> <b> Inclusion Dependency in DBMS </b> </summary>

<br/>

- Inclusion dependency can be used to guide the design of the database.

- A statement in which some columns of a relation are contained in other columns is known as an inclusion dependency.

- A foreign key is an example of inclusion dependency. The referring relation is contained in the primary key column.

**Teacher**
| teacher_id (primary key)	|   name  	| department  |
|---------------------------|-----------|-------------|
|     1	                    | Ram Kumar	| DBMS        |

**Student**
| student_id |	name	     | teached_id (foreign key)	| age    |
|------------|-------------|--------------------------|--------|
|     1	     | Rahul Singh |      1	                  | 18     |

So this foreign key concept makes the inclusion dependency possible.

#
</details>

<!------------------------------------>
<details>
  <summary> <b> Multi-valued Dependency </b> </summary>

<br/>

Multivalued Dependency exists when the values two independent columns(attributes), say b and c, are determined based on the third attribute a.

Multi-valued Dependency is represented as 'a --> b --> c'.


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Join Dependency </b> </summary>

<br/>

The table is in **Join Dependency** if it can be reproduced by connecting numerous tables and each of these tables has a subset of the table's columns(attributes).

The relation between 5NF and Join Dependency is that a relation is in 5NF if it is in 4NF and does not have any join dependencies.

#
</details>

<!------------------------------------>
<details>
  <summary> <b> Normalization in DBMS </b> </summary>

### 🧹 Normalization in DBMS

Normalization is the **process of organizing the data and the attributes of a database**. 

It is performed **to reduce the data redundancy** in a database and to ensure that data is stored logically.

It is necessary to remove data redundancy because **it causes anomalies** in a database which makes it very hard for a DBA to maintain it


### 🧩 Why Do We need Normalization ?

Normalization is used **to reduce data redundancy**. 

It provides a method to remove the following anomalies from the database and bring it to a more consistent state

A database anomaly is a flaw in the database that occurs because of poor planning and redundancy.

To handle **1. Insertion anomalies** : occur at the time of insertion bcuz of missing some columns(attributes)
 
To handle **2. Updation anomalies** : occur at the time of updatation

To handle **3. Deletion anomalies** : occur when deleting one part of the data deletes the other necessary information 


### 🧱 Normal Forms (Steps of Normalization)

To understand the above-mentioned normal forms, we first need to have an understanding of the **functional dependencies**.

There are **four types of normal forms** that are usually used in relational databases

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/3be2b9e7-e2bc-486f-8b67-cd7edb545e4f" />


**1NF** : A relation is in 1NF if all its attributes have an atomic value.

**2NF** : A relation is in 2NF if it is in 1NF and all non-key attributes are fully functional dependent on the candidate key in DBMS.

**3NF** : A relation is in 3NF if it is in 2NF and there is no transitive dependency.

**BCNF** : A relation is in BCNF if it is in 3NF and for every Functional Dependency, LHS is the super key.

> **BCNF = Boyce-Codd Normal Form**

> Note : **Atomicity in Normalization ≠ Atomicity in ACID**
> - In 1NF → atomic = single value
> - In ACID → atomic = all-or-nothing transaction


#
</details>

---

## 4. Indexing in DBMS

<!------------------------------------>
<details>
  <summary> <b> Indexing in DBMS </b> </summary>

<br/>

> **Indexing in DBMS is a technique that uses data structures to optimize the searching time of a database query**. 

It helps in **faster query results and quick data retrieval** from the database. 

Indexing makes database **performance better**. 

It also **consumes lesser space in the main memory**.

Indexing is achieved by **creating Index-table or Index**.

Index usually consists of two columns which are a **key-value pair**. 

### 🚀 Types of Indexing

1. Primary Index : Created on primary key
2. Secondary Index : Created on non-primary column
3. Clustered Index : Determines physical order of table, Only one per table
4. Non-Clustered Index : Separate from actual data

> Many DBMS when primary key is created it is clustered by default

### ⚡ Advantages of Indexing

- Faster search
- Reduced I/O
- Faster `WHERE`, `JOIN`, `ORDER BY`
- Better query performance


### ⚠️ Disadvantages of Indexing

- Extra storage
- Slower `INSERT/UPDATE/DELETE`
- Maintenance overhead

> **`Index = Faster READ But Index = Slower WRITE`**

### Indexing Attributes

#
</details>


---

## 5. Transactions in DBMS

<!------------------------------------>
<details>
  <summary> <b> What is Transaction in DBMS? </b> </summary>

<br/>

A transaction is **a sequence of database operations** treated as a single logical unit of work.

Transaction operations are the actions that read, modify, and finalize data changes.


### 🎯 Operations in Transaction

**1. `Read` (R)** : Reads data from database into memory (local buffer).

**2. `Write` (W)** : Writes modified value back to database.

**3. `Commit` (C)** : Makes all changes permanent.

**4. `Rollback / Abort` (A)** : Undo all changes made by the transaction.


<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/71c03308-46a9-4164-891e-4fb427860bfd" />


### 🎯 Transaction States

**1. Active State**

**2. Partially Committed**

**3. Failed State**

**4. Aborted State**

**5. Committed State**

**6. Terminated State**

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/027741cc-4a49-46ce-a7da-f1fb42983a67" />


### 🚀 Why these Operations Matter

They ensure ACID properties :
- Atomicity :  either the transaction takes place completely at once or doesn’t happen at all, no middle option
- Consistency : database is consistent before and after the transaction
- Isolation : multiple transactions can occur concurrently without causing any inconsistency to the database state
- Durability : once the transaction has completed execution stored in and written to disk and they remain intact even if a system failure occurs

#
</details>

<!------------------------------------>
<details>
  <summary> <b> ACID Properties in DBMS </b> </summary>

<br/>

ACID properties refer to a set of fundamental guarantees provided to ensure the reliability and consistency of data transactions. 

ACID stands for Atomicity, Consistency, Isolation, and Durability.

> **Atomicity**

- Atomicity ensures that a transaction is treated as a single indivisible unit, either executing all its operations or none at all.

> **Consistency**

- Consistency ensures that the database remains in a valid state before and after a transaction.

> **Isolation**

- Isolation ensures that concurrent transactions do not interfere with each other, maintaining data integrity.

> **Durability**

- Durability guarantees that once a transaction is committed, its effects are permanent and survive any system failures.

Together, these properties ensure reliability and maintain data integrity in DBMS operations.


### 🎯 Transaction States

| State	      |                       Description                          |
|-------------|------------------------------------------------------------|
| Active	    | Transactions are in progress.                              |
| Partially   | Committed	Operations completed, but data not yet saved.    |
| Failed	    | Transaction fails database recovery system checks.         |
| Committed	  | Successful completion, changes permanently saved.          |
| Aborted	    | Transaction fails tests, rolled back or aborted.           |
| Terminated	| Transaction terminated, system ready for new transactions. |


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/74269209-578b-41b8-9232-63f63ca4de84" />


### ⚡ Advantages of ACID properties in DBMS

**Data Integrity and Reliability** : ACID properties ensure data remains consistent and reliable execution of transactions and  free from corruption.

**Concurrency Control** : ACID properties enable simultaneous access to data without conflicts.

**Fault Tolerance** : ACID properties ensure data durability, surviving system failures.

**Transaction Management** : ACID properties offer structured transaction handling.

**Compliance and Auditability** : ACID properties facilitate regulatory compliance and auditing.

### ⚡ Disadvantages of ACID properties in DBMS

**Performance Overhead** : ACID properties can impact system performance and throughput due to additional processing and resource utilization.

**Complexity** : Implementing ACID properties adds complexity to database systems, increasing design and maintenance challenges.

**Scalability Challenges** : ACID properties can pose difficulties in highly distributed or scalable systems, limiting scalability.

**Potential for Deadlocks** : ACID transactions using locking mechanisms can lead to deadlocks and system halts.

**Limited Concurrency** : ACID properties may restrict concurrency, impacting overall system throughput.

**Recovery Complexity** : ACID properties introduce complexities in recovery and backup strategies.

**Trade-off with Availability** : Strict adherence to ACID properties may affect system availability in certain situations.

#
</details>

<!------------------------------------>
<details>
  <summary> <b> Schedule in DBMS </b> </summary>

<br/>

Scheduling is the technique of preserving the order of the operations from one transaction to another while executing such concurrent transactions. 

A series of operations from one transaction to another transaction is known as a **schedule**.


### What is Scheduling, and why is it required?

**Why ?**

When multiple transactions execute simultaneously in an unmanageable manner, then it might lead to several problems, which are known as concurrency problems. In order to overcome these problems, scheduling is required.

**What ?**

Schedules - A series of operations from one transaction to another transaction is known as a Schedule. 

It is used to preserve the order of the operation in each individual transaction.

**Types of schedules** 

**Serial Schedule** : The serial schedule is a type of Schedule where one transaction is executed completely before starting another transaction.

**Non-serial Schedule** : In a Non-serial schedule, multiple transactions execute concurrently/simultaneously.

**Total number of non-serial schedules = Total number of schedules – Total number of serial schedules**.

A schedule is called **conflict serializable** if it can be transformed into a serial schedule by swapping non-conflicting operations.

A schedule is viewed as serializable if it is view equivalent to a serial schedule. 

If a schedule is conflict serializable, then it will be view serializable.



#
</details>

<!------------------------------------>
<details>
  <summary> <b> Serializability in DBMS </b> </summary>


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Recoverability in DBMS </b> </summary>


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Deadlock in DBMS </b> </summary>


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Concurrency Control in DBMS </b> </summary>


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Distributed Database System in DBMS </b> </summary>


#
</details>

<!------------------------------------>
<details>
  <summary> <b> Query Processing in DBMS </b> </summary>


#
</details>

---

## 6. Glossary of DBMS

<!------------------------------------>
<details>
  <summary> <b> Glossary of DBMS </b> </summary>


#
</details>

---
