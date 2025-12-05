# **Day 6: Database Indexing and Query Optimization**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 6
**Topic**: Database Indexing & Query Optimization

---

## **Overview**

In this session, learners will explore the importance of **database indexing** and how it affects query performance. Understanding indexing and how to optimize queries is critical when working with large datasets. We will cover:

* **What are indexes?**
* **Types of indexes in MySQL**
* **How to create, modify, and drop indexes**
* **Understanding query performance and how to analyze it**
* **Optimizing queries with `EXPLAIN`**

By the end of Day 6, learners will have the knowledge and hands-on experience to significantly improve the performance of their SQL queries.

---

## **Learning Objectives**

By the end of this lesson, learners will be able to:

1. **Understand the concept of indexes** and how they improve query performance.
2. **Create and manage indexes** on tables in MySQL.
3. **Analyze query execution plans** using the `EXPLAIN` keyword to identify performance bottlenecks.
4. **Optimize queries** by understanding which indexes to create and how to use them effectively.
5. **Implement best practices for query optimization** in MySQL.

---

## **Key Topics**

### **1. What Are Indexes?**

* **Definition**: An **index** is a data structure that helps improve the speed of data retrieval operations on a database table at the cost of additional space and time for updates (inserts, deletes, and updates).
* **How It Works**: An index works like the index in a book. It allows the database to quickly locate rows matching a given condition without scanning the entire table.
* **Why Use Indexes?**

  * Improves query performance, especially for `SELECT` queries.
  * Speeds up search, join, and sort operations.
  * Reduces I/O operations and database load.

### **2. Types of Indexes in MySQL**

* **Primary Key Index**: Automatically created when a `PRIMARY KEY` is defined on a column. Ensures that values in the column are unique.
* **Unique Index**: Ensures that no two rows in a table have the same value in the indexed column(s).
* **Full-Text Index**: Used for full-text searches in MySQL, useful for text-heavy fields.
* **Composite Index**: An index on multiple columns, used when queries frequently filter based on multiple columns.
* **Foreign Key Index**: Automatically created when a foreign key is defined. Helps improve performance when joining tables on foreign keys.

### **3. Creating and Managing Indexes**

* **Creating an Index**:

  * Syntax:

  ```sql
  CREATE INDEX index_name ON table_name (column_name);
  ```
* **Creating a Composite Index**:

  * Syntax:

  ```sql
  CREATE INDEX index_name ON table_name (column1, column2);
  ```
* **Dropping an Index**:

  * Syntax:

  ```sql
  DROP INDEX index_name ON table_name;
  ```

### **4. Query Performance Analysis**

* **The `EXPLAIN` Keyword**:

  * The `EXPLAIN` keyword provides insight into how MySQL executes a query, including which indexes are used and the query execution plan.
  * Example:

  ```sql
  EXPLAIN SELECT * FROM employees WHERE department_id = 3;
  ```

  * **What It Shows**: The output provides a detailed plan, showing which indexes are used, how tables are joined, and the order of execution.

### **5. Optimizing Queries**

* **Using Indexes to Optimize Queries**:

  * Indexes help optimize `WHERE`, `JOIN`, and `ORDER BY` operations.
  * Common practices for optimization:

    * **Use Indexes on Columns that are Frequently Queried**.
    * **Limit the Number of Columns in the Index**: Indexing too many columns can degrade performance.
    * **Avoid using indexes for low-cardinality columns** (e.g., boolean or small integer columns).
  * **Avoid Redundant Indexes**: MySQL only needs one index on a column for most queries.

### **6. Best Practices for Indexing and Optimization**

* **Indexing**:

  * Use indexes on columns that are frequently used in search conditions (`WHERE`), as join conditions (`ON`), and in sorting (`ORDER BY`).
  * Keep the number of indexes reasonable to balance performance and storage.

* **Query Optimization**:

  * Avoid `SELECT *` in production queries. Only select the columns you need.
  * Use `EXPLAIN` to understand how MySQL is executing your queries and adjust indexes accordingly.
  * For complex queries, break them down into smaller parts to isolate performance issues.

---

## **Materials Needed**

* A MySQL server (use `sakila` or `employees` database for exercises).
* A text editor (MySQL Workbench or a similar tool to execute SQL queries).
* **Sample Data**: The exercises will use tables like `employees`, `departments`, and `orders` to practice indexing and query optimization.

---

## **Lab Exercises**

### **Lab 1: Creating Indexes**

1. **Create a simple index** on the `employees` table on the `last_name` column.
2. **Create a composite index** on the `orders` table for `customer_id` and `order_date`.

### **Lab 2: Analyzing Query Performance with `EXPLAIN`**

1. **Write a query** to retrieve all employees from a specific department.
2. **Use `EXPLAIN`** to analyze the query execution plan and identify if indexes are being used effectively.

### **Lab 3: Optimizing Queries**

1. **Optimize a query** that joins the `employees` and `departments` tables. Ensure that it uses the appropriate indexes for faster performance.
2. **Test query performance** with and without indexing, and compare the execution times.

---

## **Assessment Criteria**

* **Lab Completion**: Ensure that all tasks in the lab are completed successfully.
* **Query Optimization**: Test and verify that queries are optimized by reviewing the `EXPLAIN` output.
* **Index Usage**: Verify the creation and removal of indexes and ensure they align with the optimization goals.

---

## **Resources**

* [MySQL Indexing Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-index.html)
* [MySQL EXPLAIN Documentation](https://dev.mysql.com/doc/refman/8.0/en/explain.html)

---

## **Next Steps**

Tomorrow, on **Day 7**, we will conclude the course with a focus on **Transaction Management and Advanced SQL Features**. We’ll dive into concepts like **ACID properties**, **transactions**, and **advanced SQL techniques** that will help you maintain data integrity and handle complex data operations efficiently.

---

### **Conclusion**

Day 6 focuses on a critical skill for any SQL developer: **database indexing and query optimization**. Learners will understand how indexes work, how to create them, and how to optimize queries for better performance. This knowledge is key for working with large datasets and ensuring that SQL queries perform efficiently.
