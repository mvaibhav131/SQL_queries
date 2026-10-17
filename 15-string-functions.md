# String functions

`LTRIM` and `RTRIM` remove leading and trailing spaces.

```sql
SELECT LTRIM('   trim left side space'); -- Remove leading spaces.

SELECT RTRIM('trim right side space      '); -- Remove trailing spaces.

SELECT LTRIM('  hihiouiou'), RTRIM('kjlkjlkjl       '); -- Trim either side.

SELECT SUBSTRING('microsoft', 1, 4); -- micr

SELECT REPLACE('Vaibhav', 'bhav', 'more'); -- Vaimore

SELECT REPLICATE('Vaibhav ', 6); -- Repeat the string six times.

`REPLICATE` repeats a string the number of times specified by its second argument.
```
