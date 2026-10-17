# SQL basics

SQL (Structured Query Language) is used to define, query, and change data in relational databases.

## A basic query

```sql
SELECT column_name
FROM table_name
WHERE condition
ORDER BY column_name;
```

`SELECT`, `FROM`, `WHERE`, and `ORDER BY` are clauses in this query. The order of clauses matters.

## Common SELECT clauses

```sql
SELECT DISTINCT column_name
FROM table_name
WHERE condition
GROUP BY column_name
HAVING aggregate_condition
ORDER BY column_name
OFFSET 0 ROWS FETCH NEXT 10 ROWS ONLY;
```

Use only the clauses needed for your query. In SQL Server, `TOP (n)` is another way to limit rows; `OFFSET ... FETCH` is useful for paging sorted results.

The logical processing order of a `SELECT` query is generally `FROM`/`JOIN`, `WHERE`, `GROUP BY`, `HAVING`, `SELECT`, `DISTINCT`, `ORDER BY`, then `OFFSET`/`FETCH`. This helps explain why a select-list alias is generally not available in `WHERE`.

## Common SQL statement groups

- **DDL (Data Definition Language):** defines database objects, for example `CREATE`, `ALTER`, and `DROP`.
- **DML (Data Manipulation Language):** reads or changes data, for example `SELECT`, `INSERT`, `UPDATE`, and `DELETE`.
- **Transaction control:** manages transactions, for example `BEGIN TRANSACTION`, `COMMIT`, and `ROLLBACK`.

SQL syntax varies by database system. The examples in this repository are primarily for Microsoft SQL Server (T-SQL).
