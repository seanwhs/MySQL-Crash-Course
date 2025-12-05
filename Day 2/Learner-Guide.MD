# **Day 2 – Learner Guide**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 2
**Topic:** Tables & Data Types
**Duration:** 1.5–2 hours

---

## **Welcome to Day 2**

Welcome back to Day 2! Today, we will dive into **Tables & Data Types** in MySQL, the backbone of how data is stored in relational databases. You will learn how to create tables, define columns with specific data types, and apply constraints to ensure data integrity.

By the end of this session, you will be able to:

* Create tables using various data types
* Apply constraints like `PRIMARY KEY`, `NOT NULL`, `UNIQUE`, and `DEFAULT`
* Modify tables using `ALTER TABLE`
* Use `CREATE TABLE` to structure data effectively

---

## **Before You Begin**

1. Ensure that MySQL is installed and running on your machine.
2. Ensure you are connected to your MySQL server using either the **MySQL Command Line Interface (CLI)** or **MySQL Workbench**.
3. If you did not already create a `company_db` database in Day 1, please create a new one using the following command:

```sql
CREATE DATABASE company_db;
USE company_db;
```

---

## **Exercise 1: Create the `users` Table**

### **Objective:**

Create a table called `users` with the following columns:

* `id`: INT, primary key, auto-increment
* `name`: VARCHAR(100), NOT NULL
* `email`: VARCHAR(100), UNIQUE
* `created_at`: DATETIME, default `CURRENT_TIMESTAMP`
* `status`: VARCHAR(50), default `'active'`

### **Steps:**

1. Write the `CREATE TABLE` SQL command to create the `users` table.
2. Execute the command using either CLI or Workbench.
3. Verify the table structure by running `DESCRIBE users;`.

### **SQL Command Example:**

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    status VARCHAR(50) DEFAULT 'active'
);
```

**What You Should See:**

* The `users` table should be created with the correct columns and constraints.
* The `id` column will automatically increment with each new record.
* The `status` column will default to `'active'`.

---

## **Exercise 2: Insert Data into the `users` Table**

### **Objective:**

Insert sample data into the `users` table. Ensure that the `created_at` column uses the default timestamp value.

### **Steps:**

1. Write the `INSERT INTO` SQL command to insert at least 3 records into the `users` table.
2. Execute the command in either CLI or Workbench.
3. Use `SELECT * FROM users;` to verify that the records have been inserted correctly.

### **SQL Command Example:**

```sql
INSERT INTO users (name, email, status) 
VALUES 
    ('John Doe', 'john.doe@example.com', 'active'),
    ('Jane Smith', 'jane.smith@example.com', 'inactive'),
    ('Alice Johnson', 'alice.johnson@example.com', 'active');
```

**What You Should See:**

* Three records should be inserted into the `users` table.
* The `created_at` column should automatically populate with the current timestamp.

---

## **Exercise 3: Alter the `users` Table**

### **Objective:**

Modify the `users` table by adding a new column and modifying an existing one.

### **Steps:**

1. Use the `ALTER TABLE` command to add a new column called `phone_number` (VARCHAR(15)). This column should allow `NULL` values.
2. Modify the `status` column to ensure that it cannot be `NULL` by setting it to `NOT NULL`. The default value should remain `'active'`.
3. Verify the changes using the `DESCRIBE users;` command.

### **SQL Command Example:**

```sql
ALTER TABLE users ADD COLUMN phone_number VARCHAR(15) NULL;
ALTER TABLE users MODIFY COLUMN status VARCHAR(50) NOT NULL DEFAULT 'active';
```

**What You Should See:**

* A new column `phone_number` should be added.
* The `status` column should be `NOT NULL`, with a default value of `'active'`.

---

## **Exercise 4: Drop a Column from the `users` Table**

### **Objective:**

Remove the `phone_number` column from the `users` table.

### **Steps:**

1. Use the `ALTER TABLE` command to drop the `phone_number` column from the `users` table.
2. Run `DESCRIBE users;` to confirm that the column has been removed.

### **SQL Command Example:**

```sql
ALTER TABLE users DROP COLUMN phone_number;
```

**What You Should See:**

* The `phone_number` column should be removed from the `users` table.

---

## **Exercise 5: Data Integrity with Constraints**

### **Objective:**

Create a new table called `employees` with constraints to ensure data integrity.

### **Steps:**

1. Write the `CREATE TABLE` SQL command to create the `employees` table with the following columns:

   * `id`: INT, primary key, auto-increment
   * `name`: VARCHAR(100), NOT NULL
   * `email`: VARCHAR(100), UNIQUE, NOT NULL
   * `hire_date`: DATE, NOT NULL
   * `salary`: DECIMAL(10, 2), NOT NULL, default value `50000`
2. Insert a few rows of data into the `employees` table.
3. Verify that the `email` column does not allow duplicates and that the `salary` column defaults to `50000` if no value is provided.

### **SQL Command Example:**

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

**What You Should See:**

* The `employees` table should be created with the correct constraints.
* The `salary` column should default to `50000` if no value is provided.
* Duplicates in the `email` column should be prevented.

---

## **Optional Challenge: Alter the `employees` Table**

### **Objective:**

Alter the `employees` table to add a `department` column and assign employees to different departments.

### **Steps:**

1. Use the `ALTER TABLE` command to add a `department` column (VARCHAR(50)).
2. Insert new rows with department values such as `Sales`, `Engineering`, and `Marketing`.
3. Use `ALTER TABLE` to set the `department` column as `NOT NULL`.

### **SQL Command Example:**

```sql
ALTER TABLE employees ADD COLUMN department VARCHAR(50);
UPDATE employees SET department = 'Sales' WHERE name = 'Mark Turner';
UPDATE employees SET department = 'Engineering' WHERE name = 'Lucy Brown';
ALTER TABLE employees MODIFY COLUMN department VARCHAR(50) NOT NULL;
```

**What You Should See:**

* The `department` column should be added and populated with values for each employee.
* The `department` column should be `NOT NULL` after modification.

---

## **Lab Completion Checklist**

* [ ] Created the `users` table with proper constraints
* [ ] Inserted sample data into the `users` table
* [ ] Altered the `users` table to add and modify columns
* [ ] Dropped the `phone_number` column
* [ ] Created the `employees` table with constraints and inserted sample data

---

## **Reflection Questions**

1. What is the purpose of using `AUTO_INCREMENT` in a table?
2. How does the `NOT NULL` constraint affect a column?
3. What happens if you try to insert duplicate values into a `UNIQUE` column?
4. Why is it important to define data types when creating columns in MySQL?

---

This **Learner Guide** provides learners with detailed instructions on how to complete the Day 2 lab exercises, while reinforcing key concepts like table creation, data types, constraints, and modifying tables.

