
# Update rows

`UPDATE` modifies existing rows in a table.

```sql
UPDATE table_name
SET column1 = value1, column2 = value2,....
WHERE condition;
```

Note:If Where condition not passes it will update all table data as per condition.
Examples:-

```sql
-- Update the employee name where empId is 2.
UPDATE employee_info SET empName = 'Manish' WHERE empId = 2;

-- Without a WHERE clause, this updates every row.
UPDATE employee_info SET empSalary = empSalary + 1000;

-- Update the department for the employee whose empId is 4.
UPDATE employee_info SET deptID = 4 WHERE empId = 4;

-- Update two columns for the employee named Sanish.
UPDATE employee_info SET empSalary = 45000, job = 'Tester' WHERE empName = 'Sanish';
```

The following SQL statement updates the first customer (CustomerID = 1) with a new contact person and a new city.

```sql
UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;
```
