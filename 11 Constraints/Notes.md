# Constraints in SQL - Detailed Explanation

## Overview

Constraints in SQL are **rules** applied to columns in a table to **enforce data integrity and accuracy**. They ensure that only valid data is entered into the database. Constraints can be applied either at the **column level** or **table level**.

---

## Types of Constraints

### 1. NOT NULL Constraint

Ensures that a column cannot have a NULL value.

#### Syntax:

```sql
column_name datatype NOT NULL
```

#### Example:

```sql
CREATE TABLE Students (
  StudentID INT NOT NULL,
  Name VARCHAR(100) NOT NULL
);
```

---

### 2. UNIQUE Constraint

Ensures that all values in a column are unique.

#### Syntax:

```sql
column_name datatype UNIQUE
```

#### Example:

```sql
CREATE TABLE Students (
  Email VARCHAR(100) UNIQUE
);
```

---

### 3. PRIMARY KEY Constraint

Uniquely identifies each record in a table. It is a combination of `NOT NULL` and `UNIQUE`.

#### Syntax:

```sql
PRIMARY KEY (column1, column2, ...)
```

#### Example:

```sql
CREATE TABLE Students (
  StudentID INT PRIMARY KEY,
  Name VARCHAR(100)
);
```

---

### 4. FOREIGN KEY Constraint

Ensures the value in a column matches the primary key of another table, maintaining **referential integrity**.

#### Syntax:

```sql
FOREIGN KEY (column_name) REFERENCES parent_table (column_name)
```

#### Example:

```sql
CREATE TABLE Enrollments (
  StudentID INT,
  FOREIGN KEY (StudentID) REFERENCES Students(StudentID)
);
```

---

### 5. CHECK Constraint

Ensures that all values in a column satisfy a specific condition.

#### Syntax:

```sql
CHECK (condition)
```

#### Example:

```sql
CREATE TABLE Students (
  Age INT CHECK (Age >= 5)
);
```

Only allows students aged 5 or older.

---

### 6. DEFAULT Constraint

Provides a default value for a column when no value is specified.

#### Syntax:

```sql
column_name datatype DEFAULT default_value
```

#### Example:

```sql
CREATE TABLE Students (
  Grade CHAR(1) DEFAULT 'C'
);
```

If no grade is provided, 'C' is used.

---

## Adding Constraints After Table Creation

You can use `ALTER TABLE` to add constraints after the table is created.

### Example:

```sql
ALTER TABLE Students
ADD CONSTRAINT pk_student PRIMARY KEY (StudentID);
```

---

## Summary Table

| Constraint Type | Description                                  |
| --------------- | -------------------------------------------- |
| NOT NULL        | Column must have a value                     |
| UNIQUE          | All values must be different                 |
| PRIMARY KEY     | Uniquely identifies a record                 |
| FOREIGN KEY     | Ensures data matches in another table        |
| CHECK           | Restricts values based on a condition        |
| DEFAULT         | Provides a default value if none is provided |

---

## Conclusion

Constraints are crucial for **maintaining data quality, integrity, and consistency** in a database. By using constraints effectively, database designers can ensure that the data follows the required rules and logic of the application.
