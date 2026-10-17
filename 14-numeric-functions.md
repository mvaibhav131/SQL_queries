
# Numeric functions

| Function | Purpose |
|---|---|
| `ABS` | Returns the absolute value. |
| `CEILING` / `FLOOR` | Round up or down to an integer. |
| `SIGN` | Returns `-1`, `0`, or `1` depending on the sign. |
| `SQRT` / `SQUARE` | Return the square root or square. |
| `SIN` / `COS` / `TAN` | Trigonometric functions; input angles are in radians. |
| `DEGREES` | Converts radians to degrees. |
| `PI` | Returns pi. |
| `EXP` | Returns e raised to a power. |
| `ISNUMERIC` | Checks whether an expression can be interpreted as a numeric type. |

Examples:

```sql
SELECT ABS(-12); -- 12
SELECT CEILING(45.66); -- 46
SELECT FLOOR(55.67); -- 55
SELECT SIGN(5); -- 1
SELECT SIGN(-89); -- -1
SELECT SIGN(0); -- 0
SELECT SQUARE(5); -- 25
SELECT SQRT(81); -- 9
SELECT COS(30); -- 30 is interpreted as radians.
SELECT DEGREES(1.5); -- Convert radians to degrees.
SELECT PI();
SELECT EXP(1); -- Approximately 2.71828182845905.
SELECT ISNUMERIC(45), ISNUMERIC('65'), ISNUMERIC('hello'); -- 1, 1, 0
```

`ISNUMERIC` can return 1 for some currency and scientific-notation strings. It does not guarantee that a value can be converted to a particular numeric type; use `TRY_CONVERT` when checking for a specific type.

`SUM` is an aggregate function (covered in [Aggregate functions](./11-aggregate-functions.md)):

```sql
SELECT SUM(Quantity) FROM OrderDetails WHERE ProductId = 11;
```
