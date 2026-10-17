
# AND, OR, and NOT

Use logical operators in `WHERE` to combine or reverse conditions:

The AND and OR operators are used to filter records based on more than one condition :-

The AND operator displays a record if all the conditions separated by AND are TRUE.
The OR operator displays a record if any of the conditions separated by OR is TRUE.
The NOT operator displays a record if the condition(s) is NOT TRUE.

SELECT column1, column2
FROM table_name
WHERE condition1 AND condition2;

SELECT column1, column2
FROM table_name
WHERE condition1 OR condition2;

SELECT column1, column2
FROM table_name
WHERE NOT condition;

## Examples

```sql
SELECT * FROM Customers WHERE Country = 'Germany' AND City = 'Berlin';
SELECT * FROM Customers WHERE City = 'Berlin' OR City = 'Stuttgart';
SELECT * FROM Customers WHERE NOT Country = 'Germany';
SELECT * FROM Customers WHERE NOT Country = 'Germany' AND NOT Country = 'USA';
```

Use parentheses when mixing `AND` and `OR` so the intended order is explicit. `AND` is evaluated before `OR`.

