# Normalization in SQL - Detailed Explanation with Examples

## Overview

**Normalization** is the process of organizing data in a database to reduce **data redundancy** and improve **data integrity**. It divides large, complex tables into smaller, more manageable pieces without losing data relationships.

---

## Objectives of Normalization

- Eliminate redundant (repetitive) data
- Ensure logical data storage
- Enhance data consistency
- Improve query efficiency

---

## Types of Normal Forms

### 1. First Normal Form (1NF)

- Ensures that each column contains **atomic values** (no multiple values in a single field)
- Each record is unique

### 2. Second Normal Form (2NF)

- Must be in 1NF
- No **partial dependency** (non-key attributes depend on entire primary key)

### 3. Third Normal Form (3NF)

- Must be in 2NF
- No **transitive dependency** (non-key attributes must depend only on the primary key)

### 4. Boyce-Codd Normal Form (BCNF)

- A stricter version of 3NF
- Every determinant must be a candidate key
- Used when a table is in 3NF but still has anomalies due to **non-candidate keys** determining other attributes

### 5. Fourth Normal Form (4NF)

- Must be in BCNF
- No **multi-valued dependencies**

### 6. Fifth Normal Form (5NF)

- Must be in 4NF
- Deals with **join dependency** and lossless decomposition

---

## Example 1: Convert Unnormalized Table to 1NF

### Unnormalized Table

| StudentID | Name  | Courses          |
| --------- | ----- | ---------------- |
| 1         | Raj   | Math, Science    |
| 2         | Seema | English, History |

### Problem: Courses column has multiple values.

### 1NF Table

| StudentID | Name  | Course  |
| --------- | ----- | ------- |
| 1         | Raj   | Math    |
| 1         | Raj   | Science |
| 2         | Seema | English |
| 2         | Seema | History |

---

## Example 2: Convert to 2NF

### 1NF Table

| StudentID | CourseID | CourseName | Instructor |
| --------- | -------- | ---------- | ---------- |
| 1         | C1       | Math       | Mr. Kumar  |
| 1         | C2       | Science    | Ms. Neeta  |

**Issue**: Instructor depends on CourseID, not StudentID → Partial dependency

### 2NF - Two Tables

**Student_Course Table**

| StudentID | CourseID |
| --------- | -------- |
| 1         | C1       |
| 1         | C2       |

**Course Table**

| CourseID | CourseName | Instructor |
| -------- | ---------- | ---------- |
| C1       | Math       | Mr. Kumar  |
| C2       | Science    | Ms. Neeta  |

---

## Example 3: Convert to 3NF

### 2NF Table

| StudentID | CourseID | CourseName | Instructor | InstructorPhone |
| --------- | -------- | ---------- | ---------- | --------------- |
| 1         | C1       | Math       | Mr. Kumar  | 9876543210      |
| 1         | C2       | Science    | Ms. Neeta  | 8765432190      |

**Issue**: InstructorPhone depends on Instructor → Transitive dependency

### 3NF - Final Tables

**Student_Course Table**

| StudentID | CourseID |
| --------- | -------- |
| 1         | C1       |
| 1         | C2       |

**Course Table**

| CourseID | CourseName | Instructor |
| -------- | ---------- | ---------- |
| C1       | Math       | Mr. Kumar  |
| C2       | Science    | Ms. Neeta  |

**Instructor Table**

| Instructor | Phone      |
| ---------- | ---------- |
| Mr. Kumar  | 9876543210 |
| Ms. Neeta  | 8765432190 |

---

## Example 4: Apply BCNF

### Problem Table

| Project | Manager | Department |
| ------- | ------- | ---------- |
| P1      | M1      | D1         |
| P2      | M2      | D2         |
| P3      | M2      | D2         |

**Assumptions**:

- One manager can only be in one department.
- A project is assigned to one manager.

Here, Manager → Department (but Manager is not a candidate key)

### BCNF Tables

**Project_Manager Table**

| Project | Manager |
| ------- | ------- |
| P1      | M1      |
| P2      | M2      |
| P3      | M2      |

**Manager_Department Table**

| Manager | Department |
| ------- | ---------- |
| M1      | D1         |
| M2      | D2         |

---

## Example 5: Apply 4NF

### Original Table

| Student | Course | Hobby    |
| ------- | ------ | -------- |
| Raj     | Math   | Painting |
| Raj     | Math   | Singing  |

