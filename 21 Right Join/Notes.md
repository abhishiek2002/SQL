# RIGHT JOIN in SQL - Detailed Explanation with Examples

## Overview

The `RIGHT JOIN` (or `RIGHT OUTER JOIN`) returns **all rows from the right table** and the **matched rows from the left table**. If there is no match, the result is `NULL` on the side of the left table.

---

## Syntax

```sql
SELECT A.column1, B.column2
FROM TableA A
RIGHT JOIN TableB B
ON A.common_column = B.common_column;
```

> Note: Some databases like MySQL support `RIGHT JOIN`, while in others (like SQLite), you can simulate it using `LEFT JOIN` by switching table positions.

---

## Example 1: Orders and Customers

### Tables:

**Orders**

| OrderID | CustomerID | TotalAmount |
| ------- | ---------- | ----------- |
| 101     | 1          | 500         |
| 102     | 2          | 300         |

**Customers**

| CustomerID | CustomerName |
| ---------- | ------------ |
| 1          | Alice        |
| 2          | Bob          |
| 3          | Charlie      |

### Query:

```sql
SELECT Orders.OrderID, Customers.CustomerName, Orders.TotalAmount
FROM Orders
RIGHT JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```

### Output:

| OrderID | CustomerName | TotalAmount |
| ------- | ------------ | ----------- |
| 101     | Alice        | 500         |
| 102     | Bob          | 300         |
| NULL    | Charlie      | NULL        |

**Explanation**: Charlie has no order, so OrderID and TotalAmount are NULL.

---

## Example 2: Departments and Employees

### Tables:

**Employees**

| EmpID | Name  | DeptID |
| ----- | ----- | ------ |
| 1     | Raj   | 10     |
| 2     | Seema | 20     |

**Departments**

| DeptID | DeptName |
| ------ | -------- |
| 10     | HR       |
| 20     | IT       |
| 30     | Finance  |

### Query:

```sql
SELECT Employees.Name, Departments.DeptName
FROM Employees
RIGHT JOIN Departments ON Employees.DeptID = Departments.DeptID;
```

### Output:

| Name  | DeptName |
| ----- | -------- |
| Raj   | HR       |
| Seema | IT       |
| NULL  | Finance  |

**Explanation**: Finance department has no employees, so Name is NULL.

---

## Example 3: Products and Categories

### Tables:

**Products**

| ProductID | ProductName | CategoryID |
| --------- | ----------- | ---------- |
| 1         | Monitor     | 100        |
| 2         | Mouse       | 200        |

**Categories**

| CategoryID | CategoryName |
| ---------- | ------------ |
| 100        | Electronics  |
| 200        | Accessories  |
| 300        | Furniture    |

### Query:

```sql
SELECT Products.ProductName, Categories.CategoryName
FROM Products
RIGHT JOIN Categories ON Products.CategoryID = Categories.CategoryID;
```

### Output:

| ProductName | CategoryName |
| ----------- | ------------ |
| Monitor     | Electronics  |
| Mouse       | Accessories  |
| NULL        | Furniture    |

**Explanation**: There is no product in the 'Furniture' category, so ProductName is NULL.

---

## Conclusion

The `RIGHT JOIN` is used when you want to **keep all records from the right table**, even if there are no matching records in the left table. It's particularly useful in reporting scenarios to ensure all categories, departments, or entities appear in the result—even those without associated data.
