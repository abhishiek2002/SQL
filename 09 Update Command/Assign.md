# Learn how to use the UPDATE SQL command.

Video Link: [Update Command](https://www.loom.com/share/be1e3ba5bf1c4dafb78526a53cc6304f?sid=c4a12ee6-064e-4dff-90bb-62ea7b2979c9)

## Instructions:

Watch the video on the UPDATE SQL command to understand its syntax and use cases.
Once you have learned the concept, complete the following task:

## Deliverables:

You are managing the employees table, which contains information about employees in a company. The table has the following structure:

    id (INT)

    name (VARCHAR)

    age (INT)

    department (VARCHAR)

    salary (INT)

### Task:
The employee with id = 104 has received a salary raise and a promotion. You need to:

    Update the employee's salary to 75000.
    Update the employee's department to 'Senior Finance'.

Write an SQL query to accomplish this.


# Query

```sql

--Don't change this part of the code

--Create table employees
-- CREATE TABLE employees (
--     id INT PRIMARY KEY,
--     name VARCHAR(50),
--     age INT,
--     department VARCHAR(50),
--     salary INT
-- );

--Write your code here

update employees set salary = 75000, department = 'Senior Finance' where id = 104;
```
