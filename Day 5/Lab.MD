# **Day 5 Lab: Working with Joins in MySQL**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 5
**Topic**: SQL Joins (INNER, LEFT, RIGHT, FULL)

**Objective**: By the end of this lab, learners should be able to:

1. Use `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, and simulate `FULL JOIN` in SQL.
2. Understand how to combine data from multiple tables.
3. Perform data analysis using joins to retrieve meaningful information.
4. Optimize and troubleshoot queries involving joins.

---

## **Pre-Lab Setup**

1. **Database**: Use the `employees` or `sakila` sample database (or any database with multiple related tables).
2. **Tables Used**:

   * `employees`: Contains employee details (`employee_id`, `first_name`, `last_name`, `department_id`).
   * `departments`: Contains department details (`department_id`, `department_name`).
   * (Optional) `salaries`: Contains employee salary data (`employee_id`, `salary`).
   * (Optional) `orders`: Contains customer orders data (`order_id`, `customer_id`, `order_date`, `amount`).

---

## **Lab Tasks**

### **Task 1: Basic `INNER JOIN`**

**Objective**: Use the `INNER JOIN` to retrieve employees and their corresponding departments.

**Instructions**:

* Write a query to return a list of employee names (`first_name`, `last_name`) and their department names (`department_name`).
* Use an `INNER JOIN` between the `employees` and `departments` tables, joining on the `department_id`.

```sql
SELECT e.first_name, e.last_name, d.department_name
FROM employees e
INNER JOIN departments d ON e.department_id = d.department_id;
```

**Expected Outcome**: The query should return all employees who belong to a department.

---

### **Task 2: `LEFT JOIN` to Include Unmatched Rows**

**Objective**: Use the `LEFT JOIN` to include employees who do not belong to any department.

**Instructions**:

* Write a query that returns all employees (`first_name`, `last_name`) and their department names (`department_name`).
* Use a `LEFT JOIN` to ensure all employees are returned, even if they do not belong to a department.

```sql
SELECT e.first_name, e.last_name, d.department_name
FROM employees e
LEFT JOIN departments d ON e.department_id = d.department_id;
```

**Expected Outcome**: The query should return all employees, with `NULL` values for the `department_name` where the employee is not assigned to a department.

---

### **Task 3: `RIGHT JOIN` to Include Departments Without Employees**

**Objective**: Use the `RIGHT JOIN` to include departments that do not have any employees.

**Instructions**:

* Write a query that returns all departments (`department_name`) and the names of employees (`first_name`, `last_name`) who work in those departments.
* Use a `RIGHT JOIN` to ensure all departments are returned, even if they do not have any employees.

```sql
SELECT e.first_name, e.last_name, d.department_name
FROM employees e
RIGHT JOIN departments d ON e.department_id = d.department_id;
```

**Expected Outcome**: The query should return all departments, with `NULL` values for the employee names in departments that have no employees.

---

### **Task 4: Simulating `FULL JOIN` in MySQL**

**Objective**: Simulate a `FULL JOIN` in MySQL to return all records from both `employees` and `departments` tables.

**Instructions**:

* Since MySQL does not directly support `FULL JOIN`, you will simulate it using a combination of `LEFT JOIN` and `RIGHT JOIN`.
* Write a query that returns all employees and all departments, including those that do not have a match in the other table (showing `NULL` for unmatched rows).

```sql
SELECT e.first_name, e.last_name, d.department_name
FROM employees e
LEFT JOIN departments d ON e.department_id = d.department_id

UNION

SELECT e.first_name, e.last_name, d.department_name
FROM employees e
RIGHT JOIN departments d ON e.department_id = d.department_id;
```

**Expected Outcome**: The query should return all employees and all departments, including those without a match (with `NULL` values where necessary).

---

### **Task 5: Using `JOIN` with Multiple Tables**

**Objective**: Join multiple tables to retrieve detailed employee information along with their salary and department details.

**Instructions**:

* Write a query to return employee names (`first_name`, `last_name`), their department names (`department_name`), and their salary (`salary`).
* Use an `INNER JOIN` between `employees`, `departments`, and `salaries` tables (join on `employee_id` and `department_id`).

```sql
SELECT e.first_name, e.last_name, d.department_name, s.salary
FROM employees e
INNER JOIN departments d ON e.department_id = d.department_id
INNER JOIN salaries s ON e.employee_id = s.employee_id;
```

**Expected Outcome**: The query should return a list of employees with their department names and corresponding salaries.

---

### **Task 6: Handling Performance with Joins**

**Objective**: Optimize a query involving a large dataset.

**Instructions**:

* You are given a large `orders` table with columns (`order_id`, `customer_id`, `order_date`, `total_amount`), and a `customers` table with columns (`customer_id`, `customer_name`).
* Write a query to return the total amount spent by each customer, ordered by the highest spender. Use an `INNER JOIN` between the `orders` and `customers` tables.
* After writing the query, analyze the performance using the `EXPLAIN` keyword.

```sql
EXPLAIN SELECT c.customer_name, SUM(o.total_amount) AS total_spent
FROM customers c
INNER JOIN orders o ON c.customer_id = o.customer_id
GROUP BY c.customer_id
ORDER BY total_spent DESC;
```

**Expected Outcome**: The query should return the total amount spent by each customer, ordered by the highest amount. The `EXPLAIN` output will show the execution plan, helping you understand how MySQL processes the query.

---

### **Task 7: Complex Query with Multiple Joins and Aggregations**

**Objective**: Write a complex query involving multiple joins and aggregations.

**Instructions**:

* Write a query that returns the total sales (`SUM(order_amount)`) for each department, where departments have more than 5 employees.
* Join the `employees` table with `departments` and `orders` tables, and use a `HAVING` clause to filter departments with more than 5 employees.

```sql
SELECT d.department_name, SUM(o.total_amount) AS total_sales
FROM departments d
JOIN employees e ON d.department_id = e.department_id
JOIN orders o ON e.employee_id = o.employee_id
GROUP BY d.department_name
HAVING COUNT(e.employee_id) > 5;
```

**Expected Outcome**: The query should return the total sales for departments that have more than 5 employees, showing the department name and total sales.

---

## **Lab Submission**

After completing the tasks, learners should:

1. Submit the SQL queries they’ve written for each task.
2. Include the results of each query if possible (especially for tasks where the results are displayed).
3. Submit the performance analysis (`EXPLAIN` output) for Task 6.

---

## **Bonus Task: Real-World Scenario**

**Objective**: Solve a real-world problem using SQL joins.

**Instructions**:

* Imagine you are building a reporting dashboard for an e-commerce company. You need to create a report showing which customers have not placed any orders in the last 6 months.
* The company has `customers` and `orders` tables. Use `LEFT JOIN` and `WHERE` to write a query that returns a list of customers who have not placed an order in the last 6 months.

```sql
SELECT c.customer_name
FROM customers c
LEFT JOIN orders o ON c.customer_id = o.customer_id AND o.order_date > CURDATE() - INTERVAL 6 MONTH
WHERE o.order_id IS NULL;
```

**Expected Outcome**: The query should return the list of customers who have not placed any orders in the last 6 months.

---

## **Lab Review and Wrap-Up**

At the end of the lab:

* Discuss the queries and solutions with the learners.
* Review how different types of joins can be used to solve various business problems.
* Emphasize performance considerations when working with large datasets and using joins.

---

This **Day 5 Lab** will help learners practice and solidify their understanding of SQL joins in a hands-on manner. Let me know if you need further adjustments or have specific requests for the lab!
