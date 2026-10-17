# Date and time

Use a date/time data type that matches the values and precision your application needs.

SQL Server date and time data types include:

- `DATE` stores a calendar date.
- `TIME` stores a time of day.
- `DATETIME`, `SMALLDATETIME`, and `DATETIME2` store both a date and a time; `DATETIME2` supports configurable fractional-second precision.

In SQL Server, `TIMESTAMP` is a deprecated synonym for `ROWVERSION`, not a date/time type. Use `DATE`, `TIME`, `DATETIME`, or `DATETIME2` for dates and times.

Examples:

```sql
SELECT GETDATE() AS Today_date;

SELECT SYSDATETIME() AS Today_date;

SELECT CURRENT_TIMESTAMP AS Today_date;

SELECT DATENAME(month, CURRENT_TIMESTAMP) AS Month;

SELECT DATENAME(year, CURRENT_TIMESTAMP) AS Year;

SELECT DATENAME(hour, CURRENT_TIMESTAMP) AS Hour;

SELECT DATENAME(minute, CURRENT_TIMESTAMP) AS Minute;

SELECT DATENAME(second, CURRENT_TIMESTAMP) AS Second;

SELECT DATEDIFF(year, '19970524', CURRENT_TIMESTAMP) AS YearsSince1997;

SELECT DATEDIFF(month, '19970524', CURRENT_TIMESTAMP) AS MonthsSince1997;

SELECT DATEDIFF(year, '19970524', '20200103') AS YearBoundariesCrossed;

SELECT DATEADD(year, 100, CURRENT_TIMESTAMP) AS DateIn100Years;

SELECT DATEADD(month, 32, CURRENT_TIMESTAMP) AS DateIn32Months;
```
