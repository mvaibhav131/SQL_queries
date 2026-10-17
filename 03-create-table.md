# Create a table

`CREATE TABLE` defines a new table and its columns.

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype
);
```

Choose a data type for each column, such as `INT`, `VARCHAR`, `DECIMAL`, or `DATE`. Constraints such as `PRIMARY KEY` and `NOT NULL` can enforce rules about the data.

Example:

```sql
CREATE TABLE employee_info (
    empId INT PRIMARY KEY,
    empName VARCHAR(50) NOT NULL,
    empSalary DECIMAL(10, 2) NOT NULL,
    job VARCHAR(50),
    phone VARCHAR(20),
    deptID INT
);
```
