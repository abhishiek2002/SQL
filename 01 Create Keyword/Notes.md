# CREATE Keyword in SQL - Detailed Explanation

## Overview

The `CREATE` keyword in SQL is a **Data Definition Language (DDL)** command used to **create new database objects** such as:

* Databases
* Tables
* Views
* Indexes
* Procedures
* Triggers

It helps in defining the structure/schema of the database.

---

## 1. CREATE DATABASE

This command is used to create a new database.

### Syntax:

```sql
CREATE DATABASE database_name;
```

### Example:

```sql
CREATE DATABASE SchoolDB;
```

This creates a new database named `SchoolDB`.

---

## 2. CREATE TABLE

This command is used to create a new table in a database.

### Syntax:

```sql
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    ...
);
```

### Example:

```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(100),
    Age INT,
    Grade CHAR(1)
);
```

This creates a `Students` table with 4 columns and a primary key on `StudentID`.

---

## 3. CREATE VIEW

This command creates a **virtual table** based on the result-set of a SQL query.

### Syntax:

```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### Example:

```sql
CREATE VIEW HighScorers AS
SELECT Name, Grade
FROM Students
WHERE Grade = 'A';
```

This creates a view `HighScorers` showing students with grade A.

---

## 4. CREATE INDEX

Used to create indexes to speed up retrieval of rows.

### Syntax:

```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...);
```

### Example:

```sql
CREATE INDEX idx_name
ON Students (Name);
```

This creates an index `idx_name` on the `Name` column in `Students` table.

---

## 5. CREATE PROCEDURE

Used to create stored procedures (reusable SQL blocks).

### Syntax (SQL Server example):

```sql
CREATE PROCEDURE procedure_name
AS
BEGIN
    -- SQL statements
END;
```

---

## 6. CREATE TRIGGER

Used to create triggers that automatically execute when an event occurs in the database (like insert/update/delete).

### Syntax (MySQL example):

```sql
CREATE TRIGGER trigger_name
AFTER INSERT ON table_name
FOR EACH ROW
BEGIN
    -- SQL statements
END;
```

---

## Notes:

* The `CREATE` command is usually used by database administrators or developers.
* Appropriate permissions are needed to execute `CREATE` commands.
* Created objects can later be modified using `ALTER` or deleted using `DROP`.

---

## Summary

| Command          | Purpose                          |
| ---------------- | -------------------------------- |
| CREATE DATABASE  | Creates a new database           |
| CREATE TABLE     | Creates a new table              |
| CREATE VIEW      | Creates a virtual table (view)   |
| CREATE INDEX     | Creates an index for fast search |
| CREATE PROCEDURE | Creates a stored procedure       |
| CREATE TRIGGER   | Creates a trigger                |

The `CREATE` keyword is essential for defining the structure and components of a relational database system.
