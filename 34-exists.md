# EXISTS

`EXISTS` tests whether a subquery returns at least one row. It is often used to find rows with a related match, without returning columns from the related table.

```sql
SELECT c.CustomerID, c.CustomerName
FROM Customers AS c
WHERE EXISTS (
    SELECT 1
    FROM Orders AS o
    WHERE o.CustomerID = c.CustomerID
);
```

To find customers with no orders, use `NOT EXISTS`:

```sql
SELECT c.CustomerID, c.CustomerName
FROM Customers AS c
WHERE NOT EXISTS (
    SELECT 1
    FROM Orders AS o
    WHERE o.CustomerID = c.CustomerID
);
```

The inner query refers to the current customer, so it is a correlated subquery. `EXISTS` checks for a match; the selected value (`1` here) is not returned.
