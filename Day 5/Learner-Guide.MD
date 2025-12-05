# **Learner Guide - Day 5: Grouping and Aggregating Data**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 5

---

## **Introduction to Day 5**

Welcome to Day 5 of the MySQL crash course! Today, we will focus on **grouping and aggregating data** using SQL. These concepts are fundamental for summarizing and analyzing large datasets, which is a common task in database management and data analysis.

### **What You'll Learn Today:**

1. How to use **GROUP BY** to group rows based on column values.
2. How to apply aggregate functions like `COUNT()`, `SUM()`, `AVG()`, `MIN()`, and `MAX()` to calculate and summarize data.
3. How to filter results from grouped data using **HAVING**.
4. How to combine **GROUP BY** with **JOIN** to aggregate data from multiple tables.

---

## **Learning Objectives**

By the end of today’s session, you will be able to:

1. **Group rows** in a table using the `GROUP BY` clause.
2. Use **aggregate functions** like `COUNT()`, `SUM()`, `AVG()`, `MIN()`, and `MAX()` to summarize data.
3. Filter groups of data using the **HAVING** clause.
4. Combine **GROUP BY** and **JOIN** to analyze data across multiple tables.
5. Solve practical problems involving data aggregation and filtering.

---

## **Key Concepts to Master**

### **1. GROUP BY**

The **`GROUP BY`** clause groups rows in a table that have the same values in specified columns into summary rows. It is commonly used with aggregate functions to summarize data.

#### **Syntax of `GROUP BY`:**

```sql
SELECT column_name, aggregate_function(column_name)
FROM table_name
GROUP BY column_name;
```

**Example**:
Let’s say we have an **employees** table with `department_id` and `salary` columns. To count the number of employees in each department, we use:

```sql
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id;
```

This query will group employees by `department_id` and count how many employees are in each department.

---

### **2. Aggregate Functions**

Aggregate functions perform calculations on a set of values and return a single result. These functions are typically used with `GROUP BY`.

* **`COUNT()`**: Counts the number of rows.
* **`SUM()`**: Adds up numeric values.
* **`AVG()`**: Calculates the average of numeric values.
* **`MIN()`**: Returns the smallest value.
* **`MAX()`**: Returns the largest value.

#### **Examples of Aggregate Functions:**

```sql
-- Counting the number of employees in each department
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id;

-- Summing the total salary in each department
SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id;

-- Calculating the average salary in each department
SELECT department_id, AVG(salary) AS avg_salary
FROM employees
GROUP BY department_id;
```

---

### **3. HAVING**

The **`HAVING`** clause is used to filter groups after the `GROUP BY` operation has been applied. While `WHERE` filters rows before aggregation, `HAVING` filters the groups created by `GROUP BY`.

#### **Syntax of `HAVING`:**

```sql
SELECT column_name, aggregate_function(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Example**:
To find departments with more than 5 employees:

```sql
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id
HAVING COUNT(*) > 5;
```

---

### **4. Combining GROUP BY and JOIN**

You can use `JOIN` in combination with `GROUP BY` to aggregate data from multiple related tables. This is useful when you want to group data from one table and bring in related data from another table (e.g., combining employee and department data).

#### **Example: Using JOIN with GROUP BY**

To calculate the total salary by department and display the department names, we use:

```sql
SELECT departments.department_name, SUM(employees.salary) AS total_salary
FROM employees
INNER JOIN departments ON employees.department_id = departments.department_id
GROUP BY departments.department_name;
```

This query joins the `employees` table with the `departments` table, groups the data by `department_name`, and calculates the total salary in each department.

---

## **Practical Examples**

### **Example 1: COUNT()**

To count how many employees are in each department, use the following query:

```sql
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id;
```

### **Example 2: SUM()**

To calculate the total salary of all employees in each department:

```sql
SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id;
```

### **Example 3: AVG()**

To find the average salary of employees in each department:

```sql
SELECT department_id, AVG(salary) AS avg_salary
FROM employees
GROUP BY department_id;
```

### **Example 4: HAVING**

To find departments with more than 3 employees:

```sql
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id
HAVING COUNT(*) > 3;
```

### **Example 5: Combining GROUP BY and JOIN**

To find the total salary by department and include department names:

```sql
SELECT departments.department_name, SUM(employees.salary) AS total_salary
FROM employees
INNER JOIN departments ON employees.department_id = departments.department_id
GROUP BY departments.department_name;
```

---

## **Lab Exercises**

### **Task 1: GROUP BY and COUNT()**

Write a query that counts how many employees there are in each department.

### **Task 2: GROUP BY and SUM()**

Write a query that calculates the total salary paid to employees in each department.

### **Task 3: Using HAVING**

Write a query that returns departments with more than 3 employees.

### **Task 4: GROUP BY and JOIN**

Write a query that finds the total salary for each department, displaying the department name.

---

## **Next Steps**

1. **Practice**: Continue practicing with **aggregate functions** and **GROUP BY**. Try using more complex queries that combine multiple functions and conditions.
2. **Review**: Revisit the exercises if you need additional help or clarification.
3. **Prepare for Tomorrow**: In the next session, we will discuss **Subqueries and Complex Joins**, which will build upon today’s concepts.

---

## **Summary of Key Concepts**

* **GROUP BY**: Groups rows based on specific column values.
* **Aggregate Functions**: `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()` to summarize data.
* **HAVING**: Filters groups created by `GROUP BY`.
* **JOIN + GROUP BY**: Aggregating data from multiple tables.

