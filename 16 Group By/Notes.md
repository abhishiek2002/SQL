# GROUP BY in SQL - Detailed Explanation

## Overview

The `GROUP BY` clause in SQL is used to **group rows that have the same values** in specified columns into summary rows. It is typically used with **aggregate functions** such as `COUNT()`, `SUM()`, `AVG()`, `MAX()`, and `MIN()` to perform operations on each group.

---

## 1. Basic Syntax

```sql
SELECT column1, AGGREGATE_FUNCTION(column2)
FROM table_name
GROUP BY column1;
```

### Example:

```sql
SELECT department, COUNT(*)
FROM Employees
GROUP BY department;
```

Returns the number of employees in each department.

---

## 2. Multiple Columns in GROUP BY

You can group by more than one column.

### Example:

```sql
SELECT department, job_title, COUNT(*)
FROM Employees
GROUP BY department, job_title;
```

Groups data by both department and job title.

---

## 3. GROUP BY with WHERE

Use `WHERE` to filter rows **before** grouping.

### Example:

```sql
SELECT department, AVG(salary)
FROM Employees
WHERE salary > 50000
GROUP BY department;
```

Calculates average salary per department **only for employees with salary > 50000**.

---

## 4. GROUP BY with HAVING

Use `HAVING` to filter groups **after** aggregation.

### Example:

```sql
SELECT department, COUNT(*) AS emp_count
FROM Employees
GROUP BY department
HAVING COUNT(*) > 2;
```

Returns only departments with more than 2 employees.

---

## 5. GROUP BY vs ORDER BY

* `GROUP BY` groups rows for aggregation.
* `ORDER BY` sorts the result set.

They can be used together:

```sql
SELECT department, SUM(salary) AS total_salary
FROM Employees
GROUP BY department
ORDER BY total_salary DESC;
```

---

## 6. Invalid Use Without Aggregates

If you're using `GROUP BY`, all selected columns must be either:

* Included in `GROUP BY`, or
* Used in an aggregate function.

### Invalid:

```sql
SELECT department, salary
FROM Employees
GROUP BY department;
```

This throws an error unless `salary` is wrapped in an aggregate like `MAX(salary)`.

---

## Summary Table

| Clause     | Purpose                          |
| ---------- | -------------------------------- |
| `GROUP BY` | Groups rows with the same value  |
| `WHERE`    | Filters rows before grouping     |
| `HAVING`   | Filters groups after aggregation |
| `ORDER BY` | Sorts final output               |

---

## Conclusion

The `GROUP BY` clause is a powerful SQL tool for summarizing large datasets. By combining it with aggregate functions, `WHERE`, and `HAVING` clauses, you can generate meaningful grouped insights for reporting and analytics.
