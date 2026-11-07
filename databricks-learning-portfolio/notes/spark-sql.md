# Spark SQL Notes

## Quick reference

Add syntax and examples as you learn them. Prefer runnable, minimal examples.

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
