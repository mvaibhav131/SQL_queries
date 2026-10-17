# CASE expressions

`CASE` returns a value chosen by conditions. It can be used in a `SELECT` list, `ORDER BY`, and other expressions.

```sql
SELECT
    ProductName,
    Price,
    CASE
        WHEN Price >= 100 THEN 'Expensive'
        WHEN Price >= 25 THEN 'Standard'
        ELSE 'Budget'
    END AS PriceBand
FROM Products
ORDER BY Price DESC;
```

Conditions are checked from top to bottom; the first matching branch is returned. `ELSE` is optional, but without it an unmatched row returns `NULL`.

For matching one expression against values, use the simple form:

```sql
SELECT
    OrderID,
    CASE Status
        WHEN 'P' THEN 'Pending'
        WHEN 'S' THEN 'Shipped'
        ELSE 'Other'
    END AS StatusName
FROM Orders;
```
