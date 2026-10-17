# GROUP BY

`GROUP BY` combines rows with the same values into groups, often for use with aggregate functions.

Use aggregate functions such as `COUNT`, `MAX`, `MIN`, `SUM`, and `AVG` to summarize values in each group. Every selected column that is not aggregated must be included in the `GROUP BY`.

```sql
SELECT department_id, AVG(salary) AS AverageSalary
FROM Staff
WHERE salary > 0
GROUP BY department_id
ORDER BY department_id;
```

The following examples use the `employee_info` table from the create-table lesson:

```sql
SELECT deptID, SUM(empSalary) AS TotalSalary
FROM employee_info
GROUP BY deptID;

SELECT deptID, ROUND(AVG(empSalary), 1) AS AverageSalary
FROM employee_info
GROUP BY deptID;
```

This example requires a `Customers` table:

```sql
SELECT COUNT(CustomerID), Country FROM Customers GROUP BY Country;
SELECT COUNT(CustomerID), Country FROM Customers GROUP BY Country ORDER BY COUNT(CustomerID) DESC;
```
