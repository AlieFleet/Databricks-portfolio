# PySpark Notes

#What is PySpark?
- PySpark is Python API that lets me use Spark trough Python code.
- What is Spark anyway? Apache Spark is the engine that processes and transform the data.

## Imports
```python
from pyspark.sql.functions import col
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("StockPE").getOrCreate()
```

- SparkSession allows to interact with Spark and work with data (DataFrames, SQL, etc.).
- Once created, spark becomes main object for interacting with Spark.

| Code | Purpose | 
|---|---|
|`SparkSession.builder` |	Starts building a Spark session.|
|`.appName("StockPE")` | Gives your Spark application the name StockPE.|
|`.getOrCreate()` | Creates a new SparkSession or reuses an existing one.|
|`spark =` | 	Stores the session in a variable called spark.|

## Common DataFrame operations

- Displays the DataFrame's column names, data types, and structure.
- Remember that "df" is just an object's name to use function from imported library and can be anything

```python
df_trimmed.show(3, truncate=False)
```
- Displays only the first 3 rows of the DataFrame.
- `truncate=False` means long text values won't be cut off.
- Useful for quickly checking your data.

```python
df_trimmed.show(df_trimmed.count(), truncate=False)
```
- `df_trimmed.count()` counts the total number of rows in the DataFrame.
- `.show()` then displays that many rows.
- If the DataFrame contains 1,000 rows, it displays all 1,000 rows.

```python
df.printSchema()
```
- Displays the DataFrame's column names, data types, and structure.
- run .printSchema() to check column's name and their attributes

```python
df.describe()
```
- always returns exactly five rows:
count, mean, stddev, min, max
- describe() for a quick glance

```python
df.summary()
```
- returns those same five plus the quartiles:
count, mean, stddev, min, 25%, 50%, 75%, max
- summary() whenever the median and quartile spread matter.

```python
df.select("column_a", "column_b")
```
- Selects only the specified columns from the DataFrame.

```python
df.filter(col("amount") > 0)
```
- Filters rows where the amount column contains values greater than 0.

```python
df.groupBy("category").agg(F.count("*").alias("records"))
```
- Groups rows by category and counts the number of records in each group.
- Renames the resulting count column to records.

```python
df.orderBy(col("amount").desc())
```
- Sorts the DataFrame by amount in descending order (highest to lowest

```python
df.withColumn('new column's name', col('a') - col('b'))
```

## Distinction to remember

- Transformations (select, filter, orderBy, withColumn, …) are lazy — they return a new DataFrame you can keep chaining on.
- Actions (show, count, collect, display, …) execute and return a Python value — show() specifically returns None, so nothing can follow it in a chain.
  
- The ordering must come before the show:
``` python
df_filtered.orderBy(col("release_year").asc()).show(truncate = False)
```
 — filtered movies sorted by year, then printed
So: transform → transform → … → action last. 
