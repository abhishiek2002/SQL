# BETWEEN Operator in SQL - Detailed Explanation

## Overview

The `BETWEEN` operator in SQL is used in the `WHERE` clause to filter the result set within a **range of values**. It checks whether a column's value lies **between two specified values**, including the boundary values.

---

## 1. Basic BETWEEN Syntax

### Syntax:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

### Example:

```sql
SELECT *
FROM Employees
WHERE salary BETWEEN 50000 AND 60000;
```

This returns employees with salary **from 50000 to 60000**, including both values.

---

## 2. BETWEEN with Numeric Values

You can use `BETWEEN` with numeric data to filter number ranges.

### Example:

```sql
SELECT name
FROM Employees
WHERE employee_id BETWEEN 2 AND 4;
```

Returns employees with IDs 2, 3, and 4.

---

## 3. BETWEEN with Date Values

`BETWEEN` is often used with dates to filter records in a specific date range.

### Example:

```sql
SELECT *
FROM Orders
WHERE order_date BETWEEN '2025-01-01' AND '2025-07-01';
```

Returns all orders placed between January 1, 2025 and July 1, 2025.

---

## 4. BETWEEN with Text (Strings)

`BETWEEN` can also be used with string values, where comparison is based on **lexicographic (alphabetical)** order.

### Example:

```sql
SELECT *
FROM Products
WHERE product_name BETWEEN 'A' AND 'M';
```

Returns products whose names start with letters from 'A' to 'M'.

> 🔸 Note: String comparisons depend on collation settings and are case-insensitive by default in many systems.

---

## 5. NOT BETWEEN

To exclude values within a range, use `NOT BETWEEN`.

### Example:

```sql
SELECT *
FROM Employees
WHERE salary NOT BETWEEN 50000 AND 60000;
```

Returns employees whose salary is **less than 50000 or more than 60000**.

---

## Key Points

- `BETWEEN` is inclusive: `value1` and `value2` are included.
- Use `NOT BETWEEN` to **exclude** a range.
- Works with **numbers, dates, and strings**.

---

## Summary Table

| Usage             | Description                                   |
| ----------------- | --------------------------------------------- |
| `BETWEEN A AND B` | Checks if value is within the inclusive range |
| `NOT BETWEEN`     | Checks if value is outside the range          |
| Works with        | Numbers, dates, strings                       |

---

## Conclusion

The `BETWEEN` operator is a concise and effective way to filter data within a specified range. It's especially useful for numeric, date, and text-based filtering, making SQL queries cleaner and more readable.
