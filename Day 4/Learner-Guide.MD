# **Learner Guide - Day 4: Joins and Subqueries**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 4

---

## **Introduction to Day 4**

Welcome to Day 4 of the MySQL crash course! Today, we will focus on two essential SQL techniques:

1. **Joins** – Combining data from multiple tables.
2. **Subqueries** – Nesting queries to perform complex operations.

These techniques are fundamental for working with relational databases, allowing you to retrieve, manipulate, and analyze data across tables.

---

## **Learning Objectives**

By the end of today’s session, you will be able to:

1. Understand and use different types of **joins**:

   * **INNER JOIN**
   * **LEFT JOIN**
   * **RIGHT JOIN**
   * **FULL JOIN** (Conceptual)
2. Use **subqueries** to filter data, aggregate results, and solve complex queries.
3. Combine **joins** and **subqueries** to write more advanced SQL queries.
4. Solve practical problems using both **joins** and **subqueries**.

---

## **Key Concepts to Master**

### **1. Joins**

A **join** allows you to combine data from multiple tables based on a related column. In relational databases, data is often stored in separate tables, and joins let you bring the data together.

#### **Types of Joins**:

1. **INNER JOIN**:

   * Combines rows from both tables where there is a match.
   * Non-matching rows are excluded.
   * Example:

     ```sql
     SELECT employees.name, departments.department_name
     FROM employees
     INNER JOIN departments
     ON employees.department_id = departments.department_id;
     ```
   * Result: Only employees with a valid department are returned.

2. **LEFT JOIN (or LEFT OUTER JOIN)**:

   * Retrieves all rows from the left table, and matching rows from the right table.
   * If there is no match, `NULL` values are returned for the right table’s columns.
   * Example:

     ```sql
     SELECT employees.name, departments.department_name
     FROM employees
     LEFT JOIN departments
     ON employees.department_id = departments.department_id;
     ```
   * Result: All employees will be returned, including those without a department.

3. **RIGHT JOIN (or RIGHT OUTER JOIN)**:

   * Retrieves all rows from the right table, and matching rows from the left table.
   * If there is no match, `NULL` values are returned for the left table’s columns.
   * Example:

     ```sql
     SELECT employees.name, departments.department_name
     FROM employees
     RIGHT JOIN departments
     ON employees.department_id = departments.department_id;
     ```
   * Result: All departments will be returned, even those without employees.

4. **FULL JOIN (Conceptual)**:

   * Retrieves all rows when there is a match in either the left or right table.
   * MySQL does not support FULL JOIN natively, but you can combine `LEFT JOIN` and `RIGHT JOIN` to simulate it.
   * Example:

     ```sql
     SELECT employees.name, departments.department_name
     FROM employees
     LEFT JOIN departments ON employees.department_id = departments.department_id
     UNION
     SELECT employees.name, departments.department_name
     FROM employees
     RIGHT JOIN departments ON employees.department_id = departments.department_id;
     ```
   * Result: All employees and departments, including those with no matches.

---

### **2. Subqueries**

A **subquery** is a query that is nested inside another query. Subqueries can be used in **SELECT**, **FROM**, **WHERE**, and **HAVING** clauses to perform more complex operations.

#### **Types of Subqueries**:

1. **Single-row Subquery**:

   * Returns a single value.
   * Example:

     ```sql
     SELECT name
     FROM employees
     WHERE salary = (SELECT MAX(salary) FROM employees);
     ```
   * Result: The employee with the highest salary.

2. **Multi-row Subquery**:

   * Returns multiple values.
   * Example:

     ```sql
     SELECT name
     FROM employees
     WHERE department_id IN (SELECT department_id FROM departments WHERE budget > 500000);
     ```
   * Result: Employees who work in departments with a budget greater than $500,000.

3. **Correlated Subquery**:

   * References a column from the outer query and is executed for each row.
   * Example:

     ```sql
     SELECT e.name
     FROM employees e
     WHERE e.salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);
     ```
   * Result: Employees who earn more than the average salary in their department.

---

## **Key Skills to Practice**

### **Practice with Joins**:

* Learn how to combine tables using different types of joins.
* Experiment with real-world scenarios like fetching employee and department information or retrieving all employees even if they don’t belong to any department.

### **Practice with Subqueries**:

* Work with **subqueries** in the **SELECT** clause to calculate values such as the highest or lowest salary within a department.
* Use **subqueries** in the **WHERE** clause to filter results based on complex conditions, such as finding employees who earn more than the average salary in their department.

### **Combining Joins and Subqueries**:

* Practice using both **joins** and **subqueries** together. For example, you might use a **join** to combine employee and department information and then use a **subquery** to find the highest salary in each department.

---

## **Example SQL Queries**

### **1. INNER JOIN Example**:

Retrieve a list of employees with their department names.

```sql
SELECT employees.name, employees.salary, departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

### **2. LEFT JOIN Example**:

Retrieve all employees and their departments, including employees who don’t belong to any department.

```sql
SELECT employees.name, employees.salary, departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;
```

### **3. Subquery Example (Single-row)**:

Find the employee with the highest salary.

```sql
SELECT name
FROM employees
WHERE salary = (SELECT MAX(salary) FROM employees);
```

### **4. Subquery Example (Correlated)**:

Find employees who earn more than the average salary in their department.

```sql
SELECT e.name
FROM employees e
WHERE e.salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);
```

---

## **Lab Exercises**

### **Task 1**: **INNER JOIN**

* Use an **INNER JOIN** to retrieve all employees and their department names. If employees don’t belong to any department, they won’t be included.

### **Task 2**: **LEFT JOIN**

* Use a **LEFT JOIN** to retrieve all employees and their department names, including those without departments.

### **Task 3**: **Subquery in WHERE Clause**

* Use a **subquery** to find employees whose salary is greater than the average salary in their department.

### **Task 4**: **Combining Joins and Subqueries**

* Write a query that combines **joins** and **subqueries** to find the department with the highest average salary.

---

## **Next Steps**

1. **Complete the lab exercises** and ensure you understand each type of join and subquery.
2. **Practice** writing queries with **subqueries** in the `WHERE` clause and in the `SELECT` clause.
3. **Review the answers** from the quiz to ensure you understand the key concepts.
4. **Attend the next lesson** on **Database Normalization** and **Best Practices for Efficient Data Design**.

---

## **Conclusion**

Today’s session focused on mastering **Joins** and **Subqueries**, which are essential for working with complex data in relational databases. By the end of this day, you should be able to combine multiple tables using **joins** and handle nested queries using **subqueries** to filter and manipulate data. Practice these skills to gain more confidence in writing SQL queries and solving real-world problems.

---
