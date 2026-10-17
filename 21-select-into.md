
# SELECT INTO

In SQL Server, `SELECT INTO` creates a new table and inserts the rows returned by a query. The destination table must not already exist.

Copy all columns into a new table in the current database:

```sql
SELECT *
INTO newtable
FROM oldtable
WHERE condition;
```

Copy selected columns:

```sql
SELECT column1, column2
INTO newtable
FROM oldtable;
```

Copy a table from another database into the current database:

```sql
SELECT *
INTO emp_table_copied
FROM Sample_DB.dbo.employee_info;
```

To create the table in a different database, use a three-part destination name:

```sql
SELECT CustomerName, ContactName
INTO BackupDb.dbo.CustomersBackup
FROM SampleDb.dbo.Customers;
```

`SELECT INTO` copies the query's columns and rows, but does not copy indexes, constraints, or triggers. The Access-style `IN 'Backup.mdb'` syntax is not valid in SQL Server.
