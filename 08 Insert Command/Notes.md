# INSERT Command in SQL - Detailed Explanation

## Overview

The `INSERT` command in SQL is a **Data Manipulation Language (DML)** command used to **add new rows of data** into a table. It allows you to populate tables with data, either one row at a time or multiple rows at once.

---

## 1. Basic INSERT INTO Statement

This is used to insert data into **all columns** of a table.

### Syntax:

```sql
INSERT INTO table_name
VALUES (value1, value2, ...);
```

### Example:

```sql
INSERT INTO Students
VALUES (1, 'Rahul', 17, 'A');
```

Inserts a new row into the `Students` table.

> Note: The values must match the column order and data types defined in the table.

---

## 2. INSERT INTO Specific Columns

You can insert data into **specific columns** only.

### Syntax:

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

### Example:

```sql
INSERT INTO Students (StudentID, Name)
VALUES (2, 'Priya');
```

Inserts a row with only `StudentID` and `Name`. The other columns will take default or `NULL` values.

---

## 3. INSERT Multiple Rows

Many SQL dialects allow inserting multiple rows in one command.

### Syntax:

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES
  (value1a, value2a, ...),
  (value1b, value2b, ...);
```

### Example:

```sql
INSERT INTO Students (StudentID, Name, Age, Grade)
VALUES
  (3, 'Amit', 18, 'B'),
  (4, 'Sita', 16, 'A');
```

Inserts two rows in one command.

---

## 4. INSERT Data from Another Table

You can insert data by selecting it from another table.

### Syntax:

```sql
INSERT INTO table2 (column1, column2, ...)
SELECT column1, column2, ...
FROM table1
WHERE condition;
```

### Example:

```sql
INSERT INTO Alumni (StudentID, Name)
SELECT StudentID, Name
FROM Students
WHERE Grade = 'A';
```

Copies students with grade 'A' to the `Alumni` table.

---

## 5. INSERT with DEFAULT Values

You can use the `DEFAULT` keyword to insert the default value for a column.

### Example:

```sql
INSERT INTO Students (StudentID, Name, Age, Grade)
VALUES (5, 'Arjun', 17, DEFAULT);
```

Assumes that the default value for `Grade` is already set in the table definition.

---

## Notes

* `INSERT` adds **new rows**, it does not modify existing rows.
* If a required column is **not provided a value**, and no default is set, an error will occur.
* You can use `NULL` explicitly if a column allows null values.

---

## Summary Table

| Form                           | Description                  |
| ------------------------------ | ---------------------------- |
| `INSERT INTO VALUES`           | Insert single row            |
| `INSERT INTO (columns)`        | Insert into specific columns |
| `INSERT INTO ... VALUES (),()` | Insert multiple rows         |
| `INSERT INTO ... SELECT`       | Insert from another table    |
| `INSERT INTO ... DEFAULT`      | Insert using default values  |

---

## Conclusion

The `INSERT` command is essential for adding data into a SQL database. Whether you're adding one record or bulk inserting from another table, mastering `INSERT` ensures efficient data entry and population in relational databases.
