# Watch the following video to understand working with unique values from the columns.

Video link: [Select with distinct](https://www.loom.com/share/40f412d2bf414174901caa792a9c98e5?sid=64cf25f4-861f-42ff-bd17-07c2c4d8af4f)

## Deliverables:

Write a query to retrieve all the disitnct entries from column course-id from the enrollments table.

## Expected Output Example:

Given the enrollments table:

### Input:

Enrollments

    student_id|student_name|course_id|enrollment_date

    1|Ryan|2|2024-01-10

    2|Joanna|2|2024-02-12

    3|David|1|2024-03-15

### Output:

    course_id

    2

    1


# Query

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

select distinct course_id from enrollments;
```