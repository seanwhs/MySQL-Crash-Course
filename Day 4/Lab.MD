## **Lab Exercise - Day 4: Joins and Subqueries**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 4

---

### **Lab Overview**

In this lab, you will work with two tables: `employees` and `departments`. You will use **Joins** and **Subqueries** to combine and manipulate data across these tables.

**Tables**:

1. **employees**: Contains employee details.

   * `employee_id` (INT, Primary Key)
   * `name` (VARCHAR)
   * `salary` (DECIMAL)
   * `hire_date` (DATE)
   * `department_id` (INT, Foreign Key referencing `departments`)
2. **departments**: Contains department details.

   * `department_id` (INT, Primary Key)
   * `department_name` (VARCHAR)
   * `budget` (DECIMAL)

---

### **Lab Setup**

If the tables are not already created in your MySQL environment, use the following SQL commands to create them and insert some sample data:

```sql
CREATE TABLE departments (
    department_id INT PRIMARY KEY AUTO_INCREMENT,
    department_name VARCHAR(100),
    budget DECIMAL(10, 2)
);

CREATE TABLE employees (
    employee_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    salary DECIMAL(10, 2),
    hire_date DATE,
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(department_id)
);

-- Inserting sample data into departments
INSERT INTO departments (department_name, budget) VALUES
('HR', 500000),
('Engineering', 1000000),
('Marketing', 300000);

-- Inserting sample data into employees
INSERT INTO employees (name, salary, hire_date, department_id) VALUES
('John Doe', 70000, '2020-01-15', 1),
('Alice Green', 95000, '2018-07-23', 2),
('Mark Johnson', 80000, '2019-09-30', 1),
('Emily Davis', 120000, '2021-03-12', 2),
('Sarah Lee', 105000, '2022-06-05', 3);
```

---

### **Task 1: INNER JOIN**

**Objective**: Retrieve a list of employees along with their department names. Use an **INNER JOIN** to combine the `employees` and `departments` tables.

* **Query**:

  ```sql
  SELECT employees.name, employees.salary, departments.department_name
  FROM employees
  INNER JOIN departments
  ON employees.department_id = departments.department_id;
  ```

* **Expected Output**:

  * List of employees with their respective department names.
  * Only employees who have a valid department (no `NULL` department) will appear in the results.

---

### **Task 2: LEFT JOIN**

**Objective**: Retrieve a list of all employees along with their department names. Use a **LEFT JOIN** to include employees who do not belong to any department (i.e., employees who have a `NULL` department).

* **Query**:

  ```sql
  SELECT employees.name, employees.salary, departments.department_name
  FROM employees
  LEFT JOIN departments
  ON employees.department_id = departments.department_id;
  ```

* **Expected Output**:

  * List of all employees, including those who do not have a department.
  * Employees without a department should show `NULL` in the `department_name` column.

---

### **Task 3: RIGHT JOIN**

**Objective**: Retrieve a list of all departments along with the employees in them. Use a **RIGHT JOIN** to ensure that even departments with no employees are included.

* **Query**:

  ```sql
  SELECT employees.name, employees.salary, departments.department_name
  FROM employees
  RIGHT JOIN departments
  ON employees.department_id = departments.department_id;
  ```

* **Expected Output**:

  * List of all departments with their respective employees.
  * Departments without any employees will have `NULL` in the `employee_name` and `salary` columns.

---

### **Task 4: Subquery in WHERE Clause**

**Objective**: Find the employee(s) with the highest salary in the `employees` table using a **subquery** in the `WHERE` clause.

* **Query**:

  ```sql
  SELECT name, salary
  FROM employees
  WHERE salary = (SELECT MAX(salary) FROM employees);
  ```

* **Expected Output**:

  * List the name and salary of the employee with the highest salary.

---

### **Task 5: Subquery in SELECT Clause**

**Objective**: Retrieve the **department name** and the **highest salary** in each department. Use a **subquery** in the `SELECT` clause to get the maximum salary for each department.

* **Query**:

  ```sql
  SELECT departments.department_name,
         (SELECT MAX(salary) FROM employees WHERE employees.department_id = departments.department_id) AS highest_salary
  FROM departments;
  ```

* **Expected Output**:

  * List of department names with the highest salary in each department.
  * Use of subquery to calculate the `MAX(salary)` for each department.

---

### **Task 6: Correlated Subquery**

**Objective**: Retrieve the names of employees who earn more than the average salary of their department. Use a **correlated subquery**.

* **Query**:

  ```sql
  SELECT e.name
  FROM employees e
  WHERE e.salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);
  ```

* **Expected Output**:

  * List of employees who earn more than the average salary in their department.
  * The subquery computes the average salary for each department and compares it to each employee’s salary.

---

### **Task 7: Combining Joins and Subqueries**

**Objective**: Retrieve the department with the **highest average salary** among its employees. Use a combination of **joins** and **subqueries**.

* **Query**:

  ```sql
  SELECT department_name
  FROM departments
  WHERE department_id = (
      SELECT department_id
      FROM employees
      GROUP BY department_id
      ORDER BY AVG(salary) DESC
      LIMIT 1
  );
  ```

* **Expected Output**:

  * The name of the department that has the highest average salary.

---

### **Bonus Task: Full Join Workaround**

**Objective**: Retrieve all employees and departments, including those that don’t have a match. Use a combination of **LEFT JOIN** and **RIGHT JOIN** to simulate a **FULL JOIN**.

* **Query**:

  ```sql
  SELECT employees.name, employees.salary, departments.department_name
  FROM employees
  LEFT JOIN departments ON employees.department_id = departments.department_id
  UNION
  SELECT employees.name, employees.salary, departments.department_name
  FROM employees
  RIGHT JOIN departments ON employees.department_id = departments.department_id;
  ```

* **Expected Output**:

  * A complete list of employees and departments, with `NULL` values where no match exists between the two.

---

## **Submission Instructions**

* **Check** your queries and ensure they are correct.
* Save your SQL script with all your queries.
* Submit your script via the designated submission platform (if applicable).

---

## **Conclusion**

Today’s lab has focused on **Joins** and **Subqueries**, two essential techniques for combining and filtering data in relational databases. You should now feel comfortable writing and executing **INNER**, **LEFT**, and **RIGHT JOINs**, as well as creating **subqueries** for complex data retrieval.

---

This lab provides hands-on practice for working with the core concepts of **Joins** and **Subqueries**, helping learners develop a deep understanding of relational database management and SQL querying. 