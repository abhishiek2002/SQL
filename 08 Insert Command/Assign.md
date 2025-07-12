# Using the INSERT Command in SQL

## Video Links:

[Insert Introduction](https://www.loom.com/share/82f7bbff03844cce95d405b6113ff944?sid=a832aa5b-bd7e-45b6-8e59-582e3481f849)

[Insert Implementation](https://www.loom.com/share/f7980917914c431f81a6fcc9a9a53a9b?sid=0940686c-e56a-48ed-b072-d59ed6ed459f)

## Before attempting this question, watch the video on the INSERT statement in SQL. It demonstrates two approaches to adding data to a table:

    With Column Names: Ensures clarity by specifying the target columns, reducing errors if the table structure changes.
    Without Column Names: Adds values directly in the table’s column order but requires accuracy in matching the column sequence.

## Deliverables:

### Question:

We have a table employees. The employee has the following details:

    id
    name
    age
    department
    salary

Write an SQL query to add a new employee to the employees table such that we are making the entries as

    id :104
    name : 'Michael Johnson'
    age : 29
    department :'Finance'
    salary : 65000


# Query

```sql

--Don't change this part of the code
-- Create the Employees table

-- CREATE TABLE employees (
--     id INT PRIMARY KEY,
--     name VARCHAR(50) NOT NULL,
--     age INT NOT NULL,
--     department VARCHAR(50),
--     salary INT
-- );


--Write your code here

insert into employees values (104, 'Michael Johnson', 29, 'Finance', 65000);
```
