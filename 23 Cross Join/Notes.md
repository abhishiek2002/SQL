# CROSS JOIN in SQL - Detailed Explanation with Examples

## Overview

A `CROSS JOIN` returns the **Cartesian product** of two tables. That means it combines each row of the first table with **every row** of the second table.

> ⚠️ Use with caution: If Table A has `m` rows and Table B has `n` rows, the result will have `m × n` rows.

---

## Syntax

```sql
SELECT A.column1, B.column2
FROM TableA A
CROSS JOIN TableB B;
```

You can also write it without the `CROSS JOIN` keyword:

```sql
SELECT A.column1, B.column2
FROM TableA A, TableB B;
```

---

## Example 1: T-Shirts and Sizes

### Tables:

**Tshirts**

| TShirtID | Color |
| -------- | ----- |
| 1        | Red   |
| 2        | Blue  |

**Sizes**

| SizeID | SizeLabel |
| ------ | --------- |
| 1      | S         |
| 2      | M         |
| 3      | L         |

### Query:

```sql
SELECT Tshirts.Color, Sizes.SizeLabel
FROM Tshirts
CROSS JOIN Sizes;
```

### Output:

| Color | SizeLabel |
| ----- | --------- |
| Red   | S         |
| Red   | M         |
| Red   | L         |
| Blue  | S         |
| Blue  | M         |
| Blue  | L         |

**Explanation**: Every T-shirt color is combined with every available size.

---

## Example 2: Employees and Shifts

### Tables:

**Employees**

| EmpID | Name  |
| ----- | ----- |
| 1     | Ravi  |
| 2     | Priya |

**Shifts**

| ShiftID | ShiftTime |
| ------- | --------- |
| 1       | Morning   |
| 2       | Evening   |
| 3       | Night     |

### Query:

```sql
SELECT Employees.Name, Shifts.ShiftTime
FROM Employees
CROSS JOIN Shifts;
```

### Output:

| Name  | ShiftTime |
| ----- | --------- |
| Ravi  | Morning   |
| Ravi  | Evening   |
| Ravi  | Night     |
| Priya | Morning   |
| Priya | Evening   |
| Priya | Night     |

**Explanation**: Every employee is assigned to every possible shift.

---

## Example 3: Locations and Months

### Tables:

**Locations**

| LocID | City   |
| ----- | ------ |
| 1     | Delhi  |
| 2     | Mumbai |

**Months**

| MonthID | MonthName |
| ------- | --------- |
| 1       | January   |
| 2       | February  |

### Query:

```sql
SELECT Locations.City, Months.MonthName
FROM Locations
CROSS JOIN Months;
```

### Output:

| City   | MonthName |
| ------ | --------- |
| Delhi  | January   |
| Delhi  | February  |
| Mumbai | January   |
| Mumbai | February  |

**Explanation**: Each city is combined with each month for planning purposes.

---

## Use Cases

- Generating **combinations** of items (e.g., sizes, colors, time slots)
- Building **testing datasets**
- Creating **combinations for permutations** in logic problems

---

## Conclusion

`CROSS JOIN` is useful when you want **all possible combinations** between two tables. It's powerful, but be cautious with large tables as the result size grows rapidly with the number of rows.
