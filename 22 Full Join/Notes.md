# FULL JOIN in SQL - Detailed Explanation with Examples

## Overview

The `FULL JOIN` (or `FULL OUTER JOIN`) returns **all records from both tables**, matching rows where possible. If there is no match, the result will contain `NULL` for columns of the table without a match.

> Note: Not all databases (like MySQL) support `FULL JOIN` directly. You can emulate it using `UNION` of `LEFT JOIN` and `RIGHT JOIN`.

---

## Syntax

```sql
SELECT A.column1, B.column2
FROM TableA A
FULL OUTER JOIN TableB B
ON A.common_column = B.common_column;
```

---

## Example 1: Employees and Departments

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
| 30     | Finance  |

### Query:

```sql
SELECT Employees.Name, Departments.DeptName
FROM Employees
FULL OUTER JOIN Departments ON Employees.DeptID = Departments.DeptID;
```

### Output:

| Name  | DeptName |
| ----- | -------- |
| Raj   | HR       |
| Seema | NULL     |
| NULL  | Finance  |

**Explanation**:

- Raj is matched with HR
- Seema is unmatched (no department 20)
- Finance is unmatched (no employee assigned)

---

## Example 2: Students and Exam Results

### Tables:

**Students**

| StudentID | StudentName |
| --------- | ----------- |
| 1         | Anu         |
| 2         | Rohan       |
| 3         | Meera       |

**Results**

| StudentID | Marks |
| --------- | ----- |
| 1         | 85    |
| 4         | 90    |

### Query:

```sql
SELECT Students.StudentName, Results.Marks
FROM Students
FULL OUTER JOIN Results ON Students.StudentID = Results.StudentID;
```

### Output:

| StudentName | Marks |
| ----------- | ----- |
| Anu         | 85    |
| Rohan       | NULL  |
| Meera       | NULL  |
| NULL        | 90    |

**Explanation**:

- Anu has a result.
- Rohan and Meera are unmatched in `Results`.
- Student ID 4 has no corresponding student in `Students`.

---

## Example 3: Products and Sales

### Tables:

**Products**

| ProductID | ProductName |
| --------- | ----------- |
| 1         | Laptop      |
| 2         | Keyboard    |
| 3         | Mouse       |

**Sales**

| SaleID | ProductID | Quantity |
| ------ | --------- | -------- |
| 101    | 1         | 2        |
| 102    | 4         | 5        |

### Query:

```sql
SELECT Products.ProductName, Sales.Quantity
FROM Products
FULL OUTER JOIN Sales ON Products.ProductID = Sales.ProductID;
```

### Output:

| ProductName | Quantity |
| ----------- | -------- |
| Laptop      | 2        |
| Keyboard    | NULL     |
| Mouse       | NULL     |
| NULL        | 5        |

**Explanation**:

- Laptop is matched.
- Keyboard and Mouse have no sales.
- ProductID 4 in Sales table doesn't exist in Products.

---

## Simulating FULL JOIN in MySQL

```sql
SELECT A.*, B.*
FROM TableA A
LEFT JOIN TableB B ON A.id = B.id
UNION
SELECT A.*, B.*
FROM TableA A
RIGHT JOIN TableB B ON A.id = B.id;
```

---

## Conclusion

`FULL JOIN` is extremely helpful when you need to retain **all information from both tables**, regardless of matching. It’s useful for identifying unmatched records and combining full datasets.
