
# ORDER BY

`ORDER BY` sorts the result set in ascending (`ASC`) or descending (`DESC`) order.

```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```

Examples:
```sql
-- Show employee names in ascending order.
SELECT empName FROM employee_info ORDER BY empName ASC;

-- Show all columns, sorted by employee name.
SELECT * FROM employee_info ORDER BY empName ASC;

-- Sort products from highest to lowest price:
SELECT * FROM Products ORDER BY Price DESC;

-- Sort by country, then by customer name in descending order.
SELECT * FROM Customers ORDER BY Country ASC, CustomerName DESC;

-- If countries match, sort those customers by name.
SELECT * FROM Customers ORDER BY Country, CustomerName;
```
