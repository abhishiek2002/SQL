# Learn how to use the DELETE SQL command

## Instructions:

Video Link : [Delete Command](https://www.loom.com/share/d6d77bc2e73145e39d6c152e7800e36c?sid=8ec3df90-4e88-42b5-85b4-1a0cdc03b58f)

Watch the video on the DELETE SQL command to understand its syntax and use cases.

Once you have learned the concept, complete the following task:

## Deliverables:

You are managing the employees table, which contains information about employees in a company. The table has the following structure:

    id,name,age,department,salary

### Task:

The employee with id = 102 has left the company and needs to be removed from the employees table.

Write an SQL query to delete this employee's record from the table.

### Expected Output:

The record for the employee with id = 102 will be deleted from the employees table.

# Query

```sql

--Don't Touch this part of the code

--Create table for it
-- CREATE TABLE employees (
--     id INT,
--     name VARCHAR(100),
--     age INT,
--     department VARCHAR(100),
--     salary INT
-- );

--Write your code below this

delete from employees where id = 102;
```
