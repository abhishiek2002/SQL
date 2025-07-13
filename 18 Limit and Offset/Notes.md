# LIMIT and OFFSET in SQL - Detailed Explanation

## Overview

The `LIMIT` and `OFFSET` clauses in SQL are used to control the **number of rows returned** by a query and to **skip a specified number of rows**. They are especially useful for **pagination** and performance optimization.

> 🔸 Not all RDBMS support these keywords directly. For example, SQL Server uses `TOP` and `OFFSET-FETCH`.

---

## 1. LIMIT Clause

The `LIMIT` clause restricts the number of rows returned by a query.

### Syntax:

```sql
SELECT column1, column2, ...
FROM table_name
LIMIT number;
```

### Example:

```sql
SELECT *
FROM Employees
LIMIT 5;
```

Returns the first 5 rows from the `Employees` table.

---

## 2. OFFSET Clause

The `OFFSET` clause skips a specified number of rows before starting to return rows.

### Syntax:

```sql
SELECT column1, column2, ...
FROM table_name
OFFSET number;
```

### Example:

```sql
SELECT *
FROM Employees
OFFSET 3;
```

Skips the first 3 rows and returns the rest.

> ⚠️ `OFFSET` must be used with `LIMIT` in some SQL dialects.

---

## 3. Combining LIMIT and OFFSET

To implement pagination, `LIMIT` and `OFFSET` are used together.

### Syntax:

```sql
SELECT column1, column2, ...
FROM table_name
LIMIT limit_number OFFSET offset_number;
```

### Example:

```sql
SELECT *
FROM Employees
LIMIT 5 OFFSET 10;
```

Fetches 5 rows starting from the 11th row (zero-indexed).

---

## 4. ORDER BY with LIMIT/OFFSET

To get consistent and predictable results, use `ORDER BY` with `LIMIT` and `OFFSET`.

### Example:

```sql
SELECT *
FROM Employees
ORDER BY employee_id
LIMIT 5 OFFSET 10;
```

Ensures that the same set of records is returned each time.

---

## 5. Pagination Example

To implement a paginated view:

* Page 1: `LIMIT 10 OFFSET 0`
* Page 2: `LIMIT 10 OFFSET 10`
* Page 3: `LIMIT 10 OFFSET 20`

---

## Notes

* `LIMIT` is supported in MySQL, PostgreSQL, SQLite.
* SQL Server uses:

```sql
SELECT column1
FROM table
ORDER BY column2
OFFSET 10 ROWS FETCH NEXT 5 ROWS ONLY;
```

---

## Summary Table

| Clause             | Purpose                        |
| ------------------ | ------------------------------ |
| `LIMIT N`          | Return only N rows             |
| `OFFSET M`         | Skip the first M rows          |
| `LIMIT N OFFSET M` | Return N rows after skipping M |

---

## Conclusion

`LIMIT` and `OFFSET` are essential tools for slicing result sets, especially in pagination and performance tuning. They make queries more efficient and results more manageable, especially when dealing with large datasets.
