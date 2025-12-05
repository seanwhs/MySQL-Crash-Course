# **Pre-Course Quiz: MySQL Fundamentals**

**Course**: MySQL 1-Week Hands-On Crash Course
**Duration**: 15-20 minutes
**Format**: Multiple Choice, True/False, and Short Answer

---

### **Section 1: SQL Basics and Database Concepts**

1. **Which of the following best describes a relational database?**

   a) A collection of tables where data is stored in rows and columns
   b) A collection of documents stored as JSON
   c) A file system used to store large files
   d) A spreadsheet with data in cells

2. **Which SQL keyword is used to retrieve data from a database?**

   a) `UPDATE`
   b) `SELECT`
   c) `INSERT`
   d) `DELETE`

3. **What does the `PRIMARY KEY` in a table represent?**

   a) A unique identifier for each record in a table
   b) A column that can hold any type of data
   c) A column that contains multiple values
   d) A foreign reference to another table

4. **Which of the following is a valid SQL command to create a new table?**

   a) `CREATE TABLE table_name`
   b) `MAKE TABLE table_name`
   c) `NEW TABLE table_name`
   d) `CREATE DATABASE table_name`

5. **What is the purpose of the `WHERE` clause in SQL?**

   a) To limit the number of columns in the result
   b) To specify conditions for filtering records
   c) To delete records from the table
   d) To join two tables together

---

### **Section 2: SQL Query Writing**

6. **What does the following SQL query do?**

   ```sql
   SELECT * FROM customers WHERE age > 30;
   ```

   a) Selects all columns from the `customers` table where the age is greater than 30
   b) Deletes rows where age is greater than 30
   c) Updates the age column of the customers table
   d) Selects all records from the `customers` table

7. **What is the result of the following query?**

   ```sql
   SELECT name, COUNT(*) FROM employees GROUP BY department_id;
   ```

   a) Returns the name of each employee and the total number of employees
   b) Returns the name of each department and the number of employees in that department
   c) Returns a list of departments without counting employees
   d) Returns all employee names in alphabetical order

8. **Which of the following SQL statements can be used to add a new column to an existing table?**

   a) `ALTER TABLE table_name ADD COLUMN column_name data_type;`
   b) `CREATE COLUMN table_name data_type;`
   c) `INSERT COLUMN INTO table_name;`
   d) `CHANGE TABLE table_name ADD COLUMN column_name;`

9. **True or False: The `DISTINCT` keyword is used to return only unique (non-duplicate) values in a query.**

---

### **Section 3: SQL Joins and Relationships**

10. **Which of the following joins would you use to return all records from the left table and matching records from the right table, and NULLs where there is no match?**

    a) `INNER JOIN`
    b) `LEFT JOIN`
    c) `RIGHT JOIN`
    d) `FULL JOIN`

11. **In the context of SQL, what is a "foreign key"?**

    a) A column in one table that uniquely identifies each record in another table
    b) A column that stores sensitive data
    c) A key used to store encrypted values
    d) A primary key in the same table

12. **Which SQL command can be used to remove all records from a table without deleting the table itself?**

    a) `DELETE FROM table_name`
    b) `DROP TABLE table_name`
    c) `REMOVE FROM table_name`
    d) `TRUNCATE TABLE table_name`

---

### **Section 4: Data Types and Functions**

13. **Which SQL data type would be used to store a large amount of text data?**

    a) `INT`
    b) `VARCHAR`
    c) `TEXT`
    d) `DATE`

14. **Which of the following SQL functions returns the number of rows in a result set?**

    a) `COUNT()`
    b) `SUM()`
    c) `MAX()`
    d) `AVG()`

15. **True or False: The `NOW()` function in MySQL returns the current date and time.**

---

### **Section 5: SQL Indexing and Optimization**

16. **What is the purpose of an index in a database?**

    a) To store large amounts of data
    b) To make queries run faster by allowing quick access to data
    c) To protect sensitive information
    d) To encrypt data before storing it

17. **Which of the following can slow down query performance when working with large datasets?**

    a) Using indexes properly
    b) Having too many `JOIN`s in a query
    c) Writing optimized queries
    d) Using `GROUP BY` on indexed columns

---

### **Section 6: Advanced SQL Concepts (Optional)**

18. **True or False: A subquery is a query nested inside another query.**

19. **Which of the following SQL clauses would you use to filter grouped results?**

    a) `WHERE`
    b) `HAVING`
    c) `GROUP BY`
    d) `ORDER BY`

20. **What is a correlated subquery?**

    a) A subquery that can be executed independently of the outer query
    b) A subquery that depends on values from the outer query
    c) A subquery used in the `SELECT` clause
    d) A subquery used to calculate the average value in a table

---

## **Scoring Guide**

* **0-5 Correct**: Basic understanding of SQL concepts. The course will provide foundational knowledge to build on.
* **6-15 Correct**: Intermediate knowledge of SQL. The course will focus on expanding your skill set with more advanced techniques.
* **16-20 Correct**: Advanced knowledge of SQL. The course will dive deeper into complex queries and optimizations.

---

### **Conclusion**

This **Pre-Course Quiz** is designed to assess the learners’ foundational knowledge of SQL concepts. Based on the results, the course can be tailored to fill knowledge gaps and provide more focus on areas where learners may need additional practice. 