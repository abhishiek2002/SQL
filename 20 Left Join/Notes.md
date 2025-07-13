# LEFT JOIN in SQL - Detailed Explanation with Examples

## Overview

The `LEFT JOIN` (or `LEFT OUTER JOIN`) returns **all rows from the left table** and the **matched rows from the right table**. If there is no match, the result is `NULL` on the side of the right table.

---

## Syntax

```sql
SELECT A.column1, B.column2
FROM TableA A
LEFT JOIN TableB B
ON A.common_column = B.common_column;
```

---

## Example 1: Customers and Orders

### Tables:

**Customers**

| CustomerID | CustomerName |
| ---------- | ------------ |
| 1          | Alice        |
| 2          | Bob          |
| 3          | Charlie      |

**Orders**

| OrderID | CustomerID | TotalAmount |
| ------- | ---------- | ----------- |
| 101     | 1          | 500         |
| 102     | 2          | 300         |

### Query:

```sql
SELECT Customers.CustomerName, Orders.OrderID, Orders.TotalAmount
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```

### Output:

| CustomerName | OrderID | TotalAmount |
| ------------ | ------- | ----------- |
| Alice        | 101     | 500         |
| Bob          | 102     | 300         |
| Charlie      | NULL    | NULL        |

**Explanation**: Charlie has no order, so OrderID and TotalAmount are NULL.

---

## Example 2: Employees and Departments

### Tables:

**Employees**

| EmpID | Name  | DeptID |
| ----- | ----- | ------ |
| 1     | Raj   | 10     |
| 2     | Seema | 20     |
| 3     | Amit  | NULL   |

**Departments**

| DeptID | DeptName |
| ------ | -------- |
| 10     | HR       |
| 20     | IT       |

### Query:

```sql
SELECT Employees.Name, Departments.DeptName
FROM Employees
LEFT JOIN Departments ON Employees.DeptID = Departments.DeptID;
```

### Output:

| Name  | DeptName |
| ----- | -------- |
| Raj   | HR       |
| Seema | IT       |
| Amit  | NULL     |

**Explanation**: Amit does not belong to any department, hence NULL in DeptName.

---

## Example 3: Products and Suppliers

### Tables:

**Products**

| ProductID | ProductName | SupplierID |
| --------- | ----------- | ---------- |
| 1         | Monitor     | 201        |
| 2         | Keyboard    | NULL       |
| 3         | Mouse       | 202        |

**Suppliers**

| SupplierID | SupplierName    |
| ---------- | --------------- |
| 201        | ABC Electronics |
| 202        | XYZ Traders     |

### Query:

```sql
SELECT Products.ProductName, Suppliers.SupplierName
FROM Products
LEFT JOIN Suppliers ON Products.SupplierID = Suppliers.SupplierID;
```

### Output:

| ProductName | SupplierName    |
| ----------- | --------------- |
| Monitor     | ABC Electronics |
| Keyboard    | NULL            |
| Mouse       | XYZ Traders     |

**Explanation**: Keyboard has no supplier, so SupplierName is NULL.

---

## Conclusion

`LEFT JOIN` is ideal when you want to **keep all records from the left table** regardless of whether a match exists in the right table. It's commonly used to identify unmatched records or include optional data when joining tables.
