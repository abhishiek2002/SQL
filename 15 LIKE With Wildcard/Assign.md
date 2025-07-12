# LIKE Operator Question
Watch the following video to understand how we can implement wildcards in our queries.

Video- [Wildcards](https://www.loom.com/share/013aa4a8d5be44acb11dd067f138b8d8?sid=8fcb1f1e-ddf7-4d38-a315-1956b829d60a)

## Description:

Write a query to list the names of employees whose names start with the letter 'A' using the LIKE operator.

### Sample Input Data:

employee_id | name | department | salary

    1 | Alice | HR | 50000

    2 | Bob | IT | 60000

    3 | Charlie | Sales | 55000

    4 | David | IT | 62000

    5 | Eve | Marketing | 52000

### Query:

Write a SQL query to retrieve the names of employees whose name begins with 'A' using the LIKE operator.

### Expected Output:

name

    Alice


## Query Code

```sql

-- Create the table schema for employees

-- CREATE TABLE employees (
--     employee_id INT,
--     name VARCHAR(100),
--     department VARCHAR(50),
--     salary INT
-- );

--Write your code here using LIKE Operator

select name from employees where name LIKE "A%";
```