Write a query to retrieve all the information from the enrollments table, including student ID, student name, course ID, and enrollment date.

## Expected Output Example:

Given the enrollments table:

    student_id|student_name|course_id|enrollment_date

    1|Ryan|2|2024-01-10

    2|Joanna|2|2024-02-12

    3|David|1|2024-03-15

## The output should be:

    student_id|student_name|course_id|enrollment_date

    1|Ryan|2|2024-01-10

    2|Joanna|2|2024-02-12

    3|David|1|2024-03-15

```sql

--Don't change this part of the code

-- Create the enrollments table
-- CREATE TABLE enrollments (
--   student_id INTEGER,
--   student_name TEXT,
--   course_id INTEGER,
--   enrollment_date DATE
-- );

-- Write your code here

select * from enrollments;
```
