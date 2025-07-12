# SELECT Keyword in SQL - Detailed Explanation

## Overview

The `SELECT` keyword in SQL is a **Data Query Language (DQL)** command used to **retrieve data** from one or more tables in a database. It is the most commonly used SQL command.

---

## 1. Basic SELECT Statement

### Syntax:

```sql
SELECT column1, column2, ...
FROM table_name;
```

### Example:

```sql
SELECT Name, Age
FROM Students;
```

This query retrieves the `Name` and `Age` columns from the `Students` table.

---

## 2. SELECT All Columns

### Syntax:

```sql
SELECT *
FROM table_name;
```

### Example:

```sql
SELECT *
FROM Students;
```

This retrieves **all columns** from the `Students` table.

---

## 3. SELECT with WHERE Clause

Used to filter rows based on a condition.

### Syntax:

```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```

### Example:

```sql
SELECT Name
FROM Students
WHERE Grade = 'A';
```

This returns names of students whose grade is 'A'.

---

## 4. SELECT with ORDER BY Clause

Used to sort the result set. If order by clause is using on multiple col then most priority will given to left column first.

### Syntax:

```sql
SELECT column1, column2
FROM table_name
ORDER BY column1, column2 ... [ASC|DESC];
```

### Example:

```sql
SELECT Name, Age
FROM Students
ORDER BY Age DESC;
```

This sorts the result by age in descending order.

---

## 5. SELECT with DISTINCT Keyword

Used to return only unique (distinct) values.

### Syntax:

```sql
SELECT DISTINCT column_name
FROM table_name;
```

### Example:

```sql
SELECT DISTINCT Grade
FROM Students;
```

This returns unique grades from the table.

---

## 6. SELECT with LIMIT / TOP / FETCH

Used to limit the number of rows returned (varies by SQL dialect).

### MySQL / PostgreSQL:

```sql
SELECT *
FROM Students
LIMIT 5;
```

### SQL Server:

```sql
SELECT TOP 5 *
FROM Students;
```

---

## 7. SELECT with Aggregation Functions

Used to perform calculations on data.

### Common Functions:

* `COUNT()`
* `SUM()`
* `AVG()`
* `MIN()`
* `MAX()`

### Example:

```sql
SELECT COUNT(*)
FROM Students;
```

Returns the total number of students.

---

## 8. SELECT with GROUP BY

Used to group rows with the same values and perform aggregation.

### Syntax:

```sql
SELECT column, AGG_FUNCTION(column)
FROM table
GROUP BY column;
```

### Example:

```sql
SELECT Grade, COUNT(*)
FROM Students
GROUP BY Grade;
```

Returns number of students in each grade.

---

## 9. SELECT with JOIN

Used to retrieve data from multiple related tables.

### Example:

```sql
SELECT Students.Name, Courses.CourseName
FROM Students
JOIN Enrollments ON Students.StudentID = Enrollments.StudentID
JOIN Courses ON Enrollments.CourseID = Courses.CourseID;
```

Combines data from 3 tables based on related columns.

---

## Summary Table

| Clause    | Purpose                           |
| --------- | --------------------------------- |
| SELECT    | Specify columns to retrieve       |
| FROM      | Define the source table(s)        |
| WHERE     | Filter records                    |
| ORDER BY  | Sort the result                   |
| DISTINCT  | Remove duplicates                 |
| LIMIT/TOP | Restrict number of rows returned  |
| GROUP BY  | Group records for aggregation     |
| JOIN      | Combine rows from multiple tables |

---

## Conclusion

The `SELECT` keyword is the backbone of querying in SQL. Mastering its usage allows developers and analysts to effectively retrieve and analyze data from relational databases.
