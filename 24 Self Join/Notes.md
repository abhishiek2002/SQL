# SELF JOIN in SQL - Detailed Explanation with Examples

## Overview

A `SELF JOIN` is a regular join where a table is joined **with itself**. It is used to compare rows within the same table by using **table aliases** to differentiate between the two instances.

> ✅ It’s useful for comparing rows, finding relationships like managers, hierarchy, sibling items, etc.

---

## Syntax

```sql
SELECT A.column1, B.column2
FROM Table A
JOIN Table B ON A.common_column = B.common_column;
```

Note: Here, both `A` and `B` refer to the **same table** but are treated as different aliases.

---

## Example 1: Employees and Their Managers

### Table: Employees

| EmpID | Name  | ManagerID |
| ----- | ----- | --------- |
| 1     | Raj   | NULL      |
| 2     | Seema | 1         |
| 3     | Amit  | 1         |
| 4     | Neha  | 2         |

### Query:

```sql
SELECT E1.Name AS Employee, E2.Name AS Manager
FROM Employees E1
LEFT JOIN Employees E2 ON E1.ManagerID = E2.EmpID;
```

### Output:

| Employee | Manager |
| -------- | ------- |
| Raj      | NULL    |
| Seema    | Raj     |
| Amit     | Raj     |
| Neha     | Seema   |

**Explanation**: The table joins to itself to match each employee to their manager.

---

## Example 2: Finding Pairs of Employees in Same Department

### Table: Employees

| EmpID | Name  | DeptID |
| ----- | ----- | ------ |
| 1     | Raj   | 10     |
| 2     | Seema | 20     |
| 3     | Amit  | 10     |
| 4     | Neha  | 20     |

### Query:

```sql
SELECT A.Name AS Emp1, B.Name AS Emp2, A.DeptID
FROM Employees A
JOIN Employees B ON A.DeptID = B.DeptID AND A.EmpID < B.EmpID;
```

### Output:

| Emp1  | Emp2 | DeptID |
| ----- | ---- | ------ |
| Raj   | Amit | 10     |
| Seema | Neha | 20     |

**Explanation**: This finds all **unique pairs** of employees working in the same department.

---

## Example 3: Comparing Product Prices with Other Products

### Table: Products

| ProductID | ProductName | Price |
| --------- | ----------- | ----- |
| 1         | Monitor     | 200   |
| 2         | Keyboard    | 50    |
| 3         | Mouse       | 30    |

### Query:

```sql
SELECT A.ProductName AS Product1, B.ProductName AS Product2
FROM Products A
JOIN Products B ON A.Price > B.Price;
```

### Output:

| Product1 | Product2 |
| -------- | -------- |
| Monitor  | Keyboard |
| Monitor  | Mouse    |
| Keyboard | Mouse    |

**Explanation**: This compares every product’s price with others and shows which ones are more expensive.

---

## Conclusion

`SELF JOIN` is powerful for analyzing data **within the same table**, such as finding hierarchical relationships, comparing rows, or detecting patterns. Using aliases is essential to distinguish between instances of the table during the join.
