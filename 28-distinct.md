# DISTINCT

`DISTINCT` removes duplicate rows from the selected result columns.

```sql
SELECT DISTINCT Country
FROM Customers
ORDER BY Country;
```

When selecting multiple columns, SQL Server removes duplicate combinations of those columns, not duplicates based on just one of them:

```sql
SELECT DISTINCT Country, City
FROM Customers
ORDER BY Country, City;
```

`DISTINCT` applies to the result only; it does not change or remove rows in the table. Use it when unique results are needed, rather than as a substitute for understanding why a join returns duplicates.
