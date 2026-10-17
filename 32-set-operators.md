# Set operators

Set operators combine the results of two compatible `SELECT` queries. Each query must return the same number of columns in the same order, with compatible data types. Column names in the result come from the first query.

## UNION and UNION ALL

`UNION` removes duplicate rows; `UNION ALL` keeps them and is usually preferable when duplicates should remain.

```sql
SELECT City FROM Customers
UNION
SELECT City FROM Suppliers
ORDER BY City;
```

```sql
SELECT City FROM Customers
UNION ALL
SELECT City FROM Suppliers;
```

## INTERSECT and EXCEPT

`INTERSECT` returns rows found in both results. `EXCEPT` returns rows from the first result that are absent from the second. Both remove duplicates.

```sql
SELECT City FROM Customers
INTERSECT
SELECT City FROM Suppliers;
```

```sql
SELECT City FROM Customers
EXCEPT
SELECT City FROM Suppliers;
```

In SQL Server, put a single `ORDER BY` after the final query to sort the combined result.
