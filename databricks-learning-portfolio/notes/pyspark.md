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
df.summary()
df.select("column_a", "column_b")
df.filter(F.col("amount") > 0)
df.groupBy("category").agg(F.count("*").alias("records"))
df.orderBy(F.col("amount").desc())
```

## Topics to practise
- [ ] Read and write data
- [ ] Schema inference vs explicit schemas
- [ ] Select, filter, withColumn, drop, rename
- [ ] Null handling and deduplication
- [ ] Grouping and aggregation
- [ ] Joins
- [ ] Window functions
- [ ] User-defined functions (understand trade-offs)
- [ ] Partitioning and shuffles
- [ ] Performance basics
