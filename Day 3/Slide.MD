## **Day 3: CRUD Operations (Create, Read, Update, Delete)**

**Slide Deck Outline**:

### **Slide 1: Title Slide**

* **Title:** Day 3 – CRUD Operations (Create, Read, Update, Delete)
* **Subtitle:** MySQL 1-Week Hands-On Crash Course
* **Your Name & Date**

---

### **Slide 2: Learning Objectives**

* **Title:** Learning Objectives
* **Content:**

  * Perform Insert operations with `INSERT INTO`.
  * Retrieve data using the `SELECT` statement.
  * Filter results with `WHERE`, `AND`, `OR`.
  * Update data with the `UPDATE` statement.
  * Delete data safely with the `DELETE` statement.
  * Use aggregate functions like `COUNT()`, `SUM()`, and `AVG()`.

---

### **Slide 3: Introduction to CRUD Operations**

* **Title:** Introduction to CRUD Operations
* **Content:**

  * **CRUD** stands for:

    * **C**: Create (Insert data)
    * **R**: Read (Retrieve data)
    * **U**: Update (Modify data)
    * **D**: Delete (Remove data)
  * These are the fundamental operations in relational databases.
  * Why CRUD? CRUD operations are the core interactions you'll have with your MySQL database, enabling you to manage and manipulate data.

---

### **Slide 4: Create (INSERT INTO)**

* **Title:** Create – Inserting Data
* **Content:**

  * **Syntax:**

    ```sql
    INSERT INTO table_name (column1, column2, column3, ...) 
    VALUES (value1, value2, value3, ...);
    ```
  * **Example:**

    ```sql
    INSERT INTO employees (name, department, salary) 
    VALUES ('John Doe', 'HR', 50000);
    ```
  * **Note:** Use `INSERT INTO` to add new records to a table.

---

### **Slide 5: Bulk Insert (INSERT INTO Multiple Rows)**

* **Title:** Insert Multiple Rows
* **Content:**

  * **Syntax for Multiple Rows Insert:**

    ```sql
    INSERT INTO employees (name, department, salary) 
    VALUES 
    ('Jane Smith', 'IT', 70000),
    ('Mark Johnson', 'Finance', 80000);
    ```
  * **Use Case:** Bulk insert is useful when adding multiple records at once.

---

### **Slide 6: Read (SELECT)**

* **Title:** Read – Retrieving Data
* **Content:**

  * **Basic Syntax:**

    ```sql
    SELECT column1, column2, ... FROM table_name;
    ```
  * **Example:**

    ```sql
    SELECT * FROM employees;
    ```
  * **Note:** `SELECT *` retrieves all columns. Use specific columns to retrieve just the ones you need.

---

### **Slide 7: Filtering Results (WHERE)**

* **Title:** Filter Data – Using WHERE Clause
* **Content:**

  * **Syntax:**

    ```sql
    SELECT column1, column2 
    FROM table_name 
    WHERE condition;
    ```
  * **Example:**

    ```sql
    SELECT name, department FROM employees WHERE salary > 60000;
    ```
  * **Note:** The `WHERE` clause filters records based on the condition provided.

---

### **Slide 8: Sorting Results (ORDER BY)**

* **Title:** Sorting Data – Using ORDER BY
* **Content:**

  * **Syntax:**

    ```sql
    SELECT column1, column2 
    FROM table_name 
    ORDER BY column_name [ASC|DESC];
    ```
  * **Example:**

    ```sql
    SELECT name, salary FROM employees ORDER BY salary DESC;
    ```
  * **Note:** `ASC` is the default (ascending), and `DESC` sorts in descending order.

---

### **Slide 9: Limiting Results (LIMIT)**

* **Title:** Limit Results – Using LIMIT
* **Content:**

  * **Syntax:**

    ```sql
    SELECT column1, column2 
    FROM table_name 
    LIMIT number;
    ```
  * **Example:**

    ```sql
    SELECT * FROM employees LIMIT 5;
    ```
  * **Note:** `LIMIT` restricts the number of rows returned.

