# SQL Queries

A beginner-friendly SQL learning repository. The lessons use **Microsoft SQL Server (T-SQL)** and are intended to be run in SQL Server Management Studio (SSMS).

## Start here

1. Follow [00 — SQL basics](./00-sql-basics.md) for query structure and terminology.
2. Install [SSMS and LocalDB](./01-installation.md), then connect to `(localdb)\MSSQLLocalDB`.
3. Create a practice database with [02 — Create a database](./02-create-database.md).
4. Follow the numbered lessons in order. Most examples use the `employee_info` table from [03 — Create a table](./03-create-table.md).

Some examples use `Customers`, `Products`, or other sample tables. Those examples require you to create the named table or install a sample database first.

## Lessons

### Foundations and data changes.

| # | Topic | Lesson |
|---|---|---|
| 00 | SQL and query basics | [SQL basics](./00-sql-basics.md) |
| 01 | Install tools and connect | [Installation](./01-installation.md) |
| 02 | Create and select a database | [Create database](./02-create-database.md) |
| 03 | Define a table | [CREATE TABLE](./03-create-table.md) |
| 04 | Read rows and columns | [SELECT](./04-select-data.md) |
| 05 | Add rows | [INSERT](./05-insert-rows.md) |
| 06 | Change rows | [UPDATE](./06-update-rows.md) |
| 07 | Remove rows | [DELETE](./07-delete-rows.md) |
| 08 | Remove a table | [DROP TABLE](./08-drop-table.md) |
| 09 | Sort results | [ORDER BY](./09-order-by.md) |
| 10 | Filter rows | [WHERE](./10-where.md) |
| 11 | Summarize values | [Aggregate functions](./11-aggregate-functions.md) |
| 12 | Count string characters | [LEN](./12-string-length.md) |
| 13 | Change text case | [UPPER and LOWER](./13-case-conversion.md) |
| 14 | Calculate numeric values | [Numeric functions](./14-numeric-functions.md) |
| 15 | Transform strings | [String functions](./15-string-functions.md) |
| 16 | Combine filter conditions | [AND, OR, NOT](./16-logical-operators.md) |
| 17 | Work with date and time | [Date and time](./17-date-and-time.md) |
| 18 | Group rows | [GROUP BY](./18-group-by.md) |
| 19 | Filter groups | [HAVING](./19-having.md) |
| 20 | Change a table | [ALTER TABLE](./20-alter-table.md) |
| 21 | Create a table from query results | [SELECT INTO](./21-select-into.md) |
| 22 | Name query results and tables | [Aliases](./22-aliases.md) |

### Querying beyond the basics.

| # | Topic | Lesson |
|---|---|---|
| 23 | Combine related tables | [JOIN overview](./23-joins-overview.md) |
| 24 | Keep matching rows | [INNER JOIN](./24-inner-join.md) |
| 25 | Keep unmatched rows too | [OUTER JOIN](./25-outer-joins.md) |
| 26 | Nest a query | [Subqueries](./26-subqueries.md) |
| 27 | Return a chosen page or number of rows | [TOP and pagination](./27-top-and-pagination.md) |
| 28 | Remove duplicate results | [DISTINCT](./28-distinct.md) |
| 29 | Match ranges, lists, patterns, and missing values | [Filter operators](./29-filter-operators.md) |
| 30 | Enforce valid data | [Constraints](./30-constraints.md) |
| 31 | Choose a result based on conditions | [CASE](./31-case-expression.md) |
| 32 | Combine query results | [UNION and EXCEPT](./32-set-operators.md) |
| 33 | Name a query result for reuse | [Common table expressions](./33-common-table-expressions.md) |
| 34 | Test whether related rows exist | [EXISTS](./34-exists.md) |
| 35 | Calculate across related rows | [Window functions](./35-window-functions.md) |
| 36 | Commit or undo changes safely | [Transactions](./36-transactions.md) |

## Conventions and safety

- Unless a lesson explicitly says otherwise, examples use SQL Server/T-SQL. Syntax may differ in PostgreSQL, MySQL, SQLite, or other systems.
- Examples are educational; check the database, table, and `WHERE` condition before running `UPDATE`, `DELETE`, `DROP`, or other write statements.
- Use a practice database. The transaction lesson demonstrates how to inspect a change and roll it back before committing.
