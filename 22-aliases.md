# Aliases

Aliases give a temporary name to a column or table in a query.

- **Column aliases** make result headings easier to read.
- **Table aliases** shorten table names, especially in joins and subqueries.

```sql
SELECT empName AS EmployeeName, empSalary AS Salary
FROM employee_info;
```

The `AS` keyword is optional, but including it can make queries clearer.

In SQL Server, use `CONCAT` to combine strings:

```sql
SELECT CONCAT(fname, ' ', lname) AS FullName
FROM employee_table;
```

Use a table alias to qualify columns:

```sql
SELECT e.empName AS EmployeeName
FROM employee_info AS e;
```
