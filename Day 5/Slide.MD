# **Slide 1: Introduction to Day 5 - Grouping and Aggregating Data**

## **Welcome to Day 5**

* **Topic**: Grouping and Aggregating Data in SQL
* **Objective**: Learn how to use `GROUP BY`, aggregate functions, and `HAVING` to summarize and analyze data.

---

# **Slide 2: What is GROUP BY?**

## **GROUP BY**

* **Definition**: Groups rows that have the same values into summary rows.
* **Purpose**: It’s used to aggregate data, such as counting the number of records, summing values, or finding averages.
* **Common Use**: Generating reports and performing data analysis.

---

# **Slide 3: Example of GROUP BY**

## **GROUP BY Example**

Suppose we have a table of employees:

| Employee ID | Name  | Department ID | Salary |
| ----------- | ----- | ------------- | ------ |
| 1           | Alice | 1             | 5000   |
| 2           | Bob   | 2             | 6000   |
| 3           | Carol | 1             | 7000   |
| 4           | Dave  | 3             | 8000   |

### Query: **Group employees by Department ID and count the number of employees per department**

```sql
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id;
```

---

# **Slide 4: Aggregate Functions**

## **Common Aggregate Functions**

1. **`COUNT()`**: Returns the number of rows.

   * Example: Count employees in each department.
2. **`SUM()`**: Returns the sum of a numeric column.

   * Example: Calculate total salary in each department.
3. **`AVG()`**: Returns the average of a numeric column.

   * Example: Find the average salary in each department.
4. **`MIN()`**: Returns the minimum value.

   * Example: Find the employee with the lowest salary.
5. **`MAX()`**: Returns the maximum value.

   * Example: Find the employee with the highest salary.

---

# **Slide 5: Using Aggregate Functions**

## **Example 1: COUNT()**

### Count the number of employees in each department:

```sql
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id;
```

## **Example 2: SUM()**

### Sum of salaries for each department:

```sql
SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id;
```

---

# **Slide 6: Filtering Groups with HAVING**

## **HAVING vs WHERE**

* **WHERE**: Filters rows before aggregation.
* **HAVING**: Filters groups after aggregation.

## **Example**: Find departments with more than 3 employees:

```sql
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id
HAVING COUNT(*) > 3;
```

---

# **Slide 7: Combining GROUP BY with Joins**

## **Using Joins with GROUP BY**

* You can combine `GROUP BY` with `JOIN` to aggregate data from multiple related tables.

### Example: Find total salary per department, including department names:

```sql
SELECT departments.department_name, SUM(employees.salary) AS total_salary
FROM employees
INNER JOIN departments ON employees.department_id = departments.department_id
GROUP BY departments.department_name;
```

---

# **Slide 8: Real-World Use Case: Sales Report**

## **Example**: Calculate total sales by region and find regions with sales over $1,000,000.

* **Scenario**: We have a `sales` table with `region`, `sales_amount`, and `date`.

```sql
SELECT region, SUM(sales_amount) AS total_sales
FROM sales
GROUP BY region
HAVING SUM(sales_amount) > 1000000;
```

---

# **Slide 9: Summary of Key Concepts**

### **Key Concepts**:

* **`GROUP BY`**: Groups rows based on a column or set of columns.
* **Aggregate Functions**: `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`.
* **`HAVING`**: Filters groups after they have been aggregated.
* **`JOIN` + `GROUP BY`**: Combine data from multiple tables and aggregate results.

---

# **Slide 10: Lab Exercises**

## **Lab Tasks**:

1. Use `GROUP BY` and `COUNT()` to find the number of employees in each department.
2. Use `GROUP BY` and `SUM()` to calculate the total salary for each department.
3. Use `HAVING` to find departments with more than 5 employees.
4. Combine `JOIN` and `GROUP BY` to find the total salary by department name.

---

# **Slide 11: Q&A**

### **Any Questions?**

* Feel free to ask anything about today’s concepts.

---

# **Slide 12: Wrap-up**

## **What’s Next?**

* In the next session, we will cover **Subqueries and Complex Joins**.
* Keep practicing with real-world datasets to solidify your understanding.

