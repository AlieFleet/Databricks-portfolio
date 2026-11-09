# PySpark Notes

#What is PySpark?
- PySpark is Python API that lets me use Spark trough Python code.
- What is Spark anyway? Apache Spark is the engine that processes and transform the data.

## Imports
```python
from pyspark.sql import functions as F
from pyspark.sql import types as T
```

## Common DataFrame operations

`Displays the DataFrame's column names, data types, and structure.`

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

```python
df.summary()
```
- Generates descriptive statistics
- such as count, mean, standard deviation, minimum, and maximum for numerical columns.

```python
df.select("column_a", "column_b")
```
- Selects only the specified columns from the DataFrame.

```python
df.filter(F.col("amount") > 0)
```
- Filters rows where the amount column contains values greater than 0.

```python
df.groupBy("category").agg(F.count("*").alias("records"))
```
- Groups rows by category and counts the number of records in each group.
- Renames the resulting count column to records.

```python
df.orderBy(F.col("amount").desc())
```
- Sorts the DataFrame by amount in descending order (highest to lowest

## Distinction to remember

- Transformations (select, filter, orderBy, withColumn, …) are lazy — they return a new DataFrame you can keep chaining on.
- Actions (show, count, collect, display, …) execute and return a Python value — show() specifically returns None, so nothing can follow it in a chain.
  
- The ordering must come before the show:
``` python
df_filtered.orderBy(col("release_year").asc()).show(truncate = False)
```
 — filtered movies sorted by year, then printed
So: transform → transform → … → action last. 
