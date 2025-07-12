# Using the WHERE Clause in SQL

Before attempting this question, watch the video on the use of the WHERE clause in SQL. The video will guide you through how to filter data based on specific conditions in a column.

Video Link : [Filtering using Where Clause](https://www.loom.com/share/cf7145a1ba244ab98b6e0ad6c0a941ed?sid=78f3b5c8-d9ae-455e-b1f5-6e18c001f616)

## Deliverables:

You are given the following students table, which stores information about students and the courses they are enrolled in.

### Task:

Write an SQL query to retrieve the student_name of all the students who are enrolled in the course with gender as 'F'.

#### Example:

`Input:`

students table:

| student_id | student_name | gender | course_id |

    |1|Ryan|M|2

    |2|Joanna|F|1

    |3|David|M|3

    |4|Sarah|F|2

`Output:`

student_name

    Joanna

    Sarah


# Query

```sql

--Don't change this part of the code

-- Create the students table
-- CREATE TABLE students (
--   student_id INTEGER PRIMARY KEY,
--   student_name TEXT NOT NULL,
--   gender TEXT NOT NULL,
--   course_id INTEGER NOT NULL
-- );

-- Write your code here

select student_name from students where gender = 'F'
```