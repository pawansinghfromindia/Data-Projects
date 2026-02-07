# SparkSQL

> **Spark SQL is Apache Spark's module for working with structured data.**

- Spark provides a programming abstraction called DataFrames and can also act as a distributed SQL query engine.

**A thorough introduction to Spark SQL, The basics** <br/> 
How Spark combines the power of distributed computing with the ease of use of Python and SQL.

<details>
  <summary> <b> What is Spark and What is sparkSQL? </b> </summary>

**Apache Spark** is a computing framework for processing big data, and **Spark SQL** is a component of Apache Spark.

How to take Spark to a new level of usefulness, using advanced SQL features, such as window functions.

- We will use Spark SQL to analyze time series data, extract the most common words from a text document, 
create feature sets from natural language text, and use them to predict the last word in a sentence using logistic regression.

- Creating and querying an SQL table in Spark,

How to use SQL window functions to perform running sums, running differences, and other operations.


How to use the window function in Spark SQL for natural language processing, including using a moving window analysis to find common word sequences.

How to use the SQL Spark UI to properly cache DataFrames and SQL tables before exploring the best practices for logging in Spark.


so far to load and tokenize raw text before extracting word sequences. 
We’ll then use logistic regression to classify the text, using raw natural language data to train a text classifier.


</details>

<!----------------------------------------->

<details>
  <summary> <b>1. Spark SQL</b> </summary>

Spark provides a programming abstraction called DataFrames and can also act as a distributed SQL query engine.

</details>

<details>
  <summary> 2. Load a dataframe from file </summary>

```py
df = spark.read.csv(filename)
```

```py
df = spark.read.csv(filename, header=True)
```

</details>

<details>
  <summary> 3. Create SQL table and query it </summary>

```py
df.createOrReplaceTempView("schedule")
spark.sql("SELECT * FROM schedule WHERE station = 'San Jose'")
.show()
```
| train_id  | station  | time    |
|-----------|----------|---------|
|     324   | San Jose | 9:05a   |
|     217   | San Jose | 6:59a   |

</details>


<details>
  <summary>4. Inspecting table schema </summary>

```py
result = spark.sql("SHOW COLUMNS FROM tableName")
```
or
```py
result = spark.sql("SELECT * FROM tableName limit 0")
```
or
```py
result = spark.sql("DESCRIBE tableName")
```

Too see the result
```py
result.show()
```
or
```py
print(result.columns)
```

</details>

<details>
  <summary>5. Dataframe </summary>

> The dataframe is a fundamental data abstraction in Spark.

</details>

<details>
  <summary>6. Spark Dataframe </summary>

> A Spark DataFrame is a distributed collection of data organized into named columns.

</details>

<details>
  <summary>7. Tabular data </summary>

> It is conceptually equivalent to a table in a relational database, also called, simply, “tabular” data.

|train_id|      station| time|
|--------|-------------|-----|
|     324|San Francisco|7:59a|
|     324|  22nd Street|8:03a|
|     324|     Millbrae|8:16a|
|     324|    Hillsdale|8:24a|
|     324| Redwood City|8:31a|
|     ...|          ...|  ...|
|     217| Blossom Hill|6:36a|
|     217|      Capitol|6:42a|
|     217|       Tamien|6:50a|
|     217|     San Jose|6:59a|

</details>

<details>
  <summary>8. Two dataframes </summary>

We can have 2 dataframes having same types of columns and containing different data

</details>

<details>
  <summary>9. Two dataframes concatenated </summary>

We can concatenated two tables rows data into a single dataframe

</details>

<details>
  <summary>10. Two dataframes - distributed </summary>

Spark DataFrame is a distributed collection of data organized into named columns.

What does mean by **Distributed**? <br/>
Spark can split the datasets into parts and then store each part on a different servers 

In this case Spark is partitioning the data and distributing it automatically on our behalf we don't have to do anything.

This is one technique spark uses to handle large datasets.Even though server may not enough storage to hold the entire datasets on its own .

Spark allows us to treat a dataframe like a table and query it using SQL.


</details>

<details>
  <summary> <b>11. SQL : Structured Query Language</b> </summary>

A query tells machine(computer) what to fetch from the database. 

What's useful about Spark SQL table is that it allows us to take the datasets that is in a dataframe, namely a distributed collection of rows having
name columns and treat it as a single table and fetch data from it using SQL query.


</details>

<details>
  <summary>12. Loading delimited text </summary>

We often use an instance of a sparkSession Object.<br/>
This is provided in a variable called `spark` <br/>
Some implementation of Spark,  like PySpark Shell automatically provide an instance of SparkSession.

Load a comma delimited file `trainschedule.txt` into a dataframe called `df`:
```py
df = spark.read.csv("trainschedule.txt", header = True)

df.show()
```



</details>


<!---------------------------------------->

<details>
  <summary> <b> SQL - Structure Query Language </b> </summary>

<br/>

Window Function SQL | INTRODUCTION TO SPARK SQL IN PYTHON

As we now, now we create and query a SQL table. Now let's learn about Window SQL Function.

What is a Window Function SQL? and how it is useful ?

- SQL Window function Express operations more simply than dot notation or queries
- When processing some rows, Each row uses the values of other rows to calculate its value

