# Watch and Learn: Understanding LIMIT and OFFSET in SQL
Before jumping into the questions, watch the following video to understand how the LIMIT and OFFSET clauses work in SQL:

🎥 Video Link: [Limit and Offset in SQL](https://www.loom.com/share/b3cc86a2af6d40e7be02d3587912915d?sid=0916aa8f-d966-45ca-b19e-8223b7014728)

(Make sure to watch it to understand how to retrieve a specific number of rows and skip rows)

These two clauses are commonly used for pagination, and allow you to fetch a subset of rows from a larger result set.

LIMIT specifies how many rows to return.
OFFSET tells SQL how many rows to skip before starting to return rows.

## ✅ Now, Complete the Questions Below

### 🧩 Question 1: Using LIMIT to Display Top N Records

#### Description:

You are working with a table named students which contains details about students and their marks.

    CREATE TABLE students (
    id INT,
    name VARCHAR(50),
    marks INT
    );

Write a query to fetch the top 3 students based on their marks.

🧠 Tip: Use ORDER BY marks DESC to sort the students and LIMIT to restrict the result.

**Sample Input Data:**

id|name|marks

    1|Alice|85

    2|Bob|92

    3|Charlie|88

    4|David|95

    5|Eve|90

**Expected Output:**

name|marks

    David|95

    Bob|92

    Eve|90

