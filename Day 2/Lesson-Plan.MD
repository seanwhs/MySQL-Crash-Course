# **Lesson Plan - Day 2: Filtering and Sorting Data in MySQL**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 2

---

## **Learning Objectives**

By the end of the lesson, learners will be able to:

1. Use **logical operators** (`AND`, `OR`, `NOT`) to build complex filtering conditions in SQL.
2. Apply **comparison operators** like `=`, `>`, `<`, `BETWEEN`, `IN`, and `LIKE` in SQL queries.
3. Use **ORDER BY** to sort query results.
4. Use **LIMIT** to restrict the number of results returned by a query.
5. Write more advanced **SQL queries** involving multiple conditions and sorting.

---

## **Materials Needed**

* A MySQL database (use a sample database like `sakila`, `employees`, or `world`).
* Text editor for SQL queries (or MySQL Workbench if preferred).
* Internet connection if using online resources.

---

## **Agenda**

### **1. Introduction to Advanced Filtering (10 minutes)**

* **Objective**: Introduce learners to the concept of advanced filtering using SQL’s logical and comparison operators.
* **Overview**:

  * **Why advanced filtering?**

    * Real-world data is rarely clean or simple, and filtering with complex conditions is essential for meaningful insights.
  * **SQL Comparison Operators**:

    * `=`, `>`, `<`, `>=`, `<=`, `<>` (not equal), `BETWEEN`, `IN`, `LIKE`, `IS NULL`.

**Example**:

```sql
SELECT first_name, last_name, salary
FROM employees
WHERE salary > 50000 AND department_id = 3;
```

* This query selects employees with a salary above 50,000 who belong to department 3.

---

### **2. Using Logical Operators (`AND`, `OR`, `NOT`) (15 minutes)**

* **Objective**: Teach how to combine multiple conditions using logical operators in SQL queries.
* **Overview**:

  * **`AND`**: Returns rows where all conditions are true.
  * **`OR`**: Returns rows where at least one condition is true.
  * **`NOT`**: Excludes rows that meet the condition.

**Examples**:

```sql
-- Using AND
SELECT first_name, last_name
FROM employees
WHERE salary > 60000 AND hire_date < '2015-01-01';

-- Using OR
SELECT first_name, last_name
FROM employees
WHERE department_id = 1 OR department_id = 2;

-- Using NOT
SELECT first_name, last_name
FROM employees
WHERE NOT department_id = 5;
```

**Activity**:

* Have learners practice writing queries using `AND`, `OR`, and `NOT` to filter records based on different conditions.

---

### **3. Comparison Operators (`=`, `>`, `<`, `BETWEEN`, `IN`, `LIKE`) (20 minutes)**

* **Objective**: Deepen the learners' understanding of comparison operators and their usage in SQL queries.
* **Overview**:

  * **`=`**: Equal to.
  * **`>` and `<`**: Greater than and less than.
  * **`BETWEEN`**: Filters results within a specific range.
  * **`IN`**: Filters results based on a set of values.
  * **`LIKE`**: Filters results using pattern matching.
  * **`IS NULL`**: Filters results where the value is `NULL`.

**Examples**:

```sql
-- Equal to
SELECT first_name, last_name
FROM employees
WHERE department_id = 3;

-- Greater than
SELECT first_name, last_name, salary
FROM employees
WHERE salary > 50000;

-- BETWEEN (range)
SELECT first_name, last_name, hire_date
FROM employees
WHERE hire_date BETWEEN '2010-01-01' AND '2015-12-31';

-- IN (set of values)
SELECT first_name, last_name
FROM employees
WHERE department_id IN (1, 2, 3);

-- LIKE (pattern matching)
SELECT first_name, last_name
FROM employees
WHERE first_name LIKE 'J%';  -- Matches any name starting with J

-- IS NULL
SELECT first_name, last_name
FROM employees
WHERE middle_name IS NULL;
```

**Activity**:

* Have learners practice writing queries using `BETWEEN`, `IN`, and `LIKE` to retrieve specific records from the database.

---

### **4. Sorting Results with `ORDER BY` (15 minutes)**

