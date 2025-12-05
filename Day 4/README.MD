# **Day 4: Joins and Subqueries**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 4

## **Overview**

In Day 4, we’ll dive into two essential topics in SQL:

1. **Joins**: The most common way to combine data from multiple tables.
2. **Subqueries**: Queries nested inside other queries to perform more complex data retrieval.

Both techniques are crucial for handling relational databases efficiently and will allow you to manipulate and retrieve data from multiple tables in a flexible manner.

---

## **Learning Objectives**

By the end of this session, you will be able to:

1. Understand and implement different types of **joins** in SQL, including:

   * **INNER JOIN**
   * **LEFT JOIN**
   * **RIGHT JOIN**
   * **FULL JOIN** (Conceptual, as MySQL does not support it natively)
2. Use **subqueries** to perform complex queries inside other queries.
3. Learn how to combine joins and subqueries for advanced data retrieval.

---

## **Key Concepts**

### **1. Joins**

A **join** allows you to combine rows from two or more tables based on a related column between them. There are several types of joins in SQL:

#### **1.1 INNER JOIN**

* Combines rows from both tables where there is a match in both tables. Non-matching rows are excluded.

  **Syntax**:

  ```sql
  SELECT columns
  FROM table1
  INNER JOIN table2
  ON table1.column = table2.column;
  ```

#### **1.2 LEFT JOIN (or LEFT OUTER JOIN)**

* Retrieves all records from the left table and matching rows from the right table. If no match is found, NULL values are returned for columns from the right table.

  **Syntax**:

  ```sql
  SELECT columns
  FROM table1
  LEFT JOIN table2
  ON table1.column = table2.column;
  ```

#### **1.3 RIGHT JOIN (or RIGHT OUTER JOIN)**

* Similar to the LEFT JOIN, but retrieves all records from the right table and matching rows from the left table.

  **Syntax**:

  ```sql
  SELECT columns
  FROM table1
  RIGHT JOIN table2
  ON table1.column = table2.column;
  ```

#### **1.4 FULL JOIN (Conceptual)**

* Retrieves all records when there is a match in either the left or right table. This join is not directly supported by MySQL, but you can achieve similar results using a combination of **LEFT JOIN** and **RIGHT JOIN**.

---

### **2. Subqueries**

A **subquery** is a query nested inside another query. Subqueries can be used in **SELECT**, **INSERT**, **UPDATE**, and **DELETE** statements to perform operations that require multiple steps of data retrieval.

#### **2.1 Types of Subqueries**

* **Single-row subquery**: Returns a single value.
* **Multi-row subquery**: Returns multiple values.
* **Correlated subquery**: Depends on the outer query and is re-executed for each row in the outer query.

#### **Example Syntax**:

**Subquery in SELECT**:

```sql
SELECT name, department 
FROM employees
WHERE salary = (SELECT MAX(salary) FROM employees);
```

**Subquery in WHERE**:

```sql
SELECT name, department 
FROM employees 
WHERE department IN (SELECT department FROM departments WHERE budget > 500000);
```

---

## **Lab Overview**

In today’s hands-on lab, you'll:

* Join multiple tables using `INNER JOIN`, `LEFT JOIN`, and `RIGHT JOIN`.
* Practice creating subqueries for more complex data retrieval.
* Work with real-world scenarios where combining data from different tables is required.

---

## **Lab Requirements**

1. **Create Tables and Insert Data**:

   * We’ll work with the following two tables for this session:

     * **employees**: Contains employee details (ID, name, department, salary).
     * **departments**: Contains department details (ID, department name, budget).
2. **Basic SQL Setup**:

   * If you don't have these tables yet, you can create them using the following SQL:

   ```sql
   CREATE TABLE departments (
       department_id INT PRIMARY KEY AUTO_INCREMENT,
       department_name VARCHAR(100),
       budget DECIMAL(10, 2)
   );

   CREATE TABLE employees (
       employee_id INT PRIMARY KEY AUTO_INCREMENT,
       name VARCHAR(100),
       department_id INT,
       salary DECIMAL(10, 2),
       hire_date DATE,
       FOREIGN KEY (department_id) REFERENCES departments(department_id)
   );
   ```

---

## **Example Scenarios for Lab**

1. **INNER JOIN Example**:
   Retrieve a list of employees along with their department names:

   ```sql
   SELECT employees.name, employees.salary, departments.department_name
   FROM employees
   INNER JOIN departments
   ON employees.department_id = departments.department_id;
   ```

2. **LEFT JOIN Example**:
   Retrieve a list of all employees and their department names, including employees who do not belong to any department:

   ```sql
   SELECT employees.name, employees.salary, departments.department_name
   FROM employees
   LEFT JOIN departments
   ON employees.department_id = departments.department_id;
   ```

3. **RIGHT JOIN Example**:
   Retrieve a list of all departments and the employees within them, including departments with no employees:

   ```sql
   SELECT employees.name, employees.salary, departments.department_name
   FROM employees
   RIGHT JOIN departments
   ON employees.department_id = departments.department_id;
   ```

4. **Subquery Example**:
   Retrieve the name of the employee with the highest salary:

   ```sql
   SELECT name
   FROM employees
   WHERE salary = (SELECT MAX(salary) FROM employees);
   ```

5. **Correlated Subquery Example**:
   Retrieve the names of employees who earn more than the average salary of their respective department:

   ```sql
   SELECT e.name
   FROM employees e
   WHERE e.salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);
   ```

---

## **Expected Results**

By the end of this session:

* Learners should be able to write and execute **JOIN** queries to combine data from multiple tables.
* Learners should understand how to write **subqueries** to perform complex filtering and retrieval tasks.
* Learners should be able to combine **joins** and **subqueries** to retrieve data based on advanced business requirements.

---

## **Time Management**

* **Theory and Demonstration**: 45 minutes
* **Lab Exercise**: 45 minutes
* **Q&A and Wrap-up**: 15 minutes

---

## **Conclusion**

On Day 4, we covered powerful SQL concepts like **joins** and **subqueries** that are essential for working with relational data. These techniques are invaluable when working with multiple tables and extracting complex insights from data.

Tomorrow, we’ll continue our journey into **Database Design and Normalization**, diving into how to structure your data efficiently and avoid redundancy.

---
