# Using AND and OR Operators

Watch the video : [AND ,OR and NOT](https://www.loom.com/share/d3951abcbc3544f199ca8c75eab443d7?sid=e7e45be7-e542-4f36-be51-d940684006d9) for understanding AND,OR and NOT Operators.

After watching the video complete the following question.

You are analyzing the products table, which stores product details.

## Deliverables:

You are given a table called Products with the following structure:

    product_id|product_name|category|price|in_stock

    1|Smartphone|Electronics|50000|Yes

    2|Microwave Oven|Appliances|15000|No

    3|Laptop|Electronics|70000|Yes

    4|Vacuum Cleaner|Appliances|12000|Yes

    5|Wireless Earbuds|Electronics|3000|Yes

### Questions:

Write a query to retrieve all products that:

    Belong to the Electronics category AND cost more than 10,000.
    OR are in stock in the Appliances category.
    Use product_id, product_name, category, price, and in_stock as the output columns

### Expected Output:

product_id|product_name|category|price|in_stock

    1|Smartphone|Electronics|50000|Yes

    3|Laptop|Electronics|70000|Yes

    4|Vacuum Cleaner|Appliances|12000|Yes

## Query

```sql

-- CREATE TABLE Products (
--     product_id INT,
--     product_name VARCHAR(255),
--     category VARCHAR(255),
--     price INT,
--     in_stock VARCHAR(3)
-- );

-- INSERT INTO Products (product_id, product_name, category, price, in_stock)
-- VALUES
-- (1, 'Smartphone', 'Electronics', 50000, 'Yes'),
-- (2, 'Microwave Oven', 'Appliances', 15000, 'No'),
-- (3, 'Laptop', 'Electronics', 70000, 'Yes'),
-- (4, 'Vacuum Cleaner', 'Appliances', 12000, 'Yes'),
-- (5, 'Wireless Earbuds', 'Electronics', 3000, 'Yes');


--Write your code here

select * from Products where category = 'Electronics' and price > 10000 or in_stock = 'Yes' and category = 'Appliances';
```

# Using NOT

## Deliverables:

You are given a table called Employees with the following structure:

    emp_id|emp_name|department|salary|joining_date

    1|Alice|HR|45000|2022-05-15

    2|Bob|IT|60000|2021-03-12

    3|Charlie|IT|75000|2023-01-20

    4|Diana|HR|50000|2020-08-25

    5|Eve|Sales|65000|2023-06-10

### Question:

Write a query to retrieve all employees who:

Do NOT work in the HR department.
Do NOT have a salary less than 50,000.
Use emp_id, emp_name, department, salary, and joining_date as the output columns.

### Expected Output:

emp_id|emp_name|department|salary|joining_date

2|Bob|IT|60000|2021-03-12

3|Charlie|IT|75000|2023-01-20

5|Eve|Sales|65000|2023-06-10

## Query

```sql

-- CREATE TABLE Employees (
--     emp_id INT,
--     emp_name VARCHAR(255),
--     department VARCHAR(255),
--     salary INT,
--     joining_date DATE
-- );

-- INSERT INTO Employees (emp_id, emp_name, department, salary, joining_date)
-- VALUES
-- (1, 'Alice', 'HR', 45000, '2022-05-15'),
-- (2, 'Bob', 'IT', 60000, '2021-03-12'),
-- (3, 'Charlie', 'IT', 75000, '2023-01-20'),
-- (4, 'Diana', 'HR', 50000, '2020-08-25'),
-- (5, 'Eve', 'Sales', 65000, '2023-06-10');


--Write your code here

select * from Employees where (not department = 'HR')  and (not salary < 50000)
```
