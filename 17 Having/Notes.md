# HAVING Clause in SQL - Detailed Explanation

## Overview

The `HAVING` clause in SQL is used to **filter groups of rows** based on conditions applied to **aggregate functions**. It is typically used in combination with `GROUP BY` to restrict the results returned by grouped queries.

---

## 1. Basic Syntax

```sql
SELECT column1, AGGREGATE_FUNCTION(column2)
FROM table_name
GROUP BY column1
HAVING condition;
```

---

## 2. Purpose of HAVING

- `WHERE` filters **rows** before grouping.
- `HAVING` filters **groups** after aggregation.

---

## 3. Example 1: Count Employees per Department

```sql
SELECT department, COUNT(*) AS emp_count
FROM Employees
GROUP BY department
HAVING COUNT(*) > 2;
```

Returns departments with more than 2 employees.

---

## 4. Example 2: Average Salary Filter

```sql
SELECT department, AVG(salary) AS avg_salary
FROM Employees
GROUP BY department
HAVING AVG(salary) >= 60000;
```

Returns departments with an average salary of at least 60000.

---

## 5. Combining WHERE and HAVING

You can use both `WHERE` and `HAVING` in a single query:

```sql
SELECT department, COUNT(*) AS emp_count
FROM Employees
WHERE salary > 50000
GROUP BY department
HAVING COUNT(*) > 2;
```

- `WHERE` filters individual employees with salary > 50000
- `HAVING` filters departments with more than 2 such employees

---

## 6. Aliases in HAVING

You can use column aliases in the `HAVING` clause:

```sql
SELECT department, COUNT(*) AS emp_count
FROM Employees
GROUP BY department
HAVING emp_count > 3;
```

> Note: Not all databases support using aliases in `HAVING`, so test it in your RDBMS.

---

## 7. Difference Between WHERE and HAVING

| Feature       | WHERE                          | HAVING                      |
| ------------- | ------------------------------ | --------------------------- |
| Works on      | Individual rows                | Groups of rows              |
| Used with     | SELECT, UPDATE, DELETE         | SELECT with GROUP BY        |
| Aggregate Use | Cannot use aggregate functions | Can use aggregate functions |

---

## Summary Table

| Clause   | Purpose                          |
| -------- | -------------------------------- |
| `WHERE`  | Filters rows before grouping     |
| `HAVING` | Filters groups after aggregation |

---

## Conclusion

The `HAVING` clause is essential when working with grouped data and aggregate functions. It allows for refined filtering of result sets after aggregation, making it powerful for analytical queries and reports.
