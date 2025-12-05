# **Day 2 – Slide Deck: Tables & Data Types**

---

## **Slide 1: Title Slide**

**Title:** MySQL 1-Week Hands-On Crash Course – Day 2
**Subtitle:** Tables & Data Types
**Visuals:** MySQL logo, table icon
**Speaker Notes:**

* Welcome the learners back
* Introduce the focus of Day 2: Creating and managing tables, working with data types

---

## **Slide 2: Learning Objectives**

**Content:**
By the end of Day 2, you will be able to:

* Understand tables in MySQL
* Create tables using different data types
* Use primary keys, auto-increment, and constraints
* Modify tables with `ALTER TABLE`
  **Visuals:** Checklist icons or bullet points
  **Speaker Notes:**
* Emphasize that today is hands-on and learners will work directly with data

---

## **Slide 3: What is a Table in MySQL?**

**Content:**

* A **table** is a collection of rows and columns used to store data in a relational database
* Tables consist of columns that hold specific data types and rows that represent individual records
* The primary structure for storing data in MySQL
  **Visuals:** Diagram of a table with columns (`id`, `name`, `email`) and rows (data records)
  **Speaker Notes:**
* Describe how each row is a record, and each column is a field or attribute of that record (e.g., "Name", "Email")

---

## **Slide 4: Data Types in MySQL**

**Content:**
**Numeric Types:**

* `INT`: Integer numbers
* `FLOAT`, `DECIMAL`: Floating-point and fixed-point numbers

**String Types:**

* `VARCHAR`: Variable-length string
* `TEXT`: Long text

**Date and Time Types:**

* `DATE`: Store dates
* `DATETIME`: Store both date and time
* `TIMESTAMP`: Automatically stores current time when record is created or modified

**Boolean Type:**

* `BOOLEAN`: Stores `TRUE` or `FALSE` values

**Visuals:** Table showing examples of each data type (e.g., `INT`, `VARCHAR(100)`, `DATETIME`)
**Speaker Notes:**

* Provide real-world examples for each data type (e.g., `INT` for user IDs, `VARCHAR` for email addresses)

---

## **Slide 5: Creating a Table – Basic Syntax**

**Content:**

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);
```

**Example:**

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

**Visuals:** Screenshot of MySQL Workbench showing the code above in the query window
**Speaker Notes:**

* Walk through the SQL syntax for creating a table
* Highlight the use of `PRIMARY KEY`, `AUTO_INCREMENT`, `DEFAULT`

---

## **Slide 6: Key Concepts in Table Creation**

**Content:**

* **Primary Key**: Uniquely identifies each record
* **Auto Increment**: Automatically assigns a unique number to a column (e.g., `id`)
* **Constraints**: Rules for data (e.g., `UNIQUE`, `NOT NULL`, `DEFAULT`)

**Visuals:** Diagram showing a table with highlighted columns: `id` (primary key), `name`, `email`, `created_at`
**Speaker Notes:**

* Explain the role of primary keys in ensuring each row is uniquely identifiable
* Discuss how constraints ensure data integrity

---

## **Slide 7: Altering Tables**

**Content:**
To modify an existing table:

```sql
ALTER TABLE table_name ADD COLUMN new_column datatype;
ALTER TABLE table_name MODIFY COLUMN column_name new_datatype;
ALTER TABLE table_name DROP COLUMN column_name;
```

**Example:**

```sql
ALTER TABLE users ADD COLUMN status VARCHAR(50) DEFAULT 'active';
```

**Visuals:** Screenshot showing the `ALTER TABLE` query execution in MySQL Workbench
**Speaker Notes:**

* Walk through the `ALTER TABLE` syntax
* Explain how to add, modify, or remove columns from an existing table

---

## **Slide 8: Mini Project**

**Content:**

* **Task:** Create a `users` table with:

  * `id` (INT, primary key, auto-increment)
  * `name` (VARCHAR(100))
  * `email` (VARCHAR(100), unique)
  * `created_at` (DATETIME, default current timestamp)
  * `status` (VARCHAR(50), default 'active')

**Visuals:** Checklist or icons representing each step of the table creation process
**Speaker Notes:**

* Emphasize that this is a hands-on project to help learners apply what they’ve learned so far
* Suggest they verify their work using `DESCRIBE users;`

---

## **Slide 9: Data Integrity with Constraints**

**Content:**

* **NOT NULL**: Ensures that a column cannot have a `NULL` value
* **UNIQUE**: Ensures all values in a column are distinct
* **DEFAULT**: Sets a default value for a column if no value is provided

**Example:**

```sql
CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    hire_date DATE NOT NULL,
    salary DECIMAL(10, 2) DEFAULT 50000
);
```

**Visuals:** Diagram showing constraints applied to a table
**Speaker Notes:**

* Discuss how constraints help maintain data quality
* Show how these constraints prevent common errors, like duplicate emails

---

## **Slide 10: Next Steps**

**Content:**

* Tomorrow: **CRUD Operations** (Create, Read, Update, Delete)
* You will learn how to insert data into tables, retrieve it, and update or delete records

**Visuals:** Calendar icon or Day 3 reminder
**Speaker Notes:**

* Encourage learners to practice table creation on their own
* Reinforce that Day 2 sets the foundation for manipulating data

---

## **Slide 11: Summary & Q&A**

**Content:**

* **Recap of Day 2 Topics:**

  * Tables and Data Types
  * Creating Tables and Adding Constraints
  * Altering Tables

**Visuals:** Key points summarizing the day
**Speaker Notes:**

* Open the floor for any questions or clarifications
* Reinforce that Day 2 was all about structuring data in MySQL

---

This slide deck provides a structured and engaging way to present the concepts and exercises of **Day 2**. Each slide is paired with practical demos and key discussion points to help learners understand the role of tables and data types in MySQL.

