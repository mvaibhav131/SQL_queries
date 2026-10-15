# SQL Subquery

A Subquery is a query written inside another SQL query.

It is used to retrieve data that will be used by the main query to perform an operation.

Subqueries are also called **Inner Queries** or **Nested Queries**.

The main query that contains the subquery is called the **Outer Query**.

## Syntax

```sql
SELECT column_names
FROM table1
WHERE column_name = (
    SELECT column_name
    FROM table2
);
```

## Example

```sql
SELECT *
FROM t1
WHERE column1 = (
    SELECT column1
    FROM t2
);
```

## Explanation

**1. Outer Query:**

```sql
SELECT *
FROM t1
WHERE column1 = (...);
```

- This is the main query.
- It retrieves records from table `t1`.
- It uses the result returned by the subquery to filter records.

**2. Inner Query (Subquery):**

```sql
SELECT column1
FROM t2;
```

- This query is executed independently before the outer query in this simple example.
- It retrieves the value of `column1` from table `t2`.
- The result is used by the outer query.

**Note:** The `=` operator requires the subquery to return only one value. If the subquery returns multiple rows, use `IN` instead.

## Example with IN Operator

```sql
SELECT *
FROM t1
WHERE column1 IN (
    SELECT column1
    FROM t2
);
```

Explanation:

- The inner query retrieves values from `t2`.
- The outer query retrieves matching records from `t1`.
- The `IN` operator allows the subquery to return multiple values.

## Key Points

- A Subquery is a query inside another SQL query.
- It is also called an Inner Query or Nested Query.
- The main query is called the Outer Query.
- Subqueries are commonly used with SELECT, INSERT, UPDATE, and DELETE statements.
- Subqueries can be used with WHERE, FROM, and SELECT clauses.
- Use `=` when the subquery returns a single value.
- Use `IN` when the subquery returns multiple values.
- Subqueries help simplify complex SQL operations.