**Issue**: Multi-valued dependency: one student has multiple hobbies AND multiple courses

### 4NF Tables

**Student_Course Table**

| Student | Course |
| ------- | ------ |
| Raj     | Math   |

**Student_Hobby Table**

| Student | Hobby    |
| ------- | -------- |
| Raj     | Painting |
| Raj     | Singing  |

---

## Example 6: Apply 5NF

### Complex Table with Join Dependency

| Supplier | Product | Location |
| -------- | ------- | -------- |
| S1       | P1      | L1       |
| S1       | P2      | L1       |
| S1       | P1      | L2       |

**Goal**: Decompose while preserving all dependencies and avoid anomalies in multiple joins.

### 5NF Tables (Decomposition)

**Supplier_Product Table**

| Supplier | Product |
| -------- | ------- |
| S1       | P1      |
| S1       | P2      |

**Product_Location Table**

| Product | Location |
| ------- | -------- |
| P1      | L1       |
| P2      | L1       |
| P1      | L2       |

**Supplier_Location Table**

| Supplier | Location |
| -------- | -------- |
| S1       | L1       |
| S1       | L2       |

---

## Conclusion

Normalization is a multi-step process that improves database design by eliminating redundancy and maintaining logical relationships. Understanding **all normal forms from 1NF to 5NF** helps ensure high-quality, scalable, and maintainable databases.

Let me know if you'd like visual diagrams or a quick-reference table for each normal form.


# Properties 

# Normalization in SQL - Detailed Explanation with Examples

## Overview

**Normalization** is the process of organizing data in a database to reduce **data redundancy** and improve **data integrity**. It divides large, complex tables into smaller, more manageable pieces without losing data relationships.

---

## Objectives of Normalization

* Eliminate redundant (repetitive) data
* Ensure logical data storage
* Enhance data consistency
* Improve query efficiency

---

## Key Concepts Explained

### Atomicity (used in 1NF)

Atomicity ensures that every field in a table holds indivisible values—i.e., no lists, arrays, or multiple values in a single column.

### Partial Dependency (eliminated in 2NF)

Occurs when a **non-prime attribute** (not part of a candidate key) is functionally dependent on only **part of a composite primary key**. It leads to redundancy and anomalies.

> ✅ Fixed by separating the dependent data into another table.

### Transitive Dependency (eliminated in 3NF)

Occurs when a **non-key attribute** depends on another **non-key attribute** rather than directly on the primary key.

> ✅ Fixed by moving dependent columns into a new table.

### Determinant (important in BCNF)

A determinant is any attribute (or set of attributes) on which some other attribute is fully functionally dependent. In BCNF, **every determinant must be a candidate key**.

### Multivalued Dependency (eliminated in 4NF)

Occurs when one attribute in a table **independently determines multiple values of another attribute**, not functionally dependent.

> ✅ Fixed by placing them in separate tables.

### Join Dependency (eliminated in 5NF)

Occurs when a table can be **reconstructed from multiple smaller tables**, but not just two at a time (requires n-way join).

> ✅ Solved by decomposing the table further without data loss.

---

## Types of Normal Forms

### 1. First Normal Form (1NF)

* Ensures that each column contains **atomic values** (no multiple values in a single field)
* Each record is unique

### 2. Second Normal Form (2NF)

* Must be in 1NF
* No **partial dependency** (non-key attributes depend on entire primary key)

### 3. Third Normal Form (3NF)

* Must be in 2NF
* No **transitive dependency** (non-key attributes must depend only on the primary key)

### 4. Boyce-Codd Normal Form (BCNF)

* A stricter version of 3NF
* Every determinant must be a candidate key
* Used when a table is in 3NF but still has anomalies due to **non-candidate keys** determining other attributes

### 5. Fourth Normal Form (4NF)

* Must be in BCNF
* No **multi-valued dependencies**

### 6. Fifth Normal Form (5NF)

* Must be in 4NF
* Deals with **join dependency** and lossless decomposition

---

## \[All Example Sections Continue Below Unchanged]

(Examples 1 to 6 remain the same as before and demonstrate the normal forms in action)

---

## Conclusion

Normalization is a multi-step process that improves database design by eliminating redundancy and maintaining logical relationships. Understanding **all normal forms from 1NF to 5NF**, along with their related dependency properties, helps ensure high-quality, scalable, and maintainable databases.

Let me know if you'd like visual diagrams or a quick-reference table for each normal form.
