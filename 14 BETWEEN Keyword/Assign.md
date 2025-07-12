# BETWEEN Operator Question

## Description:

Write a query to list the names and salaries of employees whose salary is between 50,000 and 60,000 (inclusive) using the BETWEEN operator.

### Sample Input Data:

employee_id | name | department | salary

    1 | Alice | HR | 50000

    2 | Bob | IT | 60000

    3 | Charlie | Sales | 55000

    4 | David | IT | 62000

    5 | Eve | Marketing | 52000

### Query:

Write a SQL query to list the names and salaries of employees whose salary is between 50,000 and 60,000 (inclusive) using the BETWEEN operator.

### Expected Output:

name | salary

    Alice | 50000

    Charlie | 55000

    Bob | 60000

# Query Answer

```sql

-- Create the table schema for employees

-- CREATE TABLE employees (
--     employee_id INT,
--     name VARCHAR(100),
--     department VARCHAR(50),
--     salary INT
-- );

--Write your code here using BETWEEN Operator

select name, salary from employees where salary between 50000 and 60000;
```
