# Window functions

Window functions calculate a value across related rows while keeping each row in the result. `OVER` defines the window; unlike `GROUP BY`, it does not collapse rows.

```sql
SELECT
    DepartmentID,
    StaffID,
    Salary,
    AVG(Salary) OVER (PARTITION BY DepartmentID) AS DepartmentAverage
FROM Staff;
```

`PARTITION BY` starts a separate window for each group. `ORDER BY` inside `OVER` defines row order for ranking and running calculations:

```sql
SELECT
    CustomerID,
    OrderID,
    OrderDate,
    ROW_NUMBER() OVER (
        PARTITION BY CustomerID
        ORDER BY OrderDate, OrderID
    ) AS OrderNumber,
    SUM(TotalAmount) OVER (
        PARTITION BY CustomerID
        ORDER BY OrderDate, OrderID
        ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
    ) AS RunningTotal
FROM Orders;
```

Common window functions include `ROW_NUMBER`, `RANK`, `DENSE_RANK`, `SUM`, `AVG`, `MIN`, and `MAX`. Add a unique tie-breaker to the window ordering when repeatable row numbering is important.
