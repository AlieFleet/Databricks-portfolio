# PySpark Notes

## Imports
```python
from pyspark.sql import functions as F
from pyspark.sql import types as T
```

## Common DataFrame operations
```python
df.printSchema()
df.show(5, truncate=False)
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

## Useful patterns
Add short, tested examples here.

## Gotchas
- 
