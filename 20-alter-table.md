# ALTER TABLE

`ALTER TABLE` changes the structure of an existing table, including its columns and constraints. This example creates a practice table, then adds, alters, and drops a column:

```sql
CREATE TABLE CompanyInfo (
    Id INT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    Active BIT NOT NULL
);

ALTER TABLE CompanyInfo ADD Revenue DECIMAL(10, 2) NULL;

INSERT INTO CompanyInfo (Id, Name, Active, Revenue)
VALUES (1, 'Example Company', 1, 6747.00);

ALTER TABLE CompanyInfo ALTER COLUMN Name VARCHAR(100) NOT NULL;
ALTER TABLE CompanyInfo DROP COLUMN Revenue;
```

The final statement permanently removes the `Revenue` column and its values. This example is intended to be run once in a practice database.

Use `ALTER TABLE ... ADD CONSTRAINT` and `ALTER TABLE ... DROP CONSTRAINT` to add or remove constraints. See [table constraints](./30-constraints.md).
