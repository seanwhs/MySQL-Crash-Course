# **Day 3: CRUD Operations (Create, Read, Update, Delete)**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 3
**Duration:** 2–3 hours

---

## **Overview**

Today, we’ll dive into the heart of working with data in MySQL—**CRUD Operations**. These are the four basic operations that allow you to interact with data stored in a database:

* **Create**: Insert new data into the database.
* **Read**: Retrieve and query data.
* **Update**: Modify existing data in the database.
* **Delete**: Remove data from the database.

By the end of the day, you'll be able to use SQL to efficiently manipulate data, filter results, update records, and delete unwanted data.

---

## **Learning Objectives**

After completing this day, you should be able to:

1. **Perform Insert Operations**: Use the `INSERT INTO` statement to add new rows of data to your tables.
2. **Retrieve Data**: Use the `SELECT` statement to retrieve specific data with or without conditions.
3. **Filter Data**: Apply `WHERE`, `AND`, `OR`, and other operators to filter data for more granular results.
4. **Update Existing Data**: Use the `UPDATE` statement to modify records in your tables.
5. **Delete Data**: Use the `DELETE` statement to remove records from your tables.
6. **Use `ORDER BY` and `LIMIT`**: Sort your query results and limit the number of rows returned.
7. **Perform Aggregate Functions**: Use aggregate functions like `COUNT()`, `SUM()`, `AVG()`, and `MAX()` for summarizing data.

---

## **Prerequisites**

Before starting Day 3, you should have:

* Created at least one table in MySQL.
* A basic understanding of MySQL syntax and how to connect to a MySQL database.
* Completed **Day 1 and Day 2** lessons, which focused on database and table creation, data types, and constraints.

---

## **Topics Covered Today**

1. **Introduction to CRUD Operations**:

   * Overview of the four core operations (Create, Read, Update, Delete).
   * Basic syntax and usage of SQL commands.

2. **Inserting Data with `INSERT INTO`**:

   * Syntax for inserting a single row and multiple rows.
   * Understanding default values and `NULL`.

3. **Selecting Data with `SELECT`**:

   * Using `SELECT` to retrieve data from one or more columns.
   * Filtering with `WHERE` and using logical operators (`AND`, `OR`).
   * Sorting results with `ORDER BY`.
   * Limiting the number of results with `LIMIT`.

4. **Updating Data with `UPDATE`**:

   * Syntax for modifying existing records.
   * Using the `SET` clause to update one or more columns.
   * Conditions to update specific rows using `WHERE`.

5. **Deleting Data with `DELETE`**:

   * Syntax for removing records from a table.
   * Caution: Deleting data permanently.
   * Using `WHERE` to delete specific rows, preventing accidental data loss.

6. **Using Aggregate Functions**:

   * Summarizing data with functions like `COUNT()`, `SUM()`, `AVG()`, `MAX()`, and `MIN()`.
   * Grouping data using `GROUP BY` for aggregated results.

---

## **Agenda**

* **Introduction to CRUD**: 10 minutes
* **Inserting Data (Create)**: 20 minutes
* **Reading Data (Read)**: 30 minutes
* **Updating Data (Update)**: 20 minutes
* **Deleting Data (Delete)**: 20 minutes
* **Working with Aggregate Functions**: 20 minutes
* **Lab Exercise**: 30 minutes
* **Q&A and Recap**: 10–15 minutes

---

## **Lab Exercises**

In the lab session, you’ll practice the following tasks:

1. Insert sample data into the `employees` table.
2. Retrieve data from the `employees` table based on certain conditions (e.g., retrieve employees with salaries over $50,000).
3. Update records (e.g., increase the salary of all employees in a particular department).
4. Delete records (e.g., remove an employee record based on a condition).
5. Use aggregate functions to get the total salary of employees in each department.

---

## **Key SQL Statements to Practice**

### **1. `INSERT INTO`**

* Inserting a single row:

  ```sql
  INSERT INTO employees (name, department, salary) VALUES ('John Doe', 'HR', 50000);
  ```

* Inserting multiple rows:

  ```sql
  INSERT INTO employees (name, department, salary) VALUES
  ('Jane Smith', 'IT', 70000),
  ('Mark Johnson', 'Finance', 80000);
  ```

### **2. `SELECT`**

* Basic SELECT statement:

  ```sql
  SELECT * FROM employees;
  ```

* SELECT with conditions (`WHERE`):

  ```sql
  SELECT name, department FROM employees WHERE salary > 60000;
  ```

* Sorting results (`ORDER BY`):

  ```sql
  SELECT name, salary FROM employees ORDER BY salary DESC;
  ```

* Limiting results (`LIMIT`):

  ```sql
  SELECT * FROM employees LIMIT 5;
  ```

### **3. `UPDATE`**

* Update existing data:

  ```sql
  UPDATE employees SET salary = 75000 WHERE department = 'IT';
  ```

### **4. `DELETE`**

* Deleting a record:

  ```sql
  DELETE FROM employees WHERE name = 'Mark Johnson';
  ```

### **5. Aggregate Functions**

* Using `COUNT()` to count records:

  ```sql
  SELECT COUNT(*) FROM employees;
  ```

* Using `SUM()` to calculate the total salary:

  ```sql
  SELECT SUM(salary) FROM employees WHERE department = 'HR';
  ```

---

## **Expected Outcomes**

By the end of Day 3, learners will be able to:

* Insert new data into MySQL tables.
* Retrieve data using complex queries with `WHERE`, `ORDER BY`, `LIMIT`, and aggregate functions.
* Modify existing records with `UPDATE` statements.
* Delete records safely using the `DELETE` statement.
* Utilize MySQL’s aggregate functions to summarize data.

---

## **Next Steps**

After completing Day 3, you'll be ready to move on to more complex tasks such as joining multiple tables and working with relationships between them in Day 4. You’ll also begin to work with database normalization and advanced SQL techniques in the coming days.

---

**Trainer Tip:**
Encourage learners to practice with a variety of queries during the lab and walk them through debugging common mistakes, such as forgetting to use a `WHERE` clause in an `UPDATE` or `DELETE` statement (which can result in unintended modifications).

