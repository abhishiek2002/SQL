# LIKE with Wildcards in SQL - Detailed Explanation

## Overview

The `LIKE` operator in SQL is used in the `WHERE` clause to search for a **specified pattern** in a column. It is commonly used with **wildcard characters** to match flexible string values.

---

## Wildcard Characters

| Wildcard | Description                         |
| -------- | ----------------------------------- |
| `%`      | Matches **zero or more characters** |
| `_`      | Matches **exactly one character**   |

---

## 1. Basic LIKE Syntax

### Syntax:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name LIKE 'pattern';
```

---

## 2. Using `%` Wildcard

### a) Match strings that start with a specific substring:

```sql
SELECT name
FROM Employees
WHERE name LIKE 'A%';
```

Returns names that start with 'A' (e.g., 'Alice').

### b) Match strings that end with a specific substring:

```sql
SELECT name
FROM Employees
WHERE name LIKE '%e';
```

Returns names that end with 'e' (e.g., 'Eve').

### c) Match strings that contain a specific substring:

```sql
SELECT name
FROM Employees
WHERE name LIKE '%li%';
```

Returns names that contain 'li' anywhere (e.g., 'Alice', 'Charlie').

---

## 3. Using `_` Wildcard

Matches a **single character** at a specific position.

### Example:

```sql
SELECT name
FROM Employees
WHERE name LIKE '_ob';
```

Returns names with three letters where the second and third letters are 'ob' (e.g., 'Bob').

---

## 4. Combining `%` and `_`

You can combine both wildcards in one pattern.

### Example:

```sql
SELECT name
FROM Employees
WHERE name LIKE '_a%e';
```

Matches names where:

* Second character is 'a'
* Ends with 'e'
* Any characters in between

---

## 5. NOT LIKE Operator

Used to exclude pattern matches.

### Example:

```sql
SELECT name
FROM Employees
WHERE name NOT LIKE 'A%';
```

Returns names that do **not** start with 'A'.

---

## 6. Case Sensitivity

* In **most SQL dialects**, `LIKE` is **case-insensitive** (e.g., MySQL).
* In some (e.g., PostgreSQL), `LIKE` is case-sensitive unless using `ILIKE` (for case-insensitive match).

---

## 7. Escape Characters

Use `ESCAPE` to match literal `%` or `_` symbols in strings.

### Example:

```sql
SELECT comments
FROM Feedback
WHERE comments LIKE '%100\%%' ESCAPE '\';
```

Matches text that includes the literal '100%'.

---

## Summary Table

| Pattern         | Matches                            |
| --------------- | ---------------------------------- |
| `'A%'`          | Starts with 'A'                    |
| `'%e'`          | Ends with 'e'                      |
| `'%li%'`        | Contains 'li'                      |
| `'A_C'`         | 'A' followed by any char, then 'C' |
| `NOT LIKE 'X%'` | Does not start with 'X'            |

---

## Conclusion

The `LIKE` operator with wildcards is a powerful way to perform flexible string matching in SQL queries. Whether you're filtering by name patterns, email formats, or part numbers, `LIKE` helps retrieve results that match specified textual patterns easily and effectively.
