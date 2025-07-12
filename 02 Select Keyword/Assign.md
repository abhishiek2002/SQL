# Finally, we are starting with the SELECT statement in SQL.

To help you grasp the concept, watch the provided video for an in-depth explanation.

Video- [Using Select Statement](https://www.loom.com/share/b61c38e92b064c2d96f9ddcf922016a5?sid=b133c232-92e3-45a0-b4e8-5643253021f2)

After viewing the video and understanding the key points, apply your knowledge to complete the SQL queries.

## Deliverables:

    Write a query to display all records from the enrollments table, showing the student name, course ID, and enrollment date.

## Expected Output Example:

### Given the enrollments table:

    student_id|student_name|course_id|enrollment_date

    1|Ryan|2|2024-01-10

    2|Joanna|2|2024-02-12

    3|David|1|2024-03-15

### The output should be:

    student_name|course_id|enrollment_date

    Ryan|2|2024-01-10

    Joanna|2|2024-02-12

    David|1|2024-03-15


# Query

```sql

--Don't change this part of the code

-- CREATE TABLE enrollments (
--   student_id INTEGER,
--   student_name TEXT,
--   course_id INTEGER,
--   enrollment_date DATE
-- );

-- Write your code below this

select student_name, course_id, enrollment_date from enrollments;
```