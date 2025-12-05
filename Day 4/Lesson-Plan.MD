# **Lesson Plan - Day 4: Working with Subqueries and Advanced Filtering in MySQL**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 4

---

## **Learning Objectives**

By the end of this lesson, learners will be able to:

1. Understand and write **subqueries** in SQL.
2. Use subqueries in the **`SELECT`**, **`FROM`**, and **`WHERE`** clauses.
3. Apply **advanced filtering** techniques using **`IN`**, **`EXISTS`**, and **`ANY`**.
4. Learn the difference between **correlated** and **non-correlated** subqueries.
5. Combine subqueries with **`JOIN`** to filter data more efficiently.

---

## **Materials Needed**

* A MySQL database (use a sample database like `sakila`, `employees`, or `world`).
* Text editor for SQL queries (or MySQL Workbench if preferred).
* Internet connection for accessing online resources.

---

## **Agenda**

### **1. Introduction to Subqueries (15 minutes)**

* **Objective**: Explain what subqueries are and why they are useful.
* **Overview**:

  * A **subquery** is a query nested inside another query.
  * **Purpose of Subqueries**: To retrieve intermediate results for use in a main query (e.g., finding employees who earn above the average salary).

**Example**:

```sql
SELECT first_name, last_name, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

* This query finds employees whose salary is above the average salary of all employees.

**Key Points**:

* Subqueries are enclosed in parentheses.
* They can return a single value (scalar subqueries) or multiple rows/columns.

---

### **2. Subqueries in the `SELECT` Clause (20 minutes)**

* **Objective**: Teach learners how to use subqueries in the `SELECT` clause to calculate values on the fly.
* **Overview**:

  * A subquery can be used within the `SELECT` clause to create calculated columns.
  * Example: Retrieve employees' salaries and also include their department's average salary.

**Example**:

```sql
SELECT first_name, last_name, salary,
       (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id) AS avg_department_salary
