# HAVING

`HAVING` filters groups after `GROUP BY`; use `WHERE` to filter individual rows before grouping.

```sql
SELECT department_id, AVG(salary) AS AverageSalary
FROM Staff
WHERE salary > 0
GROUP BY department_id
HAVING AVG(salary) > 60000
ORDER BY AverageSalary DESC;
```

The following examples use the `employee_info` table from the create-table lesson:

```sql
SELECT deptID, ROUND(AVG(empSalary), 1) AS AverageSalary
FROM employee_info
GROUP BY deptID
HAVING AVG(empSalary) > 50000;
```

This example requires a `Customers` table:

```sql
SELECT COUNT(CustomerID), Country FROM Customers GROUP BY Country HAVING COUNT(CustomerID) > 5;
SELECT COUNT(CustomerID), Country FROM Customers GROUP BY Country HAVING COUNT(CustomerID) > 5 ORDER BY COUNT(CustomerID) DESC;
```
