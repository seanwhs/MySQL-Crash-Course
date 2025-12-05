# **Day 2 – Lab: Tables & Data Types**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 2
**Topic:** Tables & Data Types
**Duration:** 1–2 hours
**Objective:** Create and modify tables, apply constraints, and work with different data types in MySQL.

---

## **Lab Setup**

Before starting the lab:

1. Ensure that MySQL Server and MySQL Workbench are already installed and running.
2. Make sure that you are connected to MySQL via either the command-line interface (CLI) or MySQL Workbench.
3. Use the `company_db` database created in Day 1 or create a new database for this session.

---

## **Exercise 1: Create the `users` Table**

**Objective:** Create a table called `users` with the following columns:

* `id`: INT, primary key, auto-increment
* `name`: VARCHAR(100), NOT NULL
* `email`: VARCHAR(100), UNIQUE
* `created_at`: DATETIME, default `CURRENT_TIMESTAMP`
* `status`: VARCHAR(50), default `'active'`

**Steps:**

1. Write the SQL command to create the `users` table.
2. Execute the command in both CLI and Workbench.

**SQL Command Example:**

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    status VARCHAR(50) DEFAULT 'active'
);
```

**Verify:**

* Use `DESCRIBE users;` to verify the table structure.
* Check that all columns are present with the correct data types and constraints.

**Expected Outcome:**

* A table named `users` should be created with the correct columns and constraints.

---

## **Exercise 2: Insert Data into the `users` Table**

**Objective:** Insert a few rows of sample data into the `users` table.

**Steps:**

1. Write the `INSERT INTO` SQL command to add at least 3 records to the `users` table. Include values for `name`, `email`, and `status`.
2. Leave `created_at` to take the default value (it should automatically use the current timestamp).
3. Execute the `INSERT` command in CLI or Workbench.

**SQL Command Example:**

```sql
INSERT INTO users (name, email, status)  
VALUES 
    ('John Doe', 'john.doe@example.com', 'active'),  
    ('Jane Smith', 'jane.smith@example.com', 'inactive'),  
    ('Alice Johnson', 'alice.johnson@example.com', 'active');
```

**Verify:**

* Use `SELECT * FROM users;` to view the inserted data.
* Ensure the `created_at` column is populated with the current timestamp.

**Expected Outcome:**

* Three rows should be added to the `users` table with the correct data.

---

## **Exercise 3: Alter the `users` Table**

**Objective:** Modify the `users` table to add a new column and change an existing column.

**Steps:**

1. Use the `ALTER TABLE` command to add a new column called `phone_number` (VARCHAR(15), allowing NULL values).
2. Modify the `status` column to make it a `NOT NULL` field (default value is still `'active'`).

**SQL Commands Example:**

```sql
ALTER TABLE users ADD COLUMN phone_number VARCHAR(15) NULL;
ALTER TABLE users MODIFY COLUMN status VARCHAR(50) NOT NULL DEFAULT 'active';
```

**Verify:**

* Use `DESCRIBE users;` again to ensure the table structure reflects these changes.

**Expected Outcome:**

* The `phone_number` column should be added, and the `status` column should no longer accept `NULL` values.

---

## **Exercise 4: Drop a Column from the `users` Table**

**Objective:** Remove a column from the `users` table.

**Steps:**

1. Use the `ALTER TABLE` command to drop the `phone_number` column.
2. Execute the command in your MySQL session.

**SQL Command Example:**

```sql
ALTER TABLE users DROP COLUMN phone_number;
```

**Verify:**

* Use `DESCRIBE users;` to confirm that the `phone_number` column has been removed.

**Expected Outcome:**

* The `phone_number` column should be removed from the `users` table.

---

## **Exercise 5: Work with Data Integrity Constraints**

**Objective:** Add constraints to ensure data integrity and prevent invalid data.

**Steps:**

1. Create a new table called `employees` with the following columns:

   * `id`: INT, primary key, auto-increment
   * `name`: VARCHAR(100), NOT NULL
   * `email`: VARCHAR(100), UNIQUE, NOT NULL
   * `hire_date`: DATE, NOT NULL
   * `salary`: DECIMAL(10, 2), NOT NULL, default value `50000`

2. Insert a few rows of data into the `employees` table. Make sure:

   * The `salary` column defaults to `50000` if no value is provided.
   * The `email` column does not accept duplicates.

**SQL Commands Example:**

```sql
CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    hire_date DATE NOT NULL,
    salary DECIMAL(10, 2) NOT NULL DEFAULT 50000
);

INSERT INTO employees (name, email, hire_date) 
VALUES 
    ('Mark Turner', 'mark.turner@example.com', '2023-06-15'),
    ('Lucy Brown', 'lucy.brown@example.com', '2023-07-01');
```

**Verify:**

* Use `SELECT * FROM employees;` to view the data.
* Attempt to insert a duplicate email (it should fail).

**Expected Outcome:**

* The `employees` table should be created with the correct data and constraints.
* Duplicates in the `email` column should not be allowed.

---

## **Optional Challenge**

* Try altering the `employees` table to add a `department` column.
* Insert more data with different departments (e.g., "Sales", "Engineering") and ensure each employee is assigned a department.
* Use `ALTER TABLE` to make the `department` column `NOT NULL`.

---

## **Lab Completion Checklist**

* [ ] Created the `users` table with constraints
* [ ] Inserted sample data into the `users` table
* [ ] Altered the `users` table to add and modify columns
* [ ] Dropped the `phone_number` column
* [ ] Created the `employees` table with constraints
* [ ] Inserted sample employee data and ensured data integrity

---

This lab reinforces the concepts learned about tables, constraints, and data types from Day 2. Learners will get hands-on experience with the key tasks involved in creating, modifying, and maintaining tables in MySQL.