---

### **Slide 10: Update (UPDATE)**

* **Title:** Update – Modifying Data
* **Content:**

  * **Syntax:**

    ```sql
    UPDATE table_name 
    SET column1 = value1, column2 = value2 
    WHERE condition;
    ```
  * **Example:**

    ```sql
    UPDATE employees SET salary = 75000 WHERE department = 'IT';
    ```
  * **Note:** Always use a `WHERE` clause to target specific records. Omitting `WHERE` will update all rows.

---

### **Slide 11: Delete (DELETE)**

* **Title:** Delete – Removing Data
* **Content:**

  * **Syntax:**

    ```sql
    DELETE FROM table_name WHERE condition;
    ```
  * **Example:**

    ```sql
    DELETE FROM employees WHERE name = 'Mark Johnson';
    ```
  * **Note:** **Be careful!** The `DELETE` statement removes records permanently.

---

### **Slide 12: Aggregate Functions (COUNT, SUM, AVG)**

* **Title:** Aggregate Functions – Summarizing Data
* **Content:**

  * **COUNT()**: Returns the number of rows in a result set.

    * Example: `SELECT COUNT(*) FROM employees;`
  * **SUM()**: Returns the total sum of a numeric column.

    * Example: `SELECT SUM(salary) FROM employees;`
  * **AVG()**: Returns the average of a numeric column.

    * Example: `SELECT AVG(salary) FROM employees;`

---

### **Slide 13: Grouping Data (GROUP BY)**

* **Title:** Grouping Data – Using GROUP BY
* **Content:**

  * **Syntax:**

    ```sql
    SELECT column1, COUNT(*) 
    FROM table_name 
    GROUP BY column1;
    ```
  * **Example:**

    ```sql
    SELECT department, COUNT(*) FROM employees GROUP BY department;
    ```
  * **Note:** `GROUP BY` groups rows that have the same values into summary rows.

---

### **Slide 14: Practice Exercise**

* **Title:** Lab Exercise – CRUD Operations
* **Content:**

  * **Task 1:** Insert data into an `employees` table.
  * **Task 2:** Retrieve employees with salaries greater than $50,000.
  * **Task 3:** Update salaries for employees in the `IT` department.
  * **Task 4:** Delete an employee based on a specific condition.
  * **Task 5:** Use aggregate functions to summarize employee data.

---

### **Slide 15: Common Mistakes to Avoid**

* **Title:** Common Mistakes to Avoid
* **Content:**

  * Forgetting to use `WHERE` in `UPDATE` or `DELETE` statements (leading to unintended changes).
  * Using `SELECT *` when only a few columns are needed.
  * Forgetting to apply `ORDER BY` when sorting results.
  * Not using `LIMIT` when only a subset of results is needed.

---

### **Slide 16: Summary and Q&A**

* **Title:** Summary & Questions
* **Content:**

  * **Key Takeaways**:

    * The four CRUD operations form the core of interacting with a database.
    * SQL statements can be used to **create**, **retrieve**, **update**, and **delete** data.
    * Using `WHERE`, `ORDER BY`, and `LIMIT` enhances data querying.
  * Open the floor for **questions** from learners.

---

## **Final Slide: Thank You**

* **Title:** Thank You!
* **Content:**

  * **Thank you for your participation!**
  * **Next Session Preview**: Tomorrow we’ll explore **Joins** and how to retrieve data from multiple related tables.
  * Contact info (optional).

---

### **Trainer Tips for Presenting:**

* **Engage Learners**: Start by asking if anyone has worked with CRUD operations before, and get them involved by asking for examples or scenarios.
* **Live Demo**: Show live examples of `INSERT`, `SELECT`, `UPDATE`, and `DELETE` during the class to give them hands-on experience.
* **Visuals**: Use visuals like flowcharts to demonstrate how data flows during CRUD operations.
* **Time Management**: Keep the lesson moving by focusing on key concepts, ensuring you leave enough time for the lab exercises and Q&A.

---
