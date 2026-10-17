# TOP and pagination

SQL Server's `TOP` returns a fixed number of rows. Add `ORDER BY` to define which rows come first.

```sql
SELECT TOP (3) *
FROM Customers
ORDER BY CustomerID;
```

`ORDER BY` makes it clear which rows are considered the first rows. Without it, SQL Server does not guarantee the order of results.

To return a different number, change the value in `TOP`:

```sql
SELECT TOP (1000) *
FROM Customers
ORDER BY CustomerID;
```

## OFFSET and FETCH

Use `OFFSET ... FETCH` for paging. The query must include `ORDER BY`.

```sql
-- Return rows 11 through 20, ordered by customer ID.
SELECT CustomerID, CustomerName
FROM Customers
ORDER BY CustomerID
OFFSET 10 ROWS FETCH NEXT 10 ROWS ONLY;
```
