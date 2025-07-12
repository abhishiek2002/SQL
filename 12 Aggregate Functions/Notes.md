# Aggregate Functions in SQL - Detailed Explanation

## Overview

Aggregate functions in SQL perform **calculations on a set of values** and return a single value. They are often used with the `GROUP BY` clause to group result sets and are essential in data analysis and reporting.

---

## List of Common Aggregate Functions

### 1. COUNT()

Returns the **number of rows** that match a specified condition.

#### Syntax:

```sql
SELECT COUNT(column_name) FROM table_name;
```

#### Example:

```sql
SELECT COUNT(*) FROM Students;
```

Counts all rows in the `Students` table.

---

### 2. SUM()

Returns the **total sum** of a numeric column.

#### Syntax:

```sql
SELECT SUM(column_name) FROM table_name;
```

#### Example:

```sql
SELECT SUM(Marks) FROM Students;
```

Calculates the total marks of all students.

---

### 3. AVG()

Returns the **average value** of a numeric column.

#### Syntax:

```sql
SELECT AVG(column_name) FROM table_name;
```

#### Example:

```sql
SELECT AVG(Marks) FROM Students;
```

Finds the average marks of students.

---

### 4. MIN()

Returns the **minimum value** in a column.

#### Syntax:

```sql
SELECT MIN(column_name) FROM table_name;
```

#### Example:

```sql
SELECT MIN(Age) FROM Students;
```

Finds the youngest student.

---

### 5. MAX()

Returns the **maximum value** in a column.

#### Syntax:

```sql
SELECT MAX(column_name) FROM table_name;
```

#### Example:

```sql
SELECT MAX(Age) FROM Students;
```

Finds the oldest student.

---

## Using Aggregate Functions with GROUP BY

Aggregate functions are often used with the `GROUP BY` clause to group records based on one or more columns.

### Example:

```sql
SELECT Grade, COUNT(*)
FROM Students
GROUP BY Grade;
```

This counts the number of students in each grade.

---

## Using Aggregate Functions with WHERE and HAVING

- Use `WHERE` to filter rows **before** aggregation.
- Use `HAVING` to filter **after** aggregation.

### Example:

```sql
SELECT Grade, AVG(Marks)
FROM Students
GROUP BY Grade
HAVING AVG(Marks) > 75;
```

This shows grades with average marks greater than 75.

---

## Notes:

- Aggregate functions ignore `NULL` values except `COUNT(*)`.
- You can alias result columns using `AS` for readability.

### Example:

```sql
SELECT AVG(Marks) AS Average_Marks
FROM Students;
```

---

## Summary Table

| Function | Description            |
| -------- | ---------------------- |
| COUNT()  | Counts number of rows  |
| SUM()    | Calculates total sum   |
| AVG()    | Computes average value |
| MIN()    | Finds minimum value    |
| MAX()    | Finds maximum value    |

---

## Conclusion

Aggregate functions are vital in SQL for summarizing and analyzing data. When combined with clauses like `GROUP BY`, `HAVING`, and `WHERE`, they become powerful tools for generating meaningful insights from your database.
