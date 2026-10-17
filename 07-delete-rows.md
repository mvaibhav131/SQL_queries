
# Delete rows

`DELETE` removes rows from a table. Omitting `WHERE` removes every row.

```sql
DELETE FROM table_name WHERE condition;
```

```sql
-- Delete the row where empId is 3.
DELETE FROM employee_info
WHERE empId = 3;
```

Delete All Records

It is possible to delete all rows in a table without deleting the table. This means that the table structure, attributes, and indexes will be intact:

```sql
DELETE FROM table_name;
```

The following SQL statement deletes all rows in the "Customers" table, without deleting the table:

Example:
```sql
-- This permanently deletes every row in Customers.
DELETE FROM Customers;
```
