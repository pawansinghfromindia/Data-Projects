# PySpark

What is Apache Spark? <br/>
- Apache Spark is a multi-language engine for executing data engineering, data science, and machine learning on single-node machines or clusters.
- Unified engine for large-scale data analytics
- It is  Simple | Fast | Scalable | Unified.

<details>
  <summary> <b> Spark </b> </summary>

<br/>

Apache Spark is a distributed processing system used to perform big data and machine learning tasks on large datasets.
With Apache Spark, users can run queries and machine learning workflows on petabytes of data, which is impossible to do on your local device.

Apache Spark is a distributed processing system used to perform big data and machine learning tasks on large datasets. 

With Apache Spark, users can run queries and machine learning workflows on petabytes of data, which is impossible to do on your local device.

</details>


<details>
  <summary> <b> What is PySpark? </b> </summary>

<br/>

**PySpark** is an interface for Apache Spark in Python.

With PySpark, you can write Python and SQL-like commands to manipulate and analyze data in a distributed processing environment.

Using PySpark, data scientists manipulate data, build machine learning pipelines, and tune models.

Most data scientists and analysts are familiar with Python and use it to implement machine learning workflows. <br/> 
PySpark allows them to work with a familiar language on large-scale distributed datasets. 

Note : Apache Spark can also be used with other data science programming languages like **R** or **Java** etc

</details>


<details>
  <summary> <b> Why Use PySpark? </b> </summary>

<br/>

The reason companies choose to use a framework like **PySpark** is because of how quickly it can process big data. 

It is faster than libraries like Pandas and Dask, and can handle larger amounts of data than these frameworks.

If you had over petabytes of data to process, for instance, **Pandas** and **Dask** would fail <br/>
but **PySpark** would be able to handle it easily.


While it is also possible to write Python code on top of a distributed system like Hadoop, <br/>
**With PySpark, you can write code** to collect data from a source that is continuously updated, 
while data can only be processed in batch mode with Hadoop. 

PySpark provides fault tolerance, which means that it has the capability to recover loss after a failure occurs. 

The framework also has in-memory computation and is stored in random access memory (RAM).  <br/>
It can run on a machine that does not have a hard-drive or SSD installed.

</details>


<details>
  <summary> <b> How to Install PySpark ?</b> </summary>

<br/>

**Note: If you're using cloud-based platforms like DataLab or Databricks, you can skip the local installation as PySpark comes pre-installed.**

If not then follows :<br/>
**Prerequisites**
- Python 3.7 or later
- Jupyter Notebook 

**PySpark Installation Guide** <br/>

Open a Python file in your Jupyter Notebook and run the following lines of code in the first cell:
```python
!pip install pyspark
```

Now that you have PySpark up and running, we will show you how to execute an end-to-end customer segmentation project using the library. 


</details>

<details>
  <summary> <b> PySpark Tutorial </b> </summary>

<br/>

customer segmentation project using the library
> Customer segmentation is a marketing technique companies use to identify and group users who display similar characteristics.

e.g : if you visit Starbucks only during the summer to purchase cold beverages, you can be segmented as a “seasonal shopper” 
and enticed with special promotions curated for the summer season.

Data scientists usually build unsupervised machine learning algorithms such as K-Means clustering or hierarchical clustering 
to perform customer segmentation.

These models are great at identifying similar patterns between user groups that often go unnoticed by the human eye.

we will use K-Means clustering to perform customer segmentation on the e-commerce dataset

- Reading csv files with PySpark

- Exploratory Data Analysis with PySpark

- Grouping and sorting data

- Performing arithmetic operations

- Aggregating datasets

- Data Pre-Processing with PySpark

- Working with datetime values

- Type conversion

- Joining two data frames

- The rank() function

- PySpark Machine Learning

- Creating a feature vector

- Standardizing data

- Building a K-Means clustering model

- Interpreting the model

</details>


<details>
  <summary> <b> Step 1: Creating a SparkSession </b> </summary>

