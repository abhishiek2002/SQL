# HAVING Clause

The HAVING clause is used in SQL to filter records based on aggregate function results.

Unlike the WHERE clause, which filters rows before grouping, the HAVING clause filters groups after an aggregation has been performed.

Watch the following video to understand how the HAVING clause works in SQL. Then, answer the question below to practice your understanding.

## Deliverables:

Write a query to find all departments with a total salary greater than 120,000.

The query should group the data by department and use the HAVING clause to filter the results based on the total salary.

### Sample input data:

employee_id|name|department|salary

    1|Alice|HR|50000

    2|Bob|IT|60000

    3|Charlie|Sales|55000

    4|David|IT|62000

    5|Eve|Marketing|52000

    6|Frank|HR|48000

    7|Grace|IT|63000

    8|Hank|Sales|59000

    9|Ivy|Marketing|51000

    10|Jack|HR|52000

### Expected Output:

department|total_salary

    HR|150000

    IT|185000

# Query Code

```sql

-- -- Create the employees table
-- CREATE TABLE employees (
--     employee_id INT PRIMARY KEY,
--     name VARCHAR(50),
--     department VARCHAR(50),
--     salary INT
-- );


--Write your code here

select department, sum(salary) as total_salary from employees group by department having total_salary > 120000;
```
