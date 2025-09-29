# Elevate Labs - SQL Developer Internship Task 5

## Task Overview
This project is the fifth task for the SQL Developer Internship. The objective is to learn how to combine data from multiple tables using the four main types of SQL `JOIN`s: `INNER`, `LEFT`, `RIGHT`, and `FULL OUTER JOIN`.

- **Tools Used:** MySQL Workbench

---
## SQL Queries
The `join_queries.sql` file contains the main deliverable for this task. It includes four queries that demonstrate how to use different `JOIN` types to answer specific business questions. A special data setup was used to clearly show the difference between the joins, especially by including a customer who has never placed an order.

The queries demonstrate:
- `INNER JOIN` to find matching customers and orders.
- `LEFT JOIN` to list all customers and their corresponding orders (if any).
- `RIGHT JOIN` to list all orders and their associated customers.
- A simulation of `FULL OUTER JOIN` using `UNION` to show all records from both tables.

---
## Interview Questions & Answers

### 1. Difference between INNER and LEFT JOIN?
An **`INNER JOIN`** returns only the rows where the join condition is met in **both** tables—it's the intersection. A **`LEFT JOIN`** returns **all** rows from the left table, and only the matching rows from the right table. If there's no match, the columns from the right table will be `NULL`.

### 2. What is a FULL OUTER JOIN?
A `FULL OUTER JOIN` returns all rows when there is a match in either the left or the right table. It's essentially a combination of a `LEFT JOIN` and a `RIGHT JOIN`, showing all records from both tables and matching them where possible.

### 3. Can joins be nested?
Yes. You can join a table to the result set of another join, effectively nesting them to combine data from multiple sources in a specific order.

### 4. How to join more than 2 tables?
You can join more than two tables by simply adding more `JOIN` clauses. For example, you could join `Customers` to `Orders`, and then join that result to a `Products` table.

### 5. What is a cross join?
A `CROSS JOIN` returns the Cartesian product of two tables—it matches every row from the first table with every row from the second table. This is rarely used except in specific analytical scenarios.

### 6. What is a natural join?
A `NATURAL JOIN` is an implicit join that automatically joins tables based on columns that have the same name. It's generally avoided in professional code because it can be ambiguous and lead to unexpected results if schemas change.

### 7. Can you join tables without foreign key?
Yes. You can join tables on any columns that have a logical relationship and matching data types. However, joins on indexed columns (like primary and foreign keys) are much more efficient.

### 8. What is a self-join?
A self-join is a regular join where a table is joined to itself. This is useful for querying hierarchical data, such as finding an employee's manager (where the manager is also an employee in the same table).

### 9. What causes Cartesian product?
A Cartesian product is caused by a `CROSS JOIN` or, more commonly, by a regular join where the `ON` condition is missing or invalid. This results in every row from the first table being matched with every row from the second, which can create a massive, incorrect result set.

### 10. How to optimize joins?
The most important way to optimize joins is to ensure the columns used in the `ON` clause are **indexed**. Typically, these are primary and foreign keys. Additionally, filtering data with a `WHERE` clause before joining can also significantly improve performance.
