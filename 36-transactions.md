# Transactions

A transaction groups changes so they can be committed together or rolled back. Practice in a test database and verify the affected rows before committing.

This example intentionally rolls back its update:

```sql
BEGIN TRY
    BEGIN TRANSACTION;

    UPDATE dbo.employee_info
    SET empSalary = empSalary + 100
    WHERE empId = 1;

    SELECT empId, empSalary
    FROM dbo.employee_info
    WHERE empId = 1;

    ROLLBACK TRANSACTION;
END TRY
BEGIN CATCH
    IF XACT_STATE() <> 0
        ROLLBACK TRANSACTION;

    THROW;
END CATCH;
```

- `COMMIT TRANSACTION` makes the changes permanent.
- `ROLLBACK TRANSACTION` undoes uncommitted changes.
- Check the `WHERE` condition and affected rows before choosing to commit.

To keep the changes instead, use `COMMIT TRANSACTION` only after reviewing the results. Do not run both `COMMIT` and `ROLLBACK` for the same transaction.