FROM employees e;
```

* This query returns each employee’s salary along with the average salary for their department.

**Activity**:

* Have learners write a query to display each employee's salary and the maximum salary in their department.

---

### **3. Subqueries in the `FROM` Clause (15 minutes)**

* **Objective**: Teach how to use subqueries in the `FROM` clause to create temporary tables for complex queries.
* **Overview**:

  * Subqueries in the `FROM` clause are treated like temporary tables.
  * This can be useful for simplifying complex queries or when aggregating data in multiple steps.

**Example**:

```sql
SELECT department_id, MAX(salary) AS max_salary
FROM (SELECT department_id, salary FROM employees WHERE hire_date > '2015-01-01') AS recent_hires
GROUP BY department_id;
```

* This query finds the maximum salary in each department for employees hired after January 1, 2015.

**Activity**:

* Have learners write a query to find the highest salary in each department for employees who have been with the company for more than 5 years.

---

### **4. Subqueries in the `WHERE` Clause (20 minutes)**

* **Objective**: Teach learners how to use subqueries in the `WHERE` clause to filter data.
* **Overview**:

  * **Non-correlated subqueries**: A subquery that can be executed independently of the outer query.
  * **Correlated subqueries**: A subquery that depends on values from the outer query.

**Example 1**: Non-correlated subquery:

```sql
SELECT first_name, last_name, salary
FROM employees
WHERE department_id = (SELECT department_id FROM departments WHERE department_name = 'HR');
```

* This query finds all employees who work in the HR department.

**Example 2**: Correlated subquery:

```sql
SELECT first_name, last_name, salary
FROM employees e
WHERE salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);
```

* This query finds employees whose salary is greater than the average salary for their department.

**Activity**:

* Have learners write a query to find employees who earn more than the average salary for their department.

---

### **5. Advanced Filtering with `IN`, `EXISTS`, and `ANY` (20 minutes)**

* **Objective**: Teach learners advanced filtering techniques using `IN`, `EXISTS`, and `ANY`.
* **Overview**:

  * **`IN`**: Used to check if a value matches any value in a list or subquery.
  * **`EXISTS`**: Checks if a subquery returns any result. It returns a boolean value (TRUE or FALSE).
  * **`ANY`**: Compares a value to one or more values returned by a subquery. It returns TRUE if the condition is met for any of the values.

**Examples**:

* **`IN`**:

```sql
SELECT first_name, last_name
FROM employees
WHERE department_id IN (SELECT department_id FROM departments WHERE location_id = 1700);
```

* **`EXISTS`**:

```sql
SELECT first_name, last_name
FROM employees e
WHERE EXISTS (SELECT 1 FROM departments d WHERE d.department_id = e.department_id AND d.department_name = 'Sales');
```

* **`ANY`**:

```sql
SELECT first_name, last_name
FROM employees
WHERE salary > ANY (SELECT salary FROM employees WHERE department_id = 2);
```

**Activity**:

* Have learners write queries using `IN`, `EXISTS`, and `ANY` to filter employees based on various criteria (e.g., department location, departments with employees earning above a certain salary).

---

### **6. Hands-On Lab: Subqueries and Advanced Filtering (30 minutes)**

* **Objective**: Provide learners with hands-on experience writing complex queries involving subqueries and advanced filtering techniques.
* **Lab Tasks**:

  1. Write a query to find employees who earn more than the average salary in their department using a **correlated subquery**.
  2. Write a query to list the department names and the highest salary in each department, but only for departments that have employees earning above 60,000.
  3. Write a query to list employees who have the same department_id as those with a salary greater than the average salary for all employees.
  4. Write a query to return the department names and average salary for departments located in a specific location (use `IN`).
  5. Write a query to find employees who belong to departments with more than 5 employees (use `EXISTS`).

**Delivery Tip**:

* As learners work through the lab tasks, circulate and assist them with writing and troubleshooting their subqueries.
* Encourage learners to experiment with correlated and non-correlated subqueries.

---

### **7. Review and Q&A (10 minutes)**

* **Objective**: Review the key concepts covered in the lesson and answer any questions.
* **Overview**:

  * **Key Concepts**:

    * Subqueries in `SELECT`, `FROM`, and `WHERE` clauses.
    * Correlated vs non-correlated subqueries.
    * Advanced filtering using `IN`, `EXISTS`, and `ANY`.
  * **Q&A**: Open the floor for any remaining questions or clarifications. Provide further examples as needed.

---

### **8. Wrap-Up and Next Steps (5 minutes)**

* **Objective**: Summarize the day’s lessons and introduce the next day’s topic.
* **Overview**:

  * **Key Concepts Covered**:

    * How to write and use subqueries in different parts of a query.
    * Advanced filtering techniques with `IN`, `EXISTS`, and `ANY`.
  * **What’s Next**: Tomorrow, we will focus on **Joining Multiple Tables** and handling more complex relationships between data.

---

## **Materials for Learners**

1. **MySQL Sample Database**: Continue with the sample database from previous days (e.g., `sakila`, `employees`).
2. **SQL Query Reference**: Provide a reference sheet for subqueries, including syntax for `SELECT`, `FROM`, and `WHERE` subqueries.
3. **Exercises**: Provide a set of practice queries to help learners master subqueries and advanced filtering.

---

## **Practical Tips for Trainers**

* **Provide Examples**: Ensure you provide multiple examples, particularly showing the difference between correlated and non-correlated subqueries.
* **Encourage Experimentation**: Allow learners to explore different ways of using subqueries and advanced filtering techniques. Provide guidance on troubleshooting common errors, like improper subquery structure or incorrect logic.
* **Explain the Logic**: For correlated subqueries, emphasize the idea that the subquery is re-executed for each row in the outer query.

---

### **Conclusion**

Day 4 introduces learners to **subqueries** and **advanced filtering techniques**
