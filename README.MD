# **MySQL 1-Week Hands-On Crash Course**

## **Day 1: Introduction & Setup**

**Objective:** Understand MySQL basics and set up your environment.
**Topics:**

* What is a database & why MySQL?
* Relational vs. non-relational databases
* Installing MySQL & MySQL Workbench
* MySQL CLI basics
* Creating your first database
  **Mini Project:**
* Create a database called `company_db`
* Explore the database structure using `SHOW DATABASES` and `SHOW TABLES`

---

## **Day 2: Creating Tables & Understanding Data Types**

**Objective:** Learn table creation and column data types.
**Topics:**

* `CREATE TABLE` syntax
* Common data types: `INT`, `VARCHAR`, `DATE`, `FLOAT`, `BOOLEAN`
* Primary keys & auto-increment
* Nullable vs NOT NULL columns
* Modifying tables with `ALTER TABLE`
  **Mini Project:**
* Create a `employees` table with:

  * `id` (PK, auto-increment)
  * `name` (VARCHAR)
  * `email` (VARCHAR)
  * `hire_date` (DATE)
  * `salary` (FLOAT)
* Alter the table to add a `department` column

---

## **Day 3: CRUD Operations**

**Objective:** Manipulate and query data effectively.
**Topics:**

* Inserting data: `INSERT INTO`
* Reading data: `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`
* Updating data: `UPDATE`
* Deleting data: `DELETE`
* Filtering with operators: `=`, `<`, `>`, `LIKE`, `IN`, `BETWEEN`
  **Mini Project:**
* Insert 5–10 sample employees into `employees`
* Query employees with salary > 50,000
* Update the department for a specific employee
* Delete an employee by `id`

---

## **Day 4: Relationships & Joins**

**Objective:** Learn relationships between tables and joining data.
**Topics:**

* Primary & foreign keys
* One-to-many relationships
* Joining tables: `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`
* Aggregate functions: `COUNT`, `SUM`, `AVG`, `MAX`, `MIN`
* `GROUP BY` and `HAVING`
  **Mini Project:**
* Create a `projects` table with:

  * `id` (PK)
  * `employee_id` (FK → employees.id)
  * `project_name`
  * `start_date`, `end_date`
* Write queries to:

  * List all projects with employee names
  * Count the number of projects per employee

---

## **Day 5: Subqueries & Views**

**Objective:** Learn advanced queries and reusable views.
**Topics:**

* Subqueries in `SELECT`, `FROM`, and `WHERE`
* Creating views: `CREATE VIEW`
* Using views in queries
  **Mini Project:**
* Create a view `employee_project_count` showing each employee and their number of projects
* Write a query to list employees working on more than 2 projects using the view

---

## **Day 6: Indexing & Transactions**

**Objective:** Optimize queries and work with transactions.
**Topics:**

* Creating indexes for faster queries
* Using `EXPLAIN` to check query performance
* Transactions: `START TRANSACTION`, `COMMIT`, `ROLLBACK`
  **Mini Project:**
* Add an index on `email` in `employees`
* Simulate a transaction: Update salary for 2 employees, then roll it back to verify

---

## **Day 7: Mini Capstone Project**

**Objective:** Apply everything learned in a real-world scenario.
**Project:** **Employee Management System**

* Database: `company_db`
* Tables: `employees`, `projects`, `departments`
* Tasks:

  * Create tables with appropriate keys & data types
  * Insert sample data
  * Write queries to:

    * List employees by department
    * Find employees without projects
    * Count total salary per department
    * Create a view showing employees and project counts
* Optional: Practice a transaction updating salaries and project assignments

