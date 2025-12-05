# **Day 3 Lab: CRUD Operations (Create, Read, Update, Delete)**

**Duration**: 30–40 minutes

## **Lab Overview**

In this lab, you'll work with a sample `employees` table and perform different CRUD operations. You'll insert records, retrieve data, update information, and delete records. Additionally, you'll use some SQL techniques like filtering, sorting, and limiting data.

---

## **Lab Setup**

1. **Create the `employees` Table**
   If you haven't already, let's start by creating the `employees` table. Here's the SQL code to define the structure of the table:

   ```sql
   CREATE TABLE employees (
       employee_id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(100) NOT NULL,
       department VARCHAR(50),
       salary DECIMAL(10, 2),
       hire_date DATE
   );
   ```

2. **Insert Sample Data**
   Insert some sample employee records into the `employees` table. Use the following SQL code to add multiple rows:

   ```sql
   INSERT INTO employees (name, department, salary, hire_date) 
   VALUES
   ('John Doe', 'HR', 50000, '2022-06-15'),
   ('Jane Smith', 'IT', 75000, '2020-08-22'),
   ('Mark Johnson', 'Finance', 80000, '2019-02-10'),
   ('Emily Davis', 'IT', 68000, '2021-05-30'),
   ('Robert Brown', 'HR', 55000, '2020-11-17');
   ```

---

## **Lab Tasks**

### **Task 1: Insert Data (Create)**

* **Objective**: Insert a new employee record into the `employees` table.
* **Instructions**:
  Insert a new employee into the table:

  * Name: `Alice Green`
  * Department: `Marketing`
  * Salary: `62000`
  * Hire Date: `2023-01-10`

  **Hint**:
  Use the `INSERT INTO` statement as shown earlier.

---

### **Task 2: Retrieve Data (Read)**

* **Objective**: Retrieve data from the `employees` table.
* **Instructions**:

  1. Retrieve the names and salaries of all employees in the `IT` department.
  2. Retrieve all employees who have a salary greater than `60000`.
  3. Retrieve the first 3 employees listed in the table.

  **Hint**:
  Use `SELECT` with `WHERE`, `ORDER BY`, and `LIMIT` as needed.

---

### **Task 3: Update Data (Update)**

* **Objective**: Update existing records.
* **Instructions**:

  1. Increase the salary of all employees in the `HR` department by 10%.
  2. Change the department of `Mark Johnson` to `Marketing`.

  **Hint**:
  Use `UPDATE` with the `SET` clause and a `WHERE` condition.

---

### **Task 4: Delete Data (Delete)**

* **Objective**: Delete records from the table.
* **Instructions**:

  1. Delete the employee record for `Emily Davis`.
  2. Delete all employees who have a salary less than `60000`.

  **Hint**:
  Use `DELETE` with a `WHERE` condition to target specific rows.

---

### **Task 5: Aggregate Functions**

* **Objective**: Use SQL aggregate functions to summarize data.
* **Instructions**:

  1. Find the average salary of all employees.
  2. Count the total number of employees in each department.
  3. Find the highest salary among all employees.

  **Hint**:
  Use `COUNT()`, `AVG()`, and `MAX()` functions along with `GROUP BY` as needed.

---

### **Task 6: Combine Operations (Bonus Task)**

* **Objective**: Combine different SQL operations in one query.
* **Instructions**:
  Retrieve a list of employees who have a salary greater than `60000`, ordered by their `hire_date` (ascending). Limit the results to the top 5 employees.

  **Hint**:
  Use `WHERE`, `ORDER BY`, and `LIMIT` together.

---

## **Expected Results**

1. **Task 1**: A new employee, `Alice Green`, should be added to the `employees` table.
2. **Task 2**: You should see a filtered list of employees based on the criteria:

   * Employees in the `IT` department.
   * Employees with a salary greater than `60000`.
   * The first 3 employees.
3. **Task 3**: After running the `UPDATE` statements:

   * The salary of all employees in `HR` should be increased by 10%.
   * `Mark Johnson`'s department should be updated to `Marketing`.
4. **Task 4**: After running the `DELETE` statements:

   * `Emily Davis` should be removed from the table.
   * All employees with a salary less than `60000` should be deleted.
5. **Task 5**: You will see summarized data:

   * The average salary of all employees.
   * The number of employees in each department.
   * The highest salary in the table.
6. **Task 6**: The query should return a list of employees with a salary greater than `60000`, ordered by their hire date, and limited to the first 5 results.

---

## **Additional Challenge (Optional)**

* **Task 7: Complex Query with Joins**

  * Create a new table called `departments` with the following structure:

    ```sql
    CREATE TABLE departments (
        department_id INT AUTO_INCREMENT PRIMARY KEY,
        department_name VARCHAR(50)
    );
    ```
  * Insert some sample data into the `departments` table (e.g., `HR`, `IT`, `Marketing`, `Finance`).
  * Update the `employees` table to reference the `departments` table with a `department_id` (foreign key).
  * Perform a **JOIN** query to retrieve employee names and their respective department names.

---

## **Completion Criteria**

* Submit the SQL code you’ve written for each task.
* Verify the data changes in your MySQL database to ensure that all CRUD operations have been successfully completed.
* Ensure that the final query results meet the task requirements (filtered, sorted, aggregated, etc.).

---

### **Trainer Tips:**

* **Walkthrough**: Begin the lab by walking the learners through the first task to ensure everyone is on track.
* **Common Errors**: Keep an eye on common mistakes such as forgetting to include `WHERE` clauses with `UPDATE` or `DELETE` statements, which could lead to accidental data changes.
* **Use Real Data**: If the learners already have a practice database with different tables, encourage them to apply CRUD operations on their own data.
* **Time Management**: Allow time for questions during the lab session. Encourage learners to experiment with different SQL statements to deepen their understanding.

