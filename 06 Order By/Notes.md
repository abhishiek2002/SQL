## SELECT with ORDER BY Clause

Used to sort the result set.

### Syntax:

```sql
SELECT column1, column2
FROM table_name
ORDER BY column1, column2 ... [ASC|DESC];
```

### Example:

```sql
SELECT Name, Age
FROM Students
ORDER BY Age DESC;
```

This sorts the result by age in descending order.

---