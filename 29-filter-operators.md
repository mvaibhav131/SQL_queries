# Filter operators

Use these predicates in a `WHERE` clause to match values, ranges, and missing data.

## IN

`IN` matches any value in a list:

```sql
SELECT ProductName, Category
FROM Products
WHERE Category IN ('Books', 'Games');
```

## BETWEEN

`BETWEEN` includes both endpoints:

```sql
SELECT ProductName, Price
FROM Products
WHERE Price BETWEEN 10 AND 50;
```

For date ranges, a half-open interval is often safer when the column contains a time:

```sql
SELECT OrderID, OrderDate
FROM Orders
WHERE OrderDate >= '20260101'
  AND OrderDate <  '20270101';
```

## LIKE

In SQL Server, `%` matches zero or more characters and `_` matches one character:

```sql
SELECT CustomerName
FROM Customers
WHERE CustomerName LIKE 'A%';
```

## NULL

`NULL` means a value is missing or unknown. Test it with `IS NULL` or `IS NOT NULL`, not `= NULL`:

```sql
SELECT CustomerName
FROM Customers
WHERE Region IS NULL;
```

Comparisons with `NULL` evaluate to unknown, not true or false; rows are returned by `WHERE` only when its predicate is true.
