# **Lesson Plan - Day 1: Introduction to MySQL**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 1

---

## **Learning Objectives**

By the end of the lesson, learners will be able to:

1. **Understand the basics of relational databases and MySQL**.
2. **Navigate and interact with MySQL using command-line interface (CLI)**.
3. **Write basic SQL queries** to retrieve data from a MySQL database.
4. **Execute simple SELECT queries** to retrieve records from a database table.
5. **Use basic filtering techniques** with the `WHERE` clause.

---

## **Materials Needed**

* Computer with MySQL installed or access to a MySQL server.
* A MySQL database (use a sample database like `sakila` or `employees`).
* Text editor for SQL queries (or MySQL Workbench, if preferred).

---

## **Agenda**

### **1. Introduction to MySQL and Relational Databases (15 minutes)**

* **Objective**: Introduce MySQL, relational databases, and SQL.
* **Overview**: Explain what MySQL is, its role as a relational database management system (RDBMS), and its relationship with SQL.

  * **What is MySQL?**

    * A popular open-source RDBMS used to manage and store data.
  * **What is SQL?**

    * Structured Query Language (SQL) is used to interact with relational databases.
  * **What is a relational database?**

    * A database that stores data in tables, which are related to one another via foreign keys.

**Discussion Points**:

* Why MySQL is widely used in web development.
* The difference between MySQL and other databases (e.g., PostgreSQL, Oracle).

**Delivery Tip**: Keep it high-level and provide relatable examples (e.g., MySQL for websites, e-commerce platforms, etc.).

---

### **2. Setting Up MySQL (15 minutes)**

* **Objective**: Ensure learners can access and interact with MySQL.
* **Overview**: Show how to access MySQL from the command line or through MySQL Workbench.

  * **Starting MySQL Server**:

    * If running locally: `mysql -u root -p`
    * If using MySQL Workbench: Open MySQL Workbench and connect to the local or remote server.
  * **Basic MySQL Commands**:

    * `SHOW DATABASES;` – List available databases.
    * `USE <database_name>;` – Select the database to work with.
    * `SHOW TABLES;` – List tables in the selected database.

**Activity**:

* Have learners connect to MySQL and list databases and tables.

---

### **3. Introduction to SQL Queries (20 minutes)**

* **Objective**: Teach learners to write basic SQL queries to retrieve data.
* **Overview**: Explain the basic structure of a SQL query:

  * **`SELECT`**: Used to retrieve data from one or more tables.
  * **`FROM`**: Specifies the table from which to retrieve data.
  * **`WHERE`**: Filters the data based on conditions.

**Example**:

```sql
SELECT * FROM employees;
```

This query retrieves all columns from the `employees` table.

**Delivery Tip**: Walk through each clause and its purpose. Start with simple queries like retrieving all data from a table.

---

### **4. Filtering Data with the `WHERE` Clause (20 minutes)**

* **Objective**: Introduce filtering with the `WHERE` clause.
* **Overview**: The `WHERE` clause is used to filter data based on a condition (e.g., retrieving records where the salary is greater than $50,000).

**Example**:

```sql
SELECT first_name, last_name, salary
FROM employees
WHERE salary > 50000;
```

This query retrieves the first name, last name, and salary of employees who earn more than $50,000.

**Activity**:

* Have learners write queries to filter data based on different conditions (e.g., retrieving employees from a specific department or salary range).

---

### **5. Hands-On Lab: Writing Simple Queries (30 minutes)**

* **Objective**: Provide learners with hands-on practice writing basic SQL queries.
* **Overview**: Learners will execute various SQL queries to retrieve data from the sample database.

  * Query 1: Retrieve all columns from the `employees` table.
  * Query 2: Retrieve the first name, last name, and salary of employees who earn more than $60,000.
  * Query 3: Retrieve all employees from the `employees` table whose `hire_date` is before '2010-01-01'.
  * Query 4: Retrieve the first name and department of employees from a specific department.

**Activity**:

* Provide learners with a set of SQL query tasks. Walk around the room and assist as needed.

---

### **6. Review and Q&A (10 minutes)**

* **Objective**: Address any questions or challenges that arose during the hands-on exercises.
* **Overview**: Review the key points from the lesson:

  * **SELECT** and **FROM** are used to retrieve data from tables.
  * **WHERE** is used to filter records based on specific conditions.
* **Q&A**: Allow learners to ask questions. Provide clarifications as needed.

**Delivery Tip**: Use common queries from the lab exercises to help clarify concepts.

---

### **7. Wrap-up and Next Steps (5 minutes)**

* **Objective**: Summarize the day’s learning and introduce the next session.
* **Overview**:

  * **Key Concepts Covered**:

    * Introduction to MySQL and relational databases.
    * Writing basic SQL queries to retrieve data.
    * Filtering data with the `WHERE` clause.
  * **What’s Next**: Tomorrow, we will explore **Sorting and Joining Data** to manipulate query results and work with multiple tables.

---

## **Materials for Learners**

1. **MySQL Sample Database**: You can use a sample database like `sakila` or `employees`.
2. **SQL Query Reference**: Provide learners with a cheat sheet containing common SQL commands (e.g., `SELECT`, `FROM`, `WHERE`, `ORDER BY`).
3. **Exercises**: A set of hands-on exercises that guide them through querying a sample database.

---

## **Practical Tips for Trainers**

* **Engage learners with examples**: Use real-world examples, like querying employees, products, or sales data, to keep the material relatable.
* **Give clear instructions**: Ensure that learners understand how to access MySQL, select a database, and execute basic queries.
* **Hands-on practice is key**: Ensure that learners spend a significant amount of time executing queries themselves.
* **Clarify errors**: Be prepared to help learners troubleshoot common SQL errors, such as typos or missing semicolons.

---

### **Conclusion**

Day 1 focuses on introducing MySQL, setting up the environment, and covering basic SQL query syntax. By the end of the session, learners will be familiar with writing basic `SELECT` queries and using the `WHERE` clause to filter data. This sets the foundation for more advanced topics like data sorting, joining tables, and advanced filtering.

