# Spark SQL Notes

### Distributed computing
- process of splitting a large computational task into smaller subtasks,
- executing them in parallel across multiple machines that work together as a single system.

### Apache Spark
- an open-source, distributed computing engine designed to process large-scale data quickly and efficiently.
- a distributed compute engine abstracts the complexity of parallelism, letting devs focus on business logic.

## SQL Syntax

### Select and filter
```sql
SELECT *
FROM table_name
WHERE condition;
```

### Group and aggregate
```sql
SELECT category, COUNT(*) AS record_count
FROM table_name
GROUP BY category;
```

### Join
```sql
SELECT a.*, b.description
FROM table_a AS a
LEFT JOIN table_b AS b
  ON a.key = b.key;
```

## Functions to learn
- [ ] `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`
- [ ] `CASE WHEN`
- [ ] `COALESCE`
- [ ] Date and timestamp functions
- [ ] String functions
- [ ] Window functions (`ROW_NUMBER`, `RANK`, `LAG`, `LEAD`)
- [ ] CTEs (`WITH`)
- [ ] `MERGE INTO`
