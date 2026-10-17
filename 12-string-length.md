# LEN

`LEN()` returns the number of characters in a string.

```sql
SELECT empName, LEN(empName)
FROM employee_info;
```

```sql
SELECT LEN('vaibhavmore.in');
```

`LEN()` counts spaces between words but excludes trailing spaces. Use `DATALENGTH()` when you need the number of bytes instead.
