# **Lesson Plan - Day 3: Grouping and Aggregating Data in MySQL**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 3

---

## **Learning Objectives**

By the end of the lesson, learners will be able to:

1. Use the **`GROUP BY`** clause to group data by one or more columns.
2. Apply **aggregate functions** (`COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`) to summarize data.
3. Use the **`HAVING`** clause to filter grouped data.
4. Combine **`GROUP BY`** with **`JOIN`** to aggregate data across multiple tables.

---

## **Materials Needed**

* A MySQL database (use a sample database like `sakila`, `employees`, or `world`).
* Text editor for SQL queries (or MySQL Workbench if preferred).
* Internet connection for accessing online resources.

---

## **Agenda**

### **1. Introduction to Grouping Data with `GROUP BY` (15 minutes)**

* **Objective**: Introduce the concept of grouping data using the `GROUP BY` clause.
* **Overview**:

  * **What is `GROUP BY`?**

    * The `GROUP BY` clause groups rows that have the same values in specified columns into summary rows.
    * It is used to aggregate data by categories (e.g., finding the total salary per department).
  * **Why use `GROUP BY`?**

    * Useful for performing aggregate calculations on data grouped by specific criteria.

**Example**:

```sql
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id;
```

* This query groups employees by their department and counts how many employees are in each department.

**Activity**:

* Have learners write a query to group employees by department and count the number of employees in each department.

---

### **2. Aggregate Functions: `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()` (20 minutes)**

* **Objective**: Teach learners to use aggregate functions to summarize data.
* **Overview**:

  * **What are aggregate functions?**

    * Aggregate functions perform calculations on a set of values and return a single result.
  * Common aggregate functions:

    * **`COUNT()`**: Returns the number of rows.
    * **`SUM()`**: Adds up the values in a numeric column.
    * **`AVG()`**: Returns the average value of a column.
    * **`MIN()`**: Returns the minimum value in a column.
    * **`MAX()`**: Returns the maximum value in a column.

**Examples**:

```sql
-- Calculate the total salary of employees in each department
SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id;

-- Find the average salary in each department
SELECT department_id, AVG(salary) AS avg_salary
FROM employees
GROUP BY department_id;

-- Find the highest salary in each department
SELECT department_id, MAX(salary) AS highest_salary
FROM employees
GROUP BY department_id;
```

**Activity**:

* Have learners write queries to calculate the total, average, minimum, and maximum salary per department.

---

### **3. Filtering Grouped Data with `HAVING` (15 minutes)**

* **Objective**: Introduce the `HAVING` clause to filter results after aggregation.
* **Overview**:

  * **`WHERE` vs. `HAVING`**:

    * `WHERE` filters rows before aggregation (i.e., before `GROUP BY`).
    * `HAVING` filters groups after aggregation (i.e., after `GROUP BY`).
  * Use `HAVING` to filter results based on aggregate calculations (e.g., departments with total salary greater than a specific value).

**Example**:

```sql
SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id
HAVING SUM(salary) > 50000;
```

* This query retrieves departments where the total salary is greater than 50,000.

**Activity**:

* Have learners filter results where the total number of employees in a department is greater than 10 using `HAVING`.

---

### **4. Combining `GROUP BY` with `JOIN` (20 minutes)**

* **Objective**: Show how to use `GROUP BY` with `JOIN` to aggregate data across multiple tables.
* **Overview**:

  * **What is a `JOIN`?**

    * A `JOIN` combines rows from two or more tables based on a related column (e.g., employees and departments).
  * **Using `GROUP BY` with `JOIN`**:

    * When working with multiple tables, you can group the data from the result of a `JOIN`.

**Example**:

```sql
SELECT departments.department_name, SUM(employees.salary) AS total_salary
FROM employees
INNER JOIN departments ON employees.department_id = departments.department_id
GROUP BY departments.department_name;
```

* This query calculates the total salary per department, including department names.

**Activity**:

* Have learners write a query to calculate the total salary in each department, including the department names, using `JOIN` and `GROUP BY`.

---

### **5. Hands-On Lab: Grouping and Aggregating Data (30 minutes)**

* **Objective**: Provide learners with hands-on practice writing complex queries to group and aggregate data.
* **Lab Tasks**:

  1. Write a query to find the total salary in each department.
  2. Write a query to find the average salary of employees who joined after January 1, 2015.
  3. Write a query to find the highest salary in each department and filter to show only departments where the highest salary is greater than 100,000.
  4. Write a query to calculate the total salary in each department, including the department names, using `JOIN`.
  5. Write a query to count the number of employees in each department with more than 10 employees.

**Delivery Tip**:

* As learners work through the exercises, circulate around the room to provide assistance and ensure that everyone understands the concepts.

---

### **6. Review and Q&A (10 minutes)**

* **Objective**: Review key points and clarify any misunderstandings.
* **Overview**:

  * **Key Concepts**:

    * The `GROUP BY` clause is used to group data by one or more columns.
    * Aggregate functions like `COUNT()`, `SUM()`, `AVG()`, `MIN()`, and `MAX()` are used to calculate summary statistics for grouped data.
    * The `HAVING` clause is used to filter results after aggregation.
    * `JOIN` + `GROUP BY` allows you to aggregate data from multiple tables.

**Q&A**:

* Address any questions learners may have about `GROUP BY`, aggregate functions, or `HAVING`. Provide clarification as needed.

---

### **7. Wrap-Up and Next Steps (5 minutes)**

* **Objective**: Summarize the day's content and provide a preview of the next day.
* **Overview**:

  * **Key Concepts Covered**:

    * Grouping data with `GROUP BY`.
    * Using aggregate functions to summarize data.
    * Filtering grouped data with `HAVING`.
    * Combining `GROUP BY` with `JOIN` to aggregate data from multiple tables.
  * **What’s Next**: Tomorrow, we will focus on **Subqueries** and learn how to use them to make more advanced and dynamic queries.

---

## **Materials for Learners**

1. **MySQL Sample Database**: Continue using the sample database from Day 1 (e.g., `sakila` or `employees`).
2. **SQL Query Reference**: Provide learners with a reference sheet for aggregate functions, `GROUP BY`, `HAVING`, and `JOIN`.
3. **Exercises**: Provide a set of practice queries to help learners master grouping and aggregating data.

---

## **Practical Tips for Trainers**

* **Real-World Examples**: Use practical examples (e.g., calculating total sales per product, average salary per department) to make the material relatable.
* **Encourage Practice**: Ensure learners get plenty of hands-on practice with grouping, aggregation, and filtering.
* **Provide Assistance**: Walk around and assist learners who may be struggling with complex queries.
* **Clarify `HAVING` vs `WHERE`**: Emphasize the difference between `WHERE` and `HAVING`, particularly when filtering aggregated data.

---

### **Conclusion**

Day 3 focuses on grouping data and using aggregate functions to analyze it. The ability to group data using `GROUP BY`, calculate summary statistics with aggregate functions, and filter those results with `HAVING` will allow learners to analyze data more effectively. Additionally, combining `GROUP BY` with `JOIN` expands learners’ ability to work with data across multiple tables. This session builds foundational skills that will be used in more advanced SQL tasks.

