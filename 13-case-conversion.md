# UPPER and LOWER

`UPPER()` converts text to uppercase; `LOWER()` converts it to lowercase.

```sql
SELECT UPPER('this is converted to upper case') AS UpperText;
SELECT LOWER('HELLO') AS LowerText;
SELECT empName, LOWER(empName) AS LowerName
FROM employee_info;
```

These functions change the value shown in the query result; they do not update the stored column.
