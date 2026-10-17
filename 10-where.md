
# WHERE

`WHERE` filters rows before they are returned or changed.

SELECT column1, column2, ... FROM table_name WHERE condition;

Note: The WHERE clause is not only used in SELECT statements, it is also used in UPDATE, DELETE, etc.!


-- Filter for the employee whose ID is 3.
SELECT empName FROM employee_info WHERE empId = 3;


-- Select all customers from Mexico.
SELECT * FROM Customers WHERE Country = 'Mexico';
