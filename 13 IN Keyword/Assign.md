# Watch the following video

Video 1 - [Like,In and Between Introduction](https://www.loom.com/share/6450e1277d1440958c70c503e0d0bee7?sid=dcee9299-db48-4f57-ae25-9988c533b98a)

Video 2- [Like,In and Between Implementation](https://www.loom.com/share/e3ecdedd3dac4336b2b11ced4b44a5c3?sid=4460dcd0-11e6-492c-aa0e-0ed22d2132e3)

to understand the concepts of the LIKE, IN, and BETWEEN operators in SQL.

These operators are commonly used to filter and retrieve specific rows from a table based on conditions.

Ensure you have a clear understanding of how each operator functions and the scenarios where they are applied.

## Deliverables:

You are managing a company's database, which includes a table named employees with the following schema and sample data:

### Schema:

Column Name | Data Type | Description

    employee_id | INT | Unique identifier for each employee

    name | VARCHAR | The name of the employee

    department | VARCHAR | The department where the employee works

    salary | INT | The salary of the employee

### Sample Input Data:

employee_id | name | department | salary

    1 | Alice | HR | 50000

    2 | Bob | IT | 60000

    3 | Charlie | Sales | 55000

    4 | David | IT | 62000

    5 | Eve | Marketing | 52000

### Query :

Write a query to list the names of employees who work in the "IT" or "Sales" departments using the IN operator.

### Output:

name

    Bob

    Charlie

    David

# Query Answer

```sql

-- Create the table schema for employees

-- CREATE TABLE employees (
--     employee_id INT,
--     name VARCHAR(100),
--     department VARCHAR(50),
--     salary INT
-- );

--Write your code here using IN Operator

select name from employees where department in ("IT","Sales");
```