<br/>

A SparkSession is an entry point into all functionality in Spark, and is required if you want to build a dataframe in PySpark.

code to initialize a SparkSession: boilerplate code
```python
from pyspark.sql import SparkSession  # add this import

spark = (
    SparkSession.builder
    .appName("Datacamp Pyspark Tutorial")
    .config("spark.memory.offHeap.enabled", "true")
    .config("spark.memory.offHeap.size", "10g")
    .getOrCreate()
)
```
With that we built a spark session and set a name for the application. <br/>
Then, the data was cached in off-heap memory to avoid storing it directly on disk, and the amount of memory was manually specified.

</details>


<details>
  <summary> <b> Step 2: Creating the DataFrame </b> </summary>

<br/>

We can now read the dataset we just downloaded:
```python
df = spark.read.csv("datacamp_ecommerce.csv", header=True, escape='"', inferSchema=True)
```
**Note** that we defined an escape character to avoid commas in the `.csv` file when parsing.

Let’s take a look at the head of the DataFrame using the show() function:
```python
df.show(5,0)

# df : This is the DataFrame you are working with
# show(5, 0): This method displays the first 5 rows of the DataFrame. 0 specifies that no truncation should be applied to the data in the columns,
# meaning the full content of each column will be displayed without cutting off any text.
```
The DataFrame consists of 8 variables: which are the columns in a table or of csv file.

</details>


<details>
  <summary> <b> Step 3: Exploratory data analysis </b> </summary>

<br/>

Now that we have seen the variables present in this dataset, let’s perform some exploratory data analysis to further understand these data points:

1. Let’s start by counting the number of rows in the DataFrame :
```py
df.count()  # Answer: 2,500

#df.count() is used to count the number of non-NA/null entries for each column in a DataFrame df.
```

2. How many unique customers are present in the DataFrame?
```py
df.select('CustomerID').distinct().count() # Answer: 95

# df.select('CustomerID'): This selects the 'CustomerID' column from the DataFrame df.
# .distinct(): This ensures that only unique 'CustomerID' values are considered.
# .count(): This counts the number of unique 'CustomerID' values.
```

3. What country do most purchases come from? <br/>
To find the country from which most purchases are made, we need to use the groupBy() clause in PySpark:
```py
from pyspark.sql.functions import *
from pyspark.sql.types import *

df.groupBy('Country').agg(countDistinct('CustomerID').alias('country_count')).show()
```
| country     | country_count |
|-------------|---------------|
| Germany     | 2             |
| France      | 1             | 
| Norway      | 1             | 
| Neitherland | 1             |
| USA         | 1             |
| UK          | 88            |

Sort the above data
```py
df.groupBy('Country').agg(countDistinct('CustomerID').alias('country_count')).orderBy(desc('country_count')).show()
```
| country     | country_count |
|-------------|---------------|
| UK          | 88            |
| Germany     | 2             |
| France      | 1             | 
| Norway      | 1             | 
| Neitherland | 1             |
| USA         | 1             |

4. When was the most recent purchase made by a customer on the e-commerce platform? <br/>
To find when the latest purchase was made on the platform,
 we need to convert the InvoiceDate column into a timestamp format and use the max() function in Pyspark:
```py
df = df.withColumn(
    "date",
    coalesce(
        to_timestamp(col("InvoiceDate"), "yy/MM/dd HH:mm"),
        to_timestamp(col("InvoiceDate"), "yyyy-MM-dd HH:mm:ss"),
        to_timestamp(col("InvoiceDate"))  # best-effort fallback
    )
)
df.select(max("date")).show()
```
| max(date)           |
|---------------------|
| 2026-12-31 17:05:40 |

5. When was the earliest purchase made by a customer on the e-commerce platform? <br/>
Similar to what we did above, the min() function can be used to find the earliest purchase date and time:
```py
# Here we can use same data frame of above one
df.select(min("date")).show()
```
| min(date)           |
|---------------------|
| 2026-01-01 17:05:40 |

</details>



<details>
  <summary> <b> Step 4: Data pre-processing </b> </summary>

<br/>

Now that we have analyzed the dataset and have a better understanding of each data point, 
we need to prepare the data to feed into the machine learning algorithm.

Let’s take a look at the head of the data frame once again to understand how the pre-processing will be done:
```py
df.show(5,0)
```

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d5940799-2b41-4018-9946-9ef951ba37b8" />



From the dataset above, we need to create multiple customer segments based on each user’s purchase behavior. <br/>
The variables(columns) in this dataset are in a format that cannot be easily ingested into the customer segmentation model. <br/>
These features individually do not tell us much about customer purchase behavior. <br/>

Due to this, we will use the existing variables(columns) to derive three new informative features - recency, frequency, and monetary value (RFM).

**RFM** is commonly used in marketing to evaluate a client’s value based on their:
- **Recency**: How recently has each customer made a purchase?
- **Frequency**: How often have they bought something?
- **Monetary Value**: How much money do they spend on average when making purchases?

We will now pre-process the data frame to create the above variables.

### Recency
First, let’s calculate the value of recency - the latest date and time a purchase was made on the platform. <br/>
This can be achieved in two steps:

**1. Assign a recency score to each customer** <br/>
We will subtract every date in the data frame from the earliest date. <br/>
This will tell us how recently a customer was seen in the data frame. <br/>
A value of 0 indicates the lowest recency, as it will be assigned to the person who was seen making a purchase on the earliest date. <br/>
```py
df = df.withColumn("from_date", to_timestamp(lit("12/1/10 08:26"), "yy/MM/dd HH:mm"))
df2 = df.withColumn("recency", col("date").cast("long") - col("from_date").cast("long"))


w = Window.partitionBy("CustomerID").orderBy(desc("recency"))
df2 = df2.withColumn("rn", row_number().over(w)).filter(col("rn") == 1).drop("rn")
```


**2. Select the most recent purchase** <br/>
One customer can make multiple purchases at different times. <br/>
We need to select only the last time they were seen buying a product, as this is indicative of when the most recent purchase was made: 
```py
df2 = df2.join(df2.groupBy('CustomerID').agg(max('recency').alias('recency')),on='recency',how='leftsemi')

# df2.groupBy('CustomerID').agg(max('recency').alias('recency')):
#   This part groups df2 by the CustomerID column and calculates the maximum value of the recency column for each group,
#   renaming this aggregated column to recency.

## df2.join(..., on='recency', how='leftsemi'):
##    This part performs a left semi join on df2 using the result of the previous aggregation.
##     A left semi join returns rows from df2 where there is a match in the aggregated DataFrame based on the recency column.

## overall, to filter df2 to keep only the rows that have the maximum recency value for each CustomerID.
```

Let’s look at the head of the new data frame. It now has a variable called “recency” appended to it:
```py
df2.show(5,0)
```

> **An easier way to view all the variables present in a PySpark DataFrame is to use its printSchema() function.**
> - This is the equivalent of the info() function in Pandas:
```py
df2.printSchema()

## Renders all the columns name with datatypes
```

### Frequency
Let’s now calculate the value of frequency - how often a customer buys something on the platform. <br/>
To do this, we just need to group by each CustomerID and count the number of items they purchased:
```py
df_freq = df2.groupBy('CustomerID').agg(count('InvoiceDate').alias('frequency'))

## this code is to create a new DataFrame df_freq that contains each unique 'CustomerID' and
##       the corresponding count of 'InvoiceDate' occurrences, which is labeled as 'frequency'.
## This essentially calculates how many times each customer has made a purchase.
```
Look at the head of this new DataFrame we just created:
```py
df_freq.show(5,0)
```
There is a frequency value appended to each customer in the DataFrame. <br/>
This new DataFrame only has two columns, and we need to join it with the previous one:
```py
df3 = df2.join(df_freq,on='CustomerID',how='inner')

## to combine df2 and df_freq into a new DataFrame df3, containing only the rows where 'CustomerID' exists in both original DataFrames.
```

