# **Quiz - Day 5: Grouping and Aggregating Data**

**Instructions**: Answer the following multiple-choice and short-answer questions. Choose the best answer for multiple-choice questions. For short-answer questions, write your answers in the space provided.

---

### **1. Multiple Choice: What does the `GROUP BY` clause do in SQL?**

a) It sorts the data in ascending or descending order.
b) It groups rows that have the same values in specified columns into summary rows.
c) It deletes data from a table.
d) It filters rows based on a condition.

---

### **2. Multiple Choice: Which of the following is NOT an aggregate function in SQL?**

a) `COUNT()`
b) `SUM()`
c) `MIN()`
d) `UPDATE()`

---

### **3. Multiple Choice: Which SQL clause is used to filter groups after aggregation?**

a) `WHERE`
b) `HAVING`
c) `ORDER BY`
d) `GROUP BY`

---

### **4. Multiple Choice: What would the following SQL query return?**

```sql
SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id
HAVING total_salary > 10000;
```

a) The total salary in departments with more than 10 employees.
b) The total salary of all employees across departments.
c) The total salary of departments where the sum exceeds 10,000.
d) The total salary of departments where the number of employees exceeds 10.

---

### **5. Short Answer: What is the purpose of the `HAVING` clause, and how does it differ from `WHERE`?**

---

### **6. Short Answer: Write a SQL query to calculate the average salary of employees in each department.**

---

### **7. Multiple Choice: What is the result of the following SQL query?**

```sql
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id
HAVING COUNT(*) <= 3;
```

a) It will return departments with 3 or fewer employees.
b) It will return departments with more than 3 employees.
c) It will return all departments without filtering.
d) It will return an error because `HAVING` is used incorrectly.

---

### **8. Multiple Choice: Which of the following SQL queries correctly combines `GROUP BY` with `JOIN` to find the total salary per department, including department names?**

a)

```sql
SELECT department_name, SUM(salary) AS total_salary
FROM employees
GROUP BY department_name;
```

b)

```sql
SELECT department_name, SUM(salary) AS total_salary
FROM employees
JOIN departments ON employees.department_id = departments.department_id
GROUP BY department_name;
```

c)

```sql
SELECT department_id, COUNT(salary) AS total_salary
FROM employees
GROUP BY department_id;
```

d)

```sql
SELECT department_name, COUNT(salary) AS total_salary
FROM employees
JOIN departments ON employees.department_id = departments.department_id
GROUP BY department_id;
```

---

### **9. Short Answer: Explain how you can filter the results of a `GROUP BY` query using `HAVING`.**

---

### **10. True/False: The `COUNT()` function can be used with non-numeric columns, such as counting the number of rows with a specific value in a column.**

---

### **11. Short Answer: What will be the result of the following SQL query?**

```sql
SELECT department_id, AVG(salary) AS avg_salary
FROM employees
GROUP BY department_id
HAVING AVG(salary) > 5000;
```

---

### **12. Multiple Choice: Which of the following queries would return the department with the highest total salary?**

a)

```sql
SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id
ORDER BY total_salary DESC
LIMIT 1;
```

b)

```sql
SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id
HAVING SUM(salary) = MAX(salary);
```

c)

```sql
SELECT department_id, COUNT(salary) AS total_salary
FROM employees
GROUP BY department_id
ORDER BY COUNT(salary) DESC;
```

d)

```sql
SELECT department_id, MAX(salary) AS total_salary
FROM employees
GROUP BY department_id;
```

---

## **Answer Key:**

1. **b)** It groups rows that have the same values in specified columns into summary rows.
2. **d)** `UPDATE()` is not an aggregate function.
3. **b)** `HAVING` is used to filter groups after aggregation.
4. **c)** The total salary of departments where the sum exceeds 10,000.
5. **(Learner’s Response)** The `HAVING` clause is used to filter the results after they have been grouped and aggregated, unlike `WHERE`, which filters rows before aggregation.
6. **(Learner’s Response)**

```sql
SELECT department_id, AVG(salary) AS avg_salary
FROM employees
GROUP BY department_id;
```

7. **a)** It will return departments with 3 or fewer employees.
8. **b)** This query combines `GROUP BY` with `JOIN` to calculate the total salary per department, including department names.
9. **(Learner’s Response)** You can filter the results of a `GROUP BY` query using `HAVING` by applying conditions on aggregate functions, such as counting or summing.
10. **True**: `COUNT()` can be used with non-numeric columns, such as counting the number of employees in a department.
11. **(Learner’s Response)** It will return departments where the average salary is greater than 5,000.
12. **a)** This query will return the department with the highest total salary by ordering the result in descending order and limiting it to one row.

---

This quiz will assess learners' understanding of **grouping**, **aggregating**, and **filtering** data, as well as their ability to work with SQL queries that involve multiple tables and aggregate functions.
