## Create a New Courses Table

    Imagine you're designing a database for a university that wants to keep track of its courses. Your task is to help them set up the foundational structure for this important information.

## Deliverables:

### Objective:

     Write a SQL query to create a new table called Courses that will store essential details about each course offered by the university.

### Table Requirements:

The Courses table should include the following columns:

    course_id: An integer that uniquely identifies each course.
    course_name: A variable character field to store the name of the course.
    credits: An integer that represents the number of credits awarded for the course.

### Expected Table Structure:

    Column Name |Data Type

    course_id|INT

    course_name|VARCHAR(100)

    credits|INT

Now, write the SQL query to create the Courses table.

```sql
create table Courses(
    course_id int unique,
    course_name varchar(100),
    credits int
);
```
