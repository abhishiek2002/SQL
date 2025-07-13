# INNER JOIN in SQL - Detailed Explanation

## Overview

The `INNER JOIN` in SQL is used to retrieve rows that have **matching values in both tables**. It is the most common type of join used when querying data across related tables.

> It returns only those records where there is a match in both joined tables.

---

## Syntax

```sql
SELECT table1.column1, table2.column2, ...
FROM table1
INNER JOIN table2
ON table1.common_column = table2.common_column;
```

---

## Example Tables

### Customers Table:

| CustomerID | CustomerName  | Email                                                     |
| ---------- | ------------- | --------------------------------------------------------- |
| 1          | Alice Johnson | [alice.johnson@gmail.com](mailto:alice.johnson@gmail.com) |
| 2          | Bob Smith     | [bob.smith@gmail.com](mailto:bob.smith@gmail.com)         |

### Orders Table:

| OrderID | CustomerID | OrderDate  | TotalAmount |
| ------- | ---------- | ---------- | ----------- |
| 1       | 1          | 2024-10-05 | 2200        |
| 2       | 2          | 2024-10-06 | 4500        |
| 3       | 1          | 2024-10-07 | 1500        |

---

## INNER JOIN Example Query

```sql
SELECT Orders.OrderID, Customers.CustomerName, Orders.TotalAmount
FROM Orders
INNER JOIN Customers
ON Orders.CustomerID = Customers.CustomerID;
```

### Output:

| OrderID | CustomerName  | TotalAmount |
| ------- | ------------- | ----------- |
| 1       | Alice Johnson | 2200        |
| 2       | Bob Smith     | 4500        |
| 3       | Alice Johnson | 1500        |

---

## Key Points

* Only rows with **matching values** in the join condition are returned.
* Rows with **no match in either table** are excluded from the result.
* Can join multiple tables by chaining multiple `INNER JOIN` clauses.

---

## Multiple INNER JOINs Example

```sql
SELECT O.OrderID, C.CustomerName, P.ProductName
FROM Orders O
INNER JOIN Customers C ON O.CustomerID = C.CustomerID
INNER JOIN Products P ON O.ProductID = P.ProductID;
```

This joins three tables using common columns.

---

## INNER JOIN with WHERE Clause

You can add filters to the result using `WHERE`:

```sql
SELECT Orders.OrderID, Customers.CustomerName, Orders.TotalAmount
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID
WHERE Orders.TotalAmount > 2000;
```

---

## INNER JOIN vs LEFT JOIN

| Feature       | INNER JOIN                     | LEFT JOIN                          |
| ------------- | ------------------------------ | ---------------------------------- |
| Matching Rows | Only rows with a match in both | All rows from the left table       |
| Missing Rows  | Excludes unmatched rows        | Includes unmatched rows with NULLs |

---

## Conclusion

The `INNER JOIN` is essential for querying data that exists in **both** joined tables. It ensures accuracy and integrity by returning only rows where relationships are established based on a common field.
