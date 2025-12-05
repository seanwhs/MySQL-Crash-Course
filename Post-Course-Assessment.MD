# **Post-Course Assessment: MySQL Fundamentals**

**Course**: MySQL 1-Week Hands-On Crash Course
**Duration**: 30-40 minutes
**Format**: Multiple Choice, True/False, SQL Query Writing, and Short Answer

---

### **Section 1: SQL Basics and Database Concepts**

1. **Which SQL statement is used to modify existing records in a table?**

   a) `UPDATE`
   b) `INSERT`
   c) `SELECT`
   d) `ALTER`

2. **True or False: A `FOREIGN KEY` constraint is used to ensure referential integrity between two tables.**

3. **Which of the following SQL statements will create a table with the columns `id`, `first_name`, and `last_name`?**

   a) `CREATE TABLE employees (id INT PRIMARY KEY, first_name VARCHAR(50), last_name VARCHAR(50));`
   b) `CREATE DATABASE employees (id INT PRIMARY KEY, first_name VARCHAR(50), last_name VARCHAR(50));`
   c) `NEW TABLE employees (id INT, first_name VARCHAR(50), last_name VARCHAR(50));`
   d) `MAKE TABLE employees (id INT, first_name VARCHAR(50), last_name VARCHAR(50));`

4. **What does the `COUNT()` function in SQL return?**

   a) The sum of a column's values
   b) The highest value in a column
   c) The number of rows in a result set
   d) The average of a column's values

---

### **Section 2: SQL Query Writing**

5. **Write an SQL query that retrieves the first and last names of employees who work in the "Sales" department from an `employees` table and a `departments` table.**

   (You can assume that `employees.department_id` is linked to `departments.department_id`.)

   **Your Query:**

---

6. **You are given a table `orders` with the columns `order_id`, `customer_id`, `order_date`, and `total_amount`. Write an SQL query to find the total number of orders and the total amount of sales made in the last 30 days.**

   **Your Query:**

---

7. **Which of the following queries will return all customers who have made at least one order?**

   a)

   ```sql
   SELECT customers.customer_id, customers.name
   FROM customers
   LEFT JOIN orders ON customers.customer_id = orders.customer_id
   WHERE orders.order_id IS NOT NULL;
   ```

   b)

   ```sql
   SELECT customers.customer_id, customers.name
   FROM customers
   INNER JOIN orders ON customers.customer_id = orders.customer_id;
   ```

   c)

   ```sql
   SELECT customers.customer_id, customers.name
   FROM customers
   WHERE customers.customer_id IN (SELECT customer_id FROM orders);
   ```

   d) All of the above

---

### **Section 3: SQL Joins and Relationships**

8. **True or False: The `INNER JOIN` returns all records from both tables, even if there is no match.**

9. **What will the following SQL query return?**

   ```sql
   SELECT e.first_name, e.last_name, d.department_name
   FROM employees e
   LEFT JOIN departments d ON e.department_id = d.department_id;
   ```

   a) All employees, along with their department names (or `NULL` if no department is assigned)
   b) Only employees who belong to a department
   c) All departments, along with employee names (or `NULL` if no employees belong to the department)
   d) All employees, along with their job titles

10. **Write an SQL query to find the employees who do not belong to any department using a `LEFT JOIN`.**

**Your Query:**

---

### **Section 4: Subqueries and Advanced SQL**

11. **True or False: A correlated subquery is executed once for each row returned by the outer query.**

12. **Write an SQL query to find all employees who earn more than the average salary in their department.**

**Your Query:**

---

13. **What does the following SQL query do?**

```sql
SELECT e.first_name, e.last_name
FROM employees e
WHERE e.department_id = (SELECT d.department_id FROM departments d WHERE d.department_name = 'HR');
```

a) Finds employees in the HR department
b) Finds employees whose department_id matches the first department_id found in the `departments` table
c) Finds employees who have a department_id greater than the first department_id in the `departments` table
d) Finds all employees in the company

14. **True or False: The `EXISTS` clause returns TRUE if the subquery returns any results, and FALSE if it returns no results.**

---

### **Section 5: Data Types, Functions, and Query Optimization**

15. **Which SQL function would you use to return the current date and time?**

    a) `CURRENT_DATE()`
    b) `NOW()`
    c) `DATE()`
    d) `GETDATE()`

16. **Which of the following SQL functions is used to return the highest value in a column?**

    a) `MAX()`
    b) `MIN()`
    c) `COUNT()`
    d) `SUM()`

17. **True or False: Adding indexes to columns used in `JOIN` conditions can improve the performance of the query.**

---

### **Section 6: Performance and Optimization**

18. **Which of the following is the best way to ensure faster query performance when working with large tables?**

    a) Avoid using `JOIN` operations
    b) Use indexes on columns that are frequently queried
    c) Use `FULL JOIN` for all queries
    d) Use `HAVING` instead of `WHERE` for filtering results

19. **What does the `EXPLAIN` keyword do when added to an SQL query?**

    a) Explains the purpose of the query
    b) Provides the execution plan for the query, showing how MySQL will execute it
    c) Generates an error message to help debug the query
    d) Provides a detailed description of the query's data types

20. **Write an SQL query to find the total sales amount by each department, only for departments that have more than 5 employees.**

**Your Query:**

---

### **Scoring Guide**

* **0-5 Correct**: Beginner level understanding of SQL. Consider reviewing the course materials and focusing on core concepts.
* **6-15 Correct**: Intermediate understanding. The learner has a good grasp of SQL but may need practice with more advanced topics.
* **16-20 Correct**: Advanced understanding. The learner demonstrates strong SQL skills and is ready to apply them in real-world scenarios.

---

### **Conclusion**

This **Post-Course Assessment** evaluates learners on key concepts covered during the **MySQL 1-Week Hands-On Crash Course**. It is designed to assess their ability to write SQL queries, work with database relationships, optimize queries, and apply more advanced SQL techniques. Based on the results, learners will have a good idea of which areas need further review or practice.
