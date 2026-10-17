# Table constraints

Constraints protect data by rejecting rows that break rules. Define them when creating a table or add them later with `ALTER TABLE`.

```sql
CREATE TABLE Departments (
    DepartmentID INT CONSTRAINT PK_Departments PRIMARY KEY,
    DepartmentName VARCHAR(100) NOT NULL
);

CREATE TABLE Staff (
    StaffID INT CONSTRAINT PK_Staff PRIMARY KEY,
    Email VARCHAR(255) CONSTRAINT UQ_Staff_Email UNIQUE,
    Age INT CONSTRAINT CK_Staff_Age CHECK (Age >= 18),
    DepartmentID INT,
    IsActive BIT CONSTRAINT DF_Staff_IsActive DEFAULT (1),
    CONSTRAINT FK_Staff_Departments
        FOREIGN KEY (DepartmentID)
        REFERENCES Departments (DepartmentID)
);
```

- `PRIMARY KEY` identifies each row and does not allow `NULL`.
- `FOREIGN KEY` requires a referenced row to exist in the related table.
- `UNIQUE` prevents duplicate values.
- `CHECK` requires a condition to be true.
- `DEFAULT` supplies a value when an insert omits that column.
- `NOT NULL` requires a value to be provided.

Insert a department before inserting staff that references it. A default is used when the column is omitted; explicitly inserting `NULL` does not request the default.