* **Objective**: Show learners how to sort query results based on one or more columns.
* **Overview**:

  * **`ORDER BY`**: Used to sort query results in ascending (default) or descending order.
  * Sorting can be applied to one or multiple columns.

**Examples**:

```sql
-- Sorting by salary in ascending order
SELECT first_name, last_name, salary
FROM employees
ORDER BY salary;

-- Sorting by salary in descending order
SELECT first_name, last_name, salary
FROM employees
ORDER BY salary DESC;

-- Sorting by multiple columns
SELECT first_name, last_name, department_id, hire_date
FROM employees
ORDER BY department_id ASC, hire_date DESC;
```

**Activity**:

* Have learners practice sorting query results based on one or more columns (e.g., sorting employees by department and hire date).

---

### **5. Limiting Results with `LIMIT` (10 minutes)**

* **Objective**: Introduce the `LIMIT` clause to restrict the number of records returned by a query.
* **Overview**:

  * **`LIMIT`**: Restricts the result set to a specified number of rows.

**Example**:

```sql
SELECT first_name, last_name, salary
FROM employees
ORDER BY salary DESC
LIMIT 5;
```

This query retrieves the top 5 highest-paid employees.

**Activity**:

* Have learners write queries to retrieve a limited number of records (e.g., top 10 employees by salary).

---

### **6. Hands-On Lab: Filtering and Sorting Data (30 minutes)**

* **Objective**: Provide learners with hands-on practice writing queries that filter, sort, and limit results.
* **Lab Tasks**:

  1. Write a query to find all employees with a salary greater than 50,000 and who were hired before 2015.
  2. Write a query to find employees who belong to either department 1 or department 2.
  3. Write a query to list all employees whose names start with the letter ‘J’.
  4. Write a query to get the top 10 highest-paid employees in the company.
  5. Write a query to sort employees by hire date in descending order and then by last name in ascending order.

**Delivery Tip**:

* Circulate and assist learners with any challenges they face. Emphasize the importance of writing clean and readable SQL queries.

---

### **7. Review and Q&A (10 minutes)**

* **Objective**: Summarize the key points and answer any remaining questions.
* **Overview**:

  * **Key Concepts**:

    * Use of logical and comparison operators.
    * Filtering with `AND`, `OR`, `NOT`, and advanced comparison operators like `BETWEEN`, `IN`, and `LIKE`.
    * Sorting results with `ORDER BY` and limiting results with `LIMIT`.
  * **Q&A**: Open the floor for questions. Address any points of confusion or challenges learners encountered during the lab.

---

### **8. Wrap-Up and Next Steps (5 minutes)**

* **Objective**: Provide a preview of the next day’s lesson and wrap up the session.
* **Overview**:

  * **Key Concepts Covered**:

    * Logical operators: `AND`, `OR`, `NOT`.
    * Comparison operators: `=`, `>`, `<`, `BETWEEN`, `IN`, `LIKE`.
    * Sorting with `ORDER BY` and limiting results with `LIMIT`.
  * **What’s Next**: Tomorrow, we will dive into **Joining Tables** and explore how to work with multiple tables in a database.

---

## **Materials for Learners**

1. **MySQL Sample Database**: Use the same database as Day 1 (e.g., `sakila` or `employees`).
2. **SQL Query Reference**: Provide learners with a cheat sheet containing common operators and SQL clauses (`WHERE`, `AND`, `OR`, `BETWEEN`, `IN`, `LIKE`, `ORDER BY`, `LIMIT`).
3. **Exercises**: A set of practice queries for filtering, sorting, and limiting data.

---

## **Practical Tips for Trainers**

* **Engage Learners**: Ask questions throughout the lesson to keep learners engaged (e.g., "What happens if we change the `AND` operator to `OR`?").
* **Encourage Experimentation**: Have learners try different variations of queries on their own, especially when using `LIKE` and `IN`.
* **Provide Real-World Examples**: Use relatable examples, such as finding employees with specific job titles, within a certain salary range, or working in specific departments.
* **Check for Errors**: Remind learners to check for common SQL syntax issues, such as missing semicolons or incorrect column names.
