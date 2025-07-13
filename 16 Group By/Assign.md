Hey there!

# Watch the following video to understand how the GROUP BY clause works in SQL.

Video Link: [Group by](https://www.loom.com/share/1762959f35254e94bae9b2ee18027938?sid=b453eeb2-52ae-4518-af79-fc6d2c4a5e89)

    This clause helps you organize and summarize your data efficiently.

    Pay attention to how it is used to group data based on one or more columns and how aggregate functions like SUM, COUNT, AVG, and others work in conjunction with it.

    Once you've finished watching, complete the questions below to test your understanding of the GROUP BY clause.

## Deliverables:

Find the Total Salary by Department

### Description:

Write a query to calculate the total salary for each department using the GROUP BY clause.

Note: Make use of alias for creating a resultant column as total_salary

### Sample Input Data

employee_id|name|department|salary

    1|Alice|HR|50000

    2|Bob|IT|60000

    3|Charlie|Sales|55000

    4|David|IT|62000

    5|Eve|Marketing|52000

    6|Andrew|HR|48000

### Expected Output:

department|total_salary

    HR|98000

    IT|122000

    Sales|55000

    Marketing|52000

# Query Code

```sql

-- Create the employees table
-- CREATE TABLE employees (
--     employee_id INT PRIMARY KEY,
--     name VARCHAR(100),
--     department VARCHAR(100),
--     salary INT
-- );

--Write your code here

select department, sum(salary) from employees group by department;
```
