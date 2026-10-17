# JOIN overview

`JOIN` combines rows from tables using a related column or another join condition. A join condition is written with `ON`; related columns do not have to share a name, but their values and data types should be compatible.

## Join types

- **INNER JOIN** keeps rows with a match on both sides.
- **LEFT OUTER JOIN** keeps every left-side row and adds matching right-side values; unmatched right-side columns are `NULL`.
- **RIGHT OUTER JOIN** keeps every right-side row and adds matching left-side values.
- **FULL OUTER JOIN** keeps rows from either side, matching where possible.
- **CROSS JOIN** returns every combination of rows from both tables.

```sql
SELECT e.empName, d.departmentName
FROM employee_info AS e
INNER JOIN departments AS d
    ON d.deptID = e.deptID;
```

For an inner join, `JOIN` and `INNER JOIN` mean the same thing. See the [INNER JOIN](./24-inner-join.md) and [OUTER JOIN](./25-outer-joins.md) lessons for complete examples.
