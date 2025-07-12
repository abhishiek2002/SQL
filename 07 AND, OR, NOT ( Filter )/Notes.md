# AND, OR, NOT in SQL - Detailed Explanation

## Overview

`AND`, `OR`, and `NOT` are **logical operators** in SQL used in the `WHERE` clause to filter records based on multiple conditions. These operators help refine queries and make them more powerful.

---

## 1. AND Operator

The `AND` operator is used to combine **multiple conditions** in a query. All the conditions must be **true** for a row to be included in the result.

### Syntax:

```sql
SELECT column1, column2
FROM table_name
WHERE condition1 AND condition2;
```

### Example:

```sql
SELECT Name
FROM Students
WHERE Grade = 'A' AND Age < 18;
```

This returns names of students who have a grade 'A' **and** are younger than 18.

---

## 2. OR Operator

The `OR` operator is used to combine multiple conditions. If **any one condition** is true, the row will be included in the result.

### Syntax:

```sql
SELECT column1, column2
FROM table_name
WHERE condition1 OR condition2;
```

### Example:

```sql
SELECT Name
FROM Students
WHERE Grade = 'A' OR Age < 18;
```

This returns names of students who either have a grade 'A' **or** are younger than 18.

---

## 3. NOT Operator

The `NOT` operator is used to **negate a condition**. It returns rows for which the condition is **not true**.

### Syntax:

```sql
SELECT column1, column2
FROM table_name
WHERE NOT condition;
```

### Example:

```sql
SELECT Name
FROM Students
WHERE NOT Grade = 'A';
```

This returns names of students whose grade is **not** 'A'.

---

## 4. Combining AND, OR, and NOT

Logical operators can be combined using **parentheses** to control evaluation order.

### Example:

```sql
SELECT Name
FROM Students
WHERE (Grade = 'A' OR Grade = 'B') AND Age < 18;
```

This returns names of students who have a grade of A or B **and** are younger than 18.

---

## Truth Table

| Condition A | Condition B | A AND B | A OR B | NOT A |
| ----------- | ----------- | ------- | ------ | ----- |
| TRUE        | TRUE        | TRUE    | TRUE   | FALSE |
| TRUE        | FALSE       | FALSE   | TRUE   | FALSE |
| FALSE       | TRUE        | FALSE   | TRUE   | TRUE  |
| FALSE       | FALSE       | FALSE   | FALSE  | TRUE  |

---

## Use Cases

* `AND`: When you want **all** conditions to match.
* `OR`: When you want **any** condition to match.
* `NOT`: When you want to **exclude** specific rows.

---

## Conclusion

Logical operators `AND`, `OR`, and `NOT` are essential for building complex filtering conditions in SQL queries. Mastering them helps in writing precise and efficient data retrieval statements.
