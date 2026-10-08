# INNER JOIN

The INNER JOIN is used to return all matching rows from two or more tables where the JOIN condition is satisfied.

It returns only those records that have matching values in both tables.

**Note:**
- INNER JOIN is also called a Simple JOIN.
- When the JOIN condition uses the `=` operator, it is called an Equi Join.
- A Natural Join is different because it automatically joins columns with the same names.

## Syntax

```sql
SELECT column_names
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

## Example

**Step 1: Create Employees Table**

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    DepartmentID INT
);
```

**Step 2: Insert Records into Employees Table**

```sql
INSERT INTO Employees
(EmployeeID, FirstName, LastName, DepartmentID)
VALUES
(1, 'John', 'Doe', 101),
(2, 'Jane', 'Smith', 102),
(3, 'Jim', 'Brown', 101),
(4, 'Jake', 'White', 103);
```

**Step 3: Display Employees Records**

```sql
SELECT * FROM Employees;
```

Output:

| EmployeeID | FirstName | LastName | DepartmentID |
|---|---|---|---|
| 1 | John | Doe | 101 |
| 2 | Jane | Smith | 102 |
| 3 | Jim | Brown | 101 |
| 4 | Jake | White | 103 |

**Step 4: Create Departments Table**

```sql
CREATE TABLE Departments (
    DepartmentID INT PRIMARY KEY,
    DepartmentName VARCHAR(50)
);
```

**Step 5: Insert Records into Departments Table**

```sql
INSERT INTO Departments
(DepartmentID, DepartmentName)
VALUES
(101, 'Sales'),
(102, 'Marketing'),
(103, 'Developer');
```

**Step 6: Display Departments Records**

```sql
SELECT * FROM Departments;
```

Output:

| DepartmentID | DepartmentName |
|---|---|
| 101 | Sales |
| 102 | Marketing |
| 103 | Developer |

## INNER JOIN Example

Now, join both tables based on the common column `DepartmentID`.

**Example 1: Retrieve All Columns**

```sql
SELECT *
FROM Employees
INNER JOIN Departments
ON Employees.DepartmentID = Departments.DepartmentID;
```

Explanation:

- INNER JOIN combines Employees and Departments tables.
- DepartmentID is the related column in both tables.
- Only records with matching DepartmentID values are returned.

**Example 2: Retrieve Specific Columns**

```sql
SELECT
    Employees.EmployeeID,
    Employees.FirstName,
    Employees.LastName,
    Departments.DepartmentName
FROM Employees
INNER JOIN Departments
ON Employees.DepartmentID = Departments.DepartmentID;
```

Output:

| EmployeeID | FirstName | LastName | DepartmentName |
|---|---|---|---|
| 1 | John | Doe | Sales |
| 2 | Jane | Smith | Marketing |
| 3 | Jim | Brown | Sales |
| 4 | Jake | White | Developer |

## Explanation

- Employee John has DepartmentID 101, which matches Sales.
- Employee Jane has DepartmentID 102, which matches Marketing.
- Employee Jim has DepartmentID 101, which matches Sales.
- Employee Jake has DepartmentID 103, which matches Developer.

Since all employees have matching DepartmentID values in the Departments table, all 4 records are returned.

## Key Points

- INNER JOIN returns only matching records from both tables.
- It combines tables based on a related column.
- The ON keyword specifies the JOIN condition.
- If a record does not have a matching value in the other table, it will not appear in the result.
- INNER JOIN and JOIN are equivalent in SQL.
- INNER JOIN can be used with two or more tables.