Let’s print the schema of this DataFrame:
```py
df3.printSchema()
```

### Monetary Value
Finally, let’s calculate monetary value - the total amount spent by each customer in the DataFrame. <br/>
There are two steps to achieving this:

1. Find the total amount spent in each purchase: <br/>
Each `CustomerID` comes with variables called `Quantity` and `UnitPrice` for a single purchase:

To get the total amount spent by each customer in one purchase, we need to multiply Quantity with UnitPrice:
```py
m_val = df3.withColumn(
    "TotalAmount",
    col("Quantity").cast("double") * col("UnitPrice").cast("double")
)

```

2. Find the total amount spent by each customer: <br/>
To find the total amount spent by each customer overall, we just need to group by the CustomerID column and sum the total amount spent:
```py
m_val = m_val.groupBy('CustomerID').agg(sum('TotalAmount').alias('monetary_value'))

## to calculate the total monetary value (sum of 'TotalAmount') for each customer, identified by 'CustomerID'.
```

Merge this DataFrame with the all the other variables:
```py
finaldf = m_val.join(df3,on='CustomerID',how='inner')

##  to combine the data from m_val and df3 based on the CustomerID column, keeping only the rows where CustomerID exists in both DataFrames.
```
Now that we have created all the necessary variables to build the model, <br/>
run the following lines of code to select only the required columns and drop duplicate rows from the DataFrame:
```py
finaldf = finaldf.select(['recency','frequency','monetary_value','CustomerID']).distinct()

## select method is used to choose only the columns ['recency', 'frequency', 'monetary_value', 'CustomerID'] from the DataFrame.
## distinct method is applied to ensure that the resulting DataFrame contains only unique rows. 
```

Look at the head of the final DataFrame to ensure that the pre-processing has been done accurately:
```py
df.show(5, 0)
```

### Standardization

Before building the customer segmentation model, let’s standardize the DataFrame to ensure that all the variables are around the same scale:

```py
from pyspark.ml.feature import VectorAssembler, StandardScaler


assemble = VectorAssembler(
    inputCols=["recency", "frequency", "monetary_value"],
    outputCol="features"
)
assembled_data = assemble.transform(finaldf)


scale = StandardScaler(inputCol="features", outputCol="standardized")
data_scale = scale.fit(assembled_data)
data_scale_output = data_scale.transform(assembled_data)

```
To see what the standardized feature vector looks like:
```py
data_scale_output.select('standardized').show(2,truncate=False)

## displaying the first 2 rows of the 'standardized' column from the DataFrame data_scale_output in a way
## that ensures the full content of the rows is visible.

```

These are the scaled features that will be fed into the clustering algorithm.

</details>

<details>
  <summary> <b> Step 5: Building the machine learning model </b> </summary>

<br/>

Now that we have completed all the data analysis and preparation, let’s build the K-Means clustering model. 


The algorithm will be created using PySpark’s machine learning API.

1.  Finding the number of clusters to use
2.  Building the K-Means Clustering Model
3.  Making Predictions

</details>

<details>
  <summary> <b>Step 6: Cluster Analysis</b> </summary>

<br/>

The final step is to analyze the customer segments we just built.

To visualize the recency, frequency, and monetary value of each CustomerID in the DataFrame usint Matplotlib
```py
import matplotlib.pyplot as plt
import seaborn as sns

df_viz = preds.select('recency','frequency','monetary_value','prediction')
df_viz = df_viz.toPandas()
avg_df = df_viz.groupby(['prediction'], as_index=False).mean()

list1 = ['recency','frequency','monetary_value']

for i in list1:
    sns.barplot(x='prediction',y=str(i),data=avg_df)
    plt.show()
```

</details>

