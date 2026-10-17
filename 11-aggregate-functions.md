# Aggregate functions

An aggregate function calculates a single result from a set of values.

MIN() - returns the smallest value within the selected column
MAX() - returns the largest value within the selected column
COUNT() - returns the number of rows in a set
SUM() - returns the total sum of a numerical column
AVG() - returns the average value of a numerical column
Aggregate functions ignore null values (except for COUNT())

Examples of sum aggregate function :-
select sum(empSalary) from employee_info 
select avg(empSalary) from employee_info 
select max(empSalary) from employee_info 
select min(empSalary) from employee_info 
select count(empName) from employee_info 
