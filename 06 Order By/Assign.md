# Using the Order by Clause in SQL

Before attempting this question, watch the video on the use of the Order by in SQL. The video will guide you through how to ordering data based on specific conditions in a column.

Video Link: [Order By](https://www.loom.com/share/90d619156bcf474a93a3eb99ebb58fa5?sid=d1397163-36ac-410a-af14-2c23a2844acf)

## Deliverables:

Write an SQL query to retrieve the names of all employees from a table called Employees, ordered by their Salary in descending order.

### Sample Table Structure:

Employee

    ID| Name| Salary

    1| Alice| 50000

    2| Bob| 60000

    3| Charlie| 55000

### Expected Output:

Name

    Bob

    Charlie

    Alice

# Query

```sql

--Don't change this part of the code

-- Create the Employees table
-- CREATE TABLE Employees (
--     EmployeeID INT PRIMARY KEY,
--     Name VARCHAR(50),
--     Salary INT
-- );

--Write your code here

select Name from Employees order by Salary desc;
```
