# **Quiz - Day 3: CRUD Operations (Create, Read, Update, Delete)**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 3

---

## **Part 1: Multiple Choice Questions (MCQs)**

### **1. What does the `INSERT INTO` statement do in SQL?**

a) Deletes data from a table.
b) Retrieves data from a table.
c) Modifies existing data in a table.
d) Adds new records to a table.

### **2. Which SQL command is used to update the data in a table?**

a) `DELETE FROM`
b) `SELECT`
c) `UPDATE`
d) `INSERT INTO`

### **3. What happens if you run the `DELETE FROM` statement without a `WHERE` clause?**

a) The command will fail to execute.
b) It will delete a single row from the table.
c) It will delete all rows from the table.
d) It will update the table, not delete data.

### **4. Which SQL clause is used to filter records in a query?**

a) `WHERE`
b) `GROUP BY`
c) `ORDER BY`
d) `HAVING`

### **5. What does the `LIMIT` clause do in an SQL query?**

a) It limits the columns returned by the query.
b) It limits the number of rows returned by the query.
c) It limits the table size.
d) It limits the time the query will run.

---

## **Part 2: True or False**

### **6. You can use `ORDER BY` to sort the results of a query in ascending or descending order.**

* True
* False

### **7. The `UPDATE` statement can only modify one column at a time.**

* True
* False

### **8. The `COUNT()` function returns the total number of rows in a result set.**

* True
* False

### **9. The `WHERE` clause is optional when using `DELETE` or `UPDATE`.**

* True
* False

### **10. The `SUM()` function is used to calculate the total of numeric values in a column.**

* True
* False

---

## **Part 3: SQL Query Writing**

### **11. Write an SQL query to add a new employee to the `employees` table. The employee's name is 'Sarah Lee', department is 'Sales', salary is 72000, and the hire date is '2023-03-01'.**

### **12. Write an SQL query to retrieve the names and salaries of employees who earn more than $65,000.**

### **13. Write an SQL query to update the salary of all employees in the 'Finance' department by 5%.**

### **14. Write an SQL query to delete an employee from the `employees` table where the employee’s name is 'John Doe'.**

### **15. Write an SQL query to find the average salary of employees in the 'IT' department.**

---

## **Part 4: Scenario-Based Questions**

### **16. Scenario**: You have a table `employees` with columns `employee_id`, `name`, `department`, `salary`, and `hire_date`.

* What would happen if you ran the following query without a `WHERE` clause?

  ```sql
  DELETE FROM employees;
  ```

  * **Answer:** All rows in the `employees` table will be deleted. This could result in losing all data.

### **17. Scenario**: You want to list the top 5 highest-paid employees in the company.

* Which SQL query would you use to achieve this?

  * **Answer:**

    ```sql
    SELECT name, salary FROM employees ORDER BY salary DESC LIMIT 5;
    ```
  * Explanation: The `ORDER BY salary DESC` sorts the employees by salary in descending order, and `LIMIT 5` restricts the result to the top 5.

---

## **Part 5: Fill-in-the-Blanks**

### **18. To retrieve all columns from the `employees` table where the department is 'IT', use the following query:**

```sql
SELECT ________ FROM employees WHERE ________ = 'IT';
```

### **19. To update the salary of an employee named 'Alice Green' to 80000, the query would be:**

```sql
UPDATE employees SET ________ = 80000 WHERE ________ = 'Alice Green';
```

### **20. To count how many employees work in the 'HR' department, you would use:**

```sql
SELECT ________ FROM employees WHERE ________ = 'HR';
```

---

## **Answer Key**

### **Part 1: Multiple Choice Questions**

1. **d)** Adds new records to a table.
2. **c)** `UPDATE`
3. **c)** It will delete all rows from the table.
4. **a)** `WHERE`
5. **b)** It limits the number of rows returned by the query.

### **Part 2: True or False**

6. **True**
7. **False** (You can update multiple columns at once using `SET column1 = value1, column2 = value2`).
8. **True**
9. **False** (Always use `WHERE` with `DELETE` and `UPDATE` to avoid unintended data changes).
10. **True**

### **Part 3: SQL Query Writing**

11.

```sql
INSERT INTO employees (name, department, salary, hire_date) 
VALUES ('Sarah Lee', 'Sales', 72000, '2023-03-01');
```

12.

```sql
SELECT name, salary FROM employees WHERE salary > 65000;
```

13.

```sql
UPDATE employees SET salary = salary * 1.05 WHERE department = 'Finance';
```

14.

```sql
DELETE FROM employees WHERE name = 'John Doe';
```

15.

```sql
SELECT AVG(salary) FROM employees WHERE department = 'IT';
```

### **Part 4: Scenario-Based Questions**

16. **Answer**: Running the query `DELETE FROM employees;` without a `WHERE` clause will **delete all rows** in the `employees` table. This is a dangerous operation, as it permanently removes all the data.

17. **Answer**:

```sql
SELECT name, salary FROM employees ORDER BY salary DESC LIMIT 5;
```

This query retrieves the top 5 highest-paid employees by ordering the result by salary in descending order and limiting the result to 5 records.

### **Part 5: Fill-in-the-Blanks**

18.

```sql
SELECT * FROM employees WHERE department = 'IT';
```

19.

```sql
UPDATE employees SET salary = 80000 WHERE name = 'Alice Green';
```

20.

```sql
SELECT COUNT(*) FROM employees WHERE department = 'HR';
```

---

## **Conclusion**

This quiz helps reinforce the concepts learned in the session and ensures learners are comfortable with CRUD operations in MySQL. The mix of multiple choice, SQL writing, and scenario-based questions gives learners a well-rounded understanding of how to work with databases.

