Here’s the **Learner Guide** for **Day 3: CRUD Operations (Create, Read, Update, Delete)**. This guide will help learners understand the objectives and tasks for the day, provide step-by-step instructions, and give examples they can follow during the lab.

---

# **Learner Guide - Day 3: CRUD Operations (Create, Read, Update, Delete)**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 3
**Duration:** 2-3 hours

---

## **Overview**

In today’s lesson, we’ll focus on **CRUD operations**, which are the fundamental operations for interacting with any relational database. By the end of today, you’ll be able to:

* **Create** new data in your database using `INSERT INTO`.
* **Read** data from your database with `SELECT`.
* **Update** existing data with `UPDATE`.
* **Delete** data using `DELETE`.

We will also work with **aggregate functions** like `COUNT()`, `SUM()`, and `AVG()` to summarize your data.

---

## **Learning Objectives**

By the end of Day 3, you will be able to:

* **Insert data** into a table using `INSERT INTO`.
* **Retrieve data** using the `SELECT` statement.
* **Update existing data** using `UPDATE`.
* **Delete data** with the `DELETE` statement.
* **Summarize data** with aggregate functions like `COUNT()`, `SUM()`, and `AVG()`.
* Apply **filtering**, **sorting**, and **limiting** techniques to queries.

---

## **Key Concepts**

### **1. Insert Data (Create)**

* **Syntax**:

  ```sql
  INSERT INTO table_name (column1, column2, ...) 
  VALUES (value1, value2, ...);
  ```

* **Example**:
  Insert a new employee into the `employees` table:

  ```sql
  INSERT INTO employees (name, department, salary, hire_date) 
  VALUES ('John Doe', 'HR', 50000, '2022-06-15');
  ```

### **2. Retrieve Data (Read)**

* **Syntax**:

  ```sql
  SELECT column1, column2, ... FROM table_name;
  ```

* **Filtering**: Use `WHERE` to filter data.

  ```sql
  SELECT name, salary FROM employees WHERE salary > 60000;
  ```

* **Sorting**: Use `ORDER BY` to sort data.

  ```sql
  SELECT name, salary FROM employees ORDER BY salary DESC;
  ```

* **Limiting**: Use `LIMIT` to restrict the number of rows returned.

  ```sql
  SELECT * FROM employees LIMIT 5;
  ```

### **3. Update Data (Update)**

* **Syntax**:

  ```sql
  UPDATE table_name 
  SET column1 = value1, column2 = value2, ... 
  WHERE condition;
  ```

* **Example**:
  Increase the salary of all employees in the `HR` department by 10%:

  ```sql
  UPDATE employees SET salary = salary * 1.10 WHERE department = 'HR';
  ```

### **4. Delete Data (Delete)**

* **Syntax**:

  ```sql
  DELETE FROM table_name WHERE condition;
  ```

* **Example**:
  Delete an employee based on their name:

  ```sql
  DELETE FROM employees WHERE name = 'Mark Johnson';
  ```

* **Caution**: Always use the `WHERE` clause to avoid deleting all rows in the table.

### **5. Aggregate Functions**

* **COUNT()**: Counts the number of rows in a result set.

  ```sql
  SELECT COUNT(*) FROM employees;
  ```

* **SUM()**: Returns the total sum of a numeric column.

  ```sql
  SELECT SUM(salary) FROM employees;
  ```

* **AVG()**: Returns the average value of a numeric column.

  ```sql
  SELECT AVG(salary) FROM employees;
  ```

---

## **Step-by-Step Lab Instructions**

### **1. Insert Data (Create)**

* **Task 1**: Add a new employee to the `employees` table.

  * Name: `Alice Green`
  * Department: `Marketing`
  * Salary: `62000`
  * Hire Date: `2023-01-10`

  Use the `INSERT INTO` statement to insert this data.

---

### **2. Retrieve Data (Read)**

* **Task 2.1**: Retrieve the names and salaries of all employees in the `IT` department.

* **Task 2.2**: Retrieve all employees with a salary greater than `60000`.

* **Task 2.3**: Retrieve the first 3 employees listed in the `employees` table.

---

### **3. Update Data (Update)**

* **Task 3.1**: Increase the salary of all employees in the `HR` department by 10%.

* **Task 3.2**: Change the department of `Mark Johnson` to `Marketing`.

---

### **4. Delete Data (Delete)**

* **Task 4.1**: Delete the employee record for `Emily Davis`.

* **Task 4.2**: Delete all employees who have a salary less than `60000`.

---

### **5. Aggregate Functions**

* **Task 5.1**: Find the average salary of all employees.

* **Task 5.2**: Count how many employees are in the `HR` department.

* **Task 5.3**: Find the highest salary among all employees.

---

### **6. Combine Operations (Bonus Task)**

* **Task 6**: Retrieve a list of employees who have a salary greater than `60000`, ordered by their `hire_date` in ascending order, and limit the results to the first 5 records.

---

## **Troubleshooting Tips**

* **Missing `WHERE` Clause**: When using `UPDATE` or `DELETE`, always make sure to include a `WHERE` clause to avoid unintended changes or deletions. For example, forgetting to specify the `WHERE` clause could update or delete all rows in the table.

* **Order of Operations**: Make sure to complete tasks in the correct order. You must insert data before attempting to read, update, or delete it.

* **Data Types**: Be mindful of the data types when inserting values. For instance, make sure that you insert a string into a `VARCHAR` column and a date into a `DATE` column.

---

## **Next Steps After the Lab**

1. **Review the Concepts**: Go over the key CRUD operations again. Ensure that you understand the differences between `INSERT INTO`, `UPDATE`, and `DELETE`.

2. **Practice More Queries**: Try combining multiple operations in a single query, and practice filtering, sorting, and aggregating data.

3. **Look Ahead**: In the next session, we'll dive into **Joins**—a powerful technique to retrieve related data from multiple tables.

---

### **Trainer Tips**:

* **Pacing**: Make sure learners are able to complete the lab within the given time frame. Check in with each learner to see if they need help.
* **Live Examples**: Perform a live demo for one of the lab tasks, like inserting data or performing a `SELECT` query.
* **Engagement**: Encourage learners to ask questions during the lab and offer help with debugging common errors.

---

This **Learner Guide** should provide students with all the resources they need to follow along with the lesson and successfully complete the lab exercises. 