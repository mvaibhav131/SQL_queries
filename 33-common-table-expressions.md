# Common table expressions

A common table expression (CTE) gives a name to a query result for use by the statement immediately following it. A CTE is not a permanent table.

```sql
WITH DepartmentTotals AS (
    SELECT DepartmentID, AVG(Salary) AS AverageSalary
    FROM Staff
    GROUP BY DepartmentID
)
SELECT DepartmentID, AverageSalary
FROM DepartmentTotals
WHERE AverageSalary > 60000
ORDER BY AverageSalary DESC;
```

In SQL Server, if another statement precedes a CTE in the same batch, terminate that preceding statement with a semicolon. A CTE can be followed by one `SELECT`, `INSERT`, `UPDATE`, `DELETE`, or `MERGE` statement.

Use a CTE to make a complex statement easier to read. It does not guarantee that the result is materialized or evaluated only once.
