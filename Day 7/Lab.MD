# **Lab: Day 7 - Transaction Management and Advanced SQL Features**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 7
**Topic**: Transaction Management and Advanced SQL Features

---

## **Objectives of the Lab**

By the end of this lab, you will:

1. Be able to use transaction management commands (`START TRANSACTION`, `COMMIT`, `ROLLBACK`, and `SAVEPOINT`).
2. Understand how isolation levels work and be able to configure them in MySQL.
3. Create and execute stored procedures, triggers, and views.
4. Gain practical experience with managing database transactions and automating processes.

---

## **Lab Setup**

Ensure that you have:

* **MySQL Workbench** or any other MySQL client installed and configured.
* Access to a MySQL database (either a local or cloud-based database).
* A sample database (you can create your own database or use the following sample structure):

```sql
CREATE DATABASE mycompany;
USE mycompany;

CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(50),
    salary DECIMAL(10, 2),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    last_modified TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);

-- Insert some sample data
INSERT INTO employees (name, department, salary) VALUES ('John Doe', 'Sales', 50000);
INSERT INTO employees (name, department, salary) VALUES ('Jane Smith', 'HR', 55000);
```

---

## **Part 1: Working with Transactions**

### **Objective**:

* Practice using **transaction management** commands like `START TRANSACTION`, `COMMIT`, `ROLLBACK`, and `SAVEPOINT`.

### **Instructions**:

1. **Start a Transaction**:
   Open your SQL client and begin a new transaction:

   ```sql
   START TRANSACTION;
   ```

2. **Insert Data**:
   Insert a new record into the `employees` table:

   ```sql
   INSERT INTO employees (name, department, salary) 
   VALUES ('Michael Johnson', 'Marketing', 60000);
   ```

3. **Simulate an Error**:
   Try to insert a record with a duplicate primary key (or use a unique constraint violation if the column exists) to simulate an error:

   ```sql
   INSERT INTO employees (id, name, department, salary) 
   VALUES (1, 'Invalid Employee', 'Engineering', 70000);
   ```

4. **Rollback the Transaction**:
   Use `ROLLBACK` to undo the changes made in the transaction due to the error:

   ```sql
   ROLLBACK;
   ```

5. **Commit Changes**:
   Insert a new valid record, and then commit the transaction:

   ```sql
   START TRANSACTION;
   INSERT INTO employees (name, department, salary) 
   VALUES ('Alice Green', 'Finance', 75000);
   COMMIT;
   ```

6. **Savepoint**:
   Use a `SAVEPOINT` to mark a point in the transaction and roll back to it if needed:

   ```sql
   START TRANSACTION;
   SAVEPOINT before_inserting_employee;
   INSERT INTO employees (name, department, salary) 
   VALUES ('Robert Brown', 'IT', 65000);
   -- Simulate some condition to rollback to the savepoint
   ROLLBACK TO SAVEPOINT before_inserting_employee;
   COMMIT;
   ```

---

## **Part 2: Working with Isolation Levels**

### **Objective**:

* Experiment with **isolation levels** to understand how concurrent transactions interact with each other.

### **Instructions**:

1. **Set the Isolation Level**:
   Set the isolation level to `READ COMMITTED`:

   ```sql
   SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
   ```

2. **Open Two Sessions**:
   Open two different SQL clients or tabs, representing two concurrent transactions.

3. **Session 1 (Transaction 1)**:
   Begin a transaction and insert a record:

   ```sql
   START TRANSACTION;
   INSERT INTO employees (name, department, salary) 
   VALUES ('Sarah Taylor', 'Sales', 60000);
   ```

4. **Session 2 (Transaction 2)**:
   While **Transaction 1** is open, attempt to read the record inserted in **Transaction 1** from **Session 2**:

   ```sql
   SELECT * FROM employees WHERE name = 'Sarah Taylor';
   ```

   * **What do you see?**
     You should only see the record in **Session 2** after **Transaction 1** commits, demonstrating that **READ COMMITTED** ensures only committed data is visible.

5. **Change the Isolation Level**:
   Change the isolation level to `SERIALIZABLE` in **Session 1** and repeat the experiment. Observe the differences in behavior, particularly with dirty reads, non-repeatable reads, and phantom reads.

---

## **Part 3: Stored Procedures**

### **Objective**:

* Learn how to create and execute **stored procedures** to automate tasks.

### **Instructions**:

1. **Create a Stored Procedure**:
   Write a stored procedure to add a new employee to the `employees` table:

   ```sql
   DELIMITER $$

   CREATE PROCEDURE add_employee(
       IN emp_name VARCHAR(100), 
       IN emp_dept VARCHAR(50), 
       IN emp_salary DECIMAL(10, 2)
   )
   BEGIN
       INSERT INTO employees (name, department, salary) 
       VALUES (emp_name, emp_dept, emp_salary);
   END $$

   DELIMITER ;
   ```

2. **Call the Stored Procedure**:
   Call the stored procedure to insert a new employee:

   ```sql
   CALL add_employee('David Wilson', 'Marketing', 80000);
   ```

3. **Verify the Insertion**:
   Check if the employee has been inserted into the table:

   ```sql
   SELECT * FROM employees WHERE name = 'David Wilson';
   ```

---

## **Part 4: Triggers**

### **Objective**:

* Implement a **trigger** to automatically set a timestamp whenever a record in the `employees` table is updated.

### **Instructions**:

1. **Create a Trigger**:
   Create a trigger to automatically update the `last_modified` timestamp when an employee's information is updated:

   ```sql
   DELIMITER $$

   CREATE TRIGGER update_employee_timestamp
   BEFORE UPDATE ON employees
   FOR EACH ROW
   BEGIN
       SET NEW.last_modified = NOW();
   END $$

   DELIMITER ;
   ```

2. **Test the Trigger**:
   Update an employee's details and verify that the `last_modified` field is updated:

   ```sql
   UPDATE employees SET salary = 85000 WHERE name = 'David Wilson';
   SELECT * FROM employees WHERE name = 'David Wilson';
   ```

---

## **Part 5: Views**

### **Objective**:

* Create and use **views** to simplify complex queries.

### **Instructions**:

1. **Create a View**:
   Create a view to display only the employee names and their departments:

   ```sql
   CREATE VIEW employee_view AS
   SELECT name, department FROM employees;
   ```

2. **Query the View**:
   Use the view to query employee data:

   ```sql
   SELECT * FROM employee_view;
   ```

3. **Modify the View**:
   Alter the view to include salary information:

   ```sql
   CREATE OR REPLACE VIEW employee_view AS
   SELECT name, department, salary FROM employees;
   ```

4. **Query the Modified View**:

   ```sql
   SELECT * FROM employee_view;
   ```

---

## **Lab Submission**

At the end of the lab, learners should:

* Have experience using transaction commands like `START TRANSACTION`, `COMMIT`, `ROLLBACK`, and `SAVEPOINT`.
* Understand how to work with isolation levels to control concurrent transactions.
* Have created and used stored procedures, triggers, and views to automate tasks and simplify queries.

---

## **Next Steps**

* **Practice**: Continue experimenting with stored procedures, triggers, and views in your own MySQL database.
* **Advanced Topics**: Explore more complex triggers and views, or try creating stored functions and working with more complex SQL queries.

---

This **Lab** allows learners to apply the concepts of transaction management and advanced SQL features in a practical setting, reinforcing their understanding through hands-on exercises. 