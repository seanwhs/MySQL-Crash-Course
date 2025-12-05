# **Day 2 – README.md**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 2
**Topic:** Tables & Data Types
**Duration:** 2–3 hours

---

## **Welcome to Day 2**

Welcome back! In Day 2, we will start working with **tables** in MySQL, which are the fundamental structure for storing data in a relational database. You will also learn about **data types**, which define what kind of data each column in your tables can store.

By the end of Day 2, you will be able to:

* Understand what tables are and why they are important
* Create tables with different data types
* Use primary keys and auto-increment for unique identification
* Modify tables using `ALTER TABLE`
* Work with constraints to ensure data integrity

---

## **Pre-requisites**

Before starting Day 2, ensure that:

* You have completed Day 1’s setup tasks (MySQL installed, database created, and connected via CLI/Workbench).
* You understand the basic commands (`CREATE DATABASE`, `USE`, `SHOW DATABASES`, `SHOW TABLES`).

---

## **Day 2 Outline**

1. **Introduction to Tables**

   * What is a table?
   * Table structure: Columns, Rows, and Data Types

2. **Data Types in MySQL**

   * Numeric types: `INT`, `FLOAT`, `DECIMAL`
   * String types: `VARCHAR`, `TEXT`
   * Date/Time types: `DATE`, `DATETIME`, `TIMESTAMP`
   * Boolean: `BOOLEAN`

3. **Creating Tables**

   * `CREATE TABLE` syntax
   * Primary Key and Auto-Increment
   * Adding Constraints: `NOT NULL`, `UNIQUE`, `DEFAULT`

4. **Altering Tables**

   * Adding, modifying, and deleting columns with `ALTER TABLE`
   * Managing table structure

5. **Mini Project**

   * Create a `users` table with appropriate data types, primary key, and constraints
   * Add a `created_at` column using `DATETIME` type

---

## **Getting Started**

### **Step 1: What is a Table?**

In MySQL, a **table** is a collection of rows and columns used to store data. Each row represents a unique record, and each column stores a particular type of data about that record.

For example, in a table called `users`, each row could represent a user, and columns might include `id`, `name`, `email`, and `created_at`.

---

### **Step 2: Data Types in MySQL**

* **Numeric Types**

  * `INT`: Stores integers, commonly used for IDs
  * `FLOAT`, `DECIMAL`: Used for floating-point and fixed-point numbers

* **String Types**

  * `VARCHAR`: Variable-length string, used for names, emails, etc.
  * `TEXT`: Used for longer text data like descriptions

* **Date and Time Types**

  * `DATE`: Stores date in `YYYY-MM-DD` format
  * `DATETIME`: Stores date and time in `YYYY-MM-DD HH:MM:SS` format
  * `TIMESTAMP`: Automatically stores the current time when a record is created or modified

* **Boolean Type**

  * `BOOLEAN`: Stores `TRUE` or `FALSE` values

---

### **Step 3: Creating Tables**

To create a table, we use the `CREATE TABLE` statement. Here’s a basic example:

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

* **`id`**: `INT` type with `AUTO_INCREMENT` to automatically generate unique IDs for each user.
* **`name`**: `VARCHAR(100)` to store up to 100 characters.
* **`email`**: `VARCHAR(100)` with the `UNIQUE` constraint to ensure no two users have the same email.
* **`created_at`**: `DATETIME` type with a default value of the current timestamp.

---

### **Step 4: Altering Tables**

You can modify an existing table with the `ALTER TABLE` command:

```sql
ALTER TABLE users ADD COLUMN status VARCHAR(50) DEFAULT 'active';
```

* Adds a new column `status` to the `users` table with a default value of `'active'`.

You can also modify existing columns, delete columns, or change column types using `ALTER TABLE`.

---

### **Step 5: Mini Project**

**Task:** Create a `users` table with the following columns:

* `id` (INT, primary key, auto-increment)
* `name` (VARCHAR(100))
* `email` (VARCHAR(100), unique)
* `created_at` (DATETIME, default `CURRENT_TIMESTAMP`)

Then, add a column for `status` (VARCHAR, default 'active').

---

## **Suggested Reading**

* [MySQL Data Types Documentation](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)
* [MySQL CREATE TABLE Syntax](https://dev.mysql.com/doc/refman/8.0/en/create-table.html)

---

## **Mini Project**

**Create a `users` table with the following structure:**

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    status VARCHAR(50) DEFAULT 'active'
);
```

Verify the table structure with:

```sql
DESCRIBE users;
```

This project gives you hands-on experience in structuring data, applying constraints, and managing your database schema.

---

## **Next Steps**

Tomorrow, we’ll dive into **CRUD operations** (Create, Read, Update, Delete) and learn how to manipulate the data in your tables. Be ready to apply what you learned about tables and data types to manage real-world data!