A train schedule
| train_id | station      | time |
|----------|--------------|------|
|324       |San Francisco | 7:59 |
| 324      |22nd Street   | 8:03 |
| 324      |Millbrae      | 8:16 |
|324       |Hillsdale     | 8:24 |
|324       |Redwood City  | 8:31 |
|324       |Palo Alto     | 8:37 |
|324       |San Jose      | 9:05 |


**Column with time until next stop added**
| train_id | station      |time   |time_to_next_stop |
|----------|--------------|-------|------------------|
|324       |San Francisco |7:59   |4 min             |
|324       |22nd Street   |8:03   |13 min            |
|324       |Millbrae      |8:16   |8 min             |
|324       |Hillsdale     |8:24   |7 min             |
|324       |Redwood City  |8:31   |6 min             |
|324       |Palo Alto     |8:37   |28 min            |
|324       |San Jose      |9:05   |null              |

**Column with time of next stop**
| train_id | station      |time   |time (following row) |
|----------|--------------|-------|---------------------|
|324       |San Francisco |7:59   |4 min             |
|324       |22nd Street   |8:03   |13 min            |
|324       |Millbrae      |8:16   |8 min             |
|324       |Hillsdale     |8:24   |7 min             |
|324       |Redwood City  |8:31   |6 min             |
|324       |Palo Alto     |8:37   |28 min            |
|324       |San Jose      |9:05   |null              |


**OVER clause and ORDER BY clause**
```py
query = """
SELECT
      train_id,
      station,
      time,
      LEAD(time, 1) OVER (ORDER BY time) AS time_next
FROM sched
WHERE train_id=324  """

spark.sql(query).show()
```

**PARTITION BY clause**
```sql
SELECT train_id, station, time, LEAD(time,1) OVER (PARTITIONBY train_id ORDERBYtime) AS time_next FROM sched 
```


Dataframe Dot notation and SQL | INTRODUCTION TO SPARK SQL IN PYTHON

**Our table has 3 columns**
```py
df.columns

# ['train_id', 'station', 'time']
```
```py
df.show(5) 
```
|train_id|      station| time|
|--------|-------------|-----|
|     324|San Francisco|7:59 |
|     324|  22nd Street|8:03 |
|     324|     Millbrae|8:16 |
|     324|    Hillsdale|8:24 |
|     324| Redwood City|8:31 |

We only need 2
```py
df.select('train_id','station')  .show(5)
```
|train_id|      station|
|--------|-------------|
|     324|San Francisco|
|     324|  22nd Street|
|     324|     Millbrae|
|     324|    Hillsdale|
|     324| Redwood City|


Three ways to select 2 columns
```py
df.select('train_id', 'station')
```
```py
df.select(df.train_id, df.station) #dataframe dot notation
```
```py
from pyspark.sql.functions import col
df.select(col('train_id'), col('station'))
```

Two ways to rename a column
```py
df.select('train_id', 'station')
  .withColumnRenamed('train_id', 'train')
  .show(5);
```

```py
df.select(col('train_id').alias('train'), 'station') # BUT It is not recommended
```
Don't do this. 
Not use all three conventions at the same time without good reason.


**SQL Queries using dot notation**

Most SparkSQL queries can be done either in dot notation or sql notation.

```py
spark.sql('SELECT train_id AS train, station  FROM schedule LIMIT 5')
     .show()
```
or
```
spark.select(col('train_id').alias('train'), 'station')
     .limit(5)
     .show()
```
Both give same result
| train | station |
|-------|----------|
| 324   | San Francisco |
| 324   | 22 Street |
| 324   | Millbrae |
| 324   | Hillsdale |
| 324   | Redwood City |


SQL Windows function can be also done either in SQL or in dot notation
```py
query = """
SELECT *,
      ROW_NUMBER() OVER(PARTITION BY train_id) ORDER BY(time) AS id
FROM schedule
"""
spark.sql(query)
     .show(11)
```
or
```py
from pyspark.sql import window,
from pyspark.sql functions import row_number

df.withColumn("id", row_number().over(windows.partitionBy('train_id').orderBy('time')))
```
Both results the same result.

|train_id|      station| time| id  |
|--------|-------------|-----|-----|
|     217| Gilroy      |6:06a| 1   |
|     217| Sen Martin  |6:15a| 2   |
|     217| Morgan Hill |6:21a| 3   |
|     217|       Tamien|6:36a| 4   |
|     217|     Capitol|6:42a | 5   | 
|     217|     Capitol|6:42a | 6   | 
|     217|     Capitol|6:42a | 7   | 
|     324|San Francisco|7:59a| 1   |
|     324|  22nd Street|8:03a| 2   |
|     324|     Millbrae|8:16a| 3   |
|     324|    Hillsdale|8:24a| 4   |

There is typically a dot notation equivalent of every SQL clause including window functions.

ROW_NUMBER in SQL : `pyspark.sql.functions.row_number`

The inside of the OVER clause : `pyspark.sql.window`

The window object provides methods for partitions and orders.

PARITION BY : `pyspark.sql.window.partitionBy`

ORDER BY : `pyspark.sql.window.ordeBy`

Some people prefer SQL version other people dot notation. 

**Using a WindowSpec**
- The `over` function in spark SQL correspond to the `OVER` clause in SQL.
- The class `pyspark.sql.window.Window` represents inside of an `OVER` clause
```py
window = Window.partitionBy('train_id').orderBy('time')
dfx = df.withColumn('next', lead('time', 1).over(window))
```

Above type(window) is `pyspark.sql.window.WindowSpec`

</details>

