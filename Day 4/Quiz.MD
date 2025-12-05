# **Quiz - Day 4: Joins and Subqueries**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 4

---

## **Part 1: Multiple Choice Questions (MCQs)**

### **1. Which SQL join will return only matching rows from two tables?**

a) LEFT JOIN
b) RIGHT JOIN
c) INNER JOIN
d) FULL JOIN

### **2. Which of the following joins is used to return all rows from the left table and matching rows from the right table?**

a) INNER JOIN
b) LEFT JOIN
c) RIGHT JOIN
d) FULL JOIN

### **3. Which of the following queries retrieves all employees along with their department names, including employees who don't belong to any department?**

a) `INNER JOIN`
b) `LEFT JOIN`
c) `RIGHT JOIN`
d) `FULL JOIN`

### **4. What will the following query return?**

```sql
SELECT employees.name, employees.salary, departments.department_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;
```

a) All employees and their respective departments
b) All departments and the employees in those departments
c) Only departments with employees
d) Departments with no employees and their employee details as `NULL`

### **5. Which of the following is an example of a correlated subquery?**

a) A subquery used in the `WHERE` clause
b) A subquery that references a column from the outer query
c) A subquery used in the `SELECT` clause
d) A subquery that runs independently of the outer query

---

## **Part 2: True or False**

### **6. A RIGHT JOIN will return all rows from the right table and matching rows from the left table.**

* True
* False

### **7. An INNER JOIN will return only rows where there is a match in both tables.**

* True
* False

### **8. A subquery can be used in the `SELECT` clause to perform calculations like `AVG()` or `MAX()`.**

* True
* False

### **9. A correlated subquery executes once for each row in the outer query.**

* True
* False

### **10. FULL JOIN is natively supported by MySQL and returns all rows from both tables, even if there is no match.**

* True
* False

---

## **Part 3: SQL Query Writing**

### **11. Write an SQL query to retrieve the names of employees who work in the 'Engineering' department and earn more than $80,000.**

### **12. Write an SQL query to retrieve the department names along with the highest salary in each department. Use a subquery in the `SELECT` clause.**

### **13. Write an SQL query to retrieve the names of employees who earn more than the average salary of their respective departments.**

### **14. Write an SQL query to retrieve the department name with the highest average salary. Use a subquery to calculate the average salary for each department.**

### **15. Write an SQL query to retrieve all employees and departments, including those that don’t have a match. Use a combination of `LEFT JOIN` and `RIGHT JOIN` to simulate a FULL JOIN.**

---

## **Part 4: Scenario-Based Questions**

### **16. Scenario**:

You have two tables: `employees` and `departments`. The `employees` table contains an employee’s `name`, `salary`, and `department_id`, and the `departments` table contains a `department_name` and `department_id`.

* What SQL query will return a list of employees and their departments, where employees without departments will still appear in the result with `NULL` for the department?

### **17. Scenario**:

You have a table `employees` with columns `employee_id`, `name`, `salary`, and `department_id`, and another table `departments` with columns `department_id` and `department_name`.

* How would you retrieve the department name and the highest salary in each department using a **subquery** in the `SELECT` clause?

---

## **Answer Key**

### **Part 1: Multiple Choice Questions (MCQs)**

1. **c)** INNER JOIN
2. **b)** LEFT JOIN
3. **b)** LEFT JOIN
4. **b)** All departments and the employees in those departments
5. **b)** A subquery that references a column from the outer query

### **Part 2: True or False**

6. **True**
7. **True**
8. **True**
9. **True**
10. **False** (MySQL does not support FULL JOIN natively)

### **Part 3: SQL Query Writing**

11.

```sql
SELECT name 
FROM employees 
WHERE department_id = (SELECT department_id FROM departments WHERE department_name = 'Engineering') 
AND salary > 80000;
```

12.

```sql
SELECT department_name, 
       (SELECT MAX(salary) FROM employees WHERE employees.department_id = departments.department_id) AS highest_salary
FROM departments;
```

13.

```sql
SELECT e.name
FROM employees e
WHERE e.salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);
```

14.

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

15.

```sql
SELECT employees.name, employees.salary, departments.department_name
FROM employees
LEFT JOIN departments ON employees.department_id = departments.department_id
UNION
SELECT employees.name, employees.salary, departments.department_name
FROM employees
RIGHT JOIN departments ON employees.department_id = departments.department_id;
```

### **Part 4: Scenario-Based Questions**

16. **Answer**:
    You would use a **LEFT JOIN** to include employees who don’t have a department.

```sql
SELECT employees.name, departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;
```

17. **Answer**:
    To retrieve the department name and highest salary in each department using a subquery, you can use the following query:

```sql
SELECT departments.department_name,
       (SELECT MAX(salary) FROM employees WHERE employees.department_id = departments.department_id) AS highest_salary
FROM departments;
```

---

## **Conclusion**

This quiz reinforces the key concepts of **Joins** and **Subqueries**. The combination of multiple-choice questions, SQL writing tasks, and scenario-based questions ensures that learners can both understand the theory and apply the concepts in practice.

