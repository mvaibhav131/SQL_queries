# OUTER JOIN

The OUTER JOIN is used to retrieve matching and non-matching records from two or more tables.

There are three types of OUTER JOIN:

1. **LEFT OUTER JOIN:** Returns all records from the left table and matching records from the right table.
2. **RIGHT OUTER JOIN:** Returns all records from the right table and matching records from the left table.
3. **FULL OUTER JOIN:** Returns all records from both tables, including matching and non-matching records.

**Note:** If no matching record is found, the missing columns from the other table return NULL values.

## 1. LEFT OUTER JOIN

The LEFT OUTER JOIN returns all records from the left table and only matching records from the right table.

If no matching record is found in the right table, NULL values are returned for the right table columns.

### Syntax

```sql
SELECT column_names
FROM table1
LEFT OUTER JOIN table2
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

## LEFT OUTER JOIN Example

Now, join both tables based on the related column `DepartmentID`.

**Example 1: Retrieve All Columns**

```sql
SELECT *
FROM Employees
LEFT OUTER JOIN Departments
ON Employees.DepartmentID = Departments.DepartmentID;
```

Explanation:

- Employees is the left table.
- Departments is the right table.
- All records from Employees will be returned.
- Matching DepartmentID records from Departments will be included.
- If no matching department exists, DepartmentName will be NULL.

**Example 2: Retrieve Specific Columns**

```sql
SELECT
    Employees.EmployeeID,
    Employees.FirstName,
    Employees.LastName,
    Departments.DepartmentName
FROM Employees
LEFT OUTER JOIN Departments
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

- John belongs to Sales (DepartmentID 101).
- Jane belongs to Marketing (DepartmentID 102).
- Jim belongs to Sales (DepartmentID 101).
- Jake belongs to Developer (DepartmentID 103).

Since all employees have matching departments, all 4 records are returned.

## Example 3: LEFT JOIN with No Matching Record

Insert one more employee with a DepartmentID that does not exist in the Departments table.

```sql
INSERT INTO Employees
(EmployeeID, FirstName, LastName, DepartmentID)
VALUES
(5, 'David', 'Wilson', 105);
```

Now execute the LEFT JOIN:

```sql
SELECT
    Employees.EmployeeID,
    Employees.FirstName,
    Employees.LastName,
    Departments.DepartmentName
FROM Employees
LEFT OUTER JOIN Departments
ON Employees.DepartmentID = Departments.DepartmentID;
```

Output:

| EmployeeID | FirstName | LastName | DepartmentName |
|---|---|---|---|
| 1 | John | Doe | Sales |
| 2 | Jane | Smith | Marketing |
| 3 | Jim | Brown | Sales |
| 4 | Jake | White | Developer |
| 5 | David | Wilson | NULL |

Explanation:

- David has DepartmentID 105.
- DepartmentID 105 does not exist in the Departments table.
- LEFT JOIN still returns David's record because Employees is the left table.
- DepartmentName returns NULL because no matching department exists.

## Key Points

- LEFT JOIN returns all records from the left table.
- It returns matching records from the right table.
- If no matching record exists, right table columns return NULL.
- LEFT JOIN and LEFT OUTER JOIN are the same.
- The ON keyword specifies the JOIN condition.
- LEFT JOIN is useful when we want all records from one table, even if related data is missing from another table.
