## **Slide Deck - Day 4: Joins and Subqueries**

### **Slide 1: Title Slide**

* **Title**: Day 4: Joins and Subqueries
* **Subtitle**: MySQL 1-Week Hands-On Crash Course
* **Presenter**: [Your Name]
* **Date**: [Insert Date]

---

### **Slide 2: Course Overview**

* **Course Overview**:

  * Quick recap of the course progress so far.
  * **Day 4 Focus**: Joins and Subqueries.
  * **Learning Outcomes**:

    * Combine data using different types of **Joins**.
    * Use **Subqueries** to solve complex data retrieval problems.

---

### **Slide 3: What are Joins?**

* **Definition**: Joins allow you to retrieve data from two or more tables in a single query.
* **Why Joins Matter**:

  * Relational databases often store data across multiple tables.
  * Joins help combine data from related tables efficiently.

---

### **Slide 4: Types of Joins**

* **INNER JOIN**: Combines rows from both tables where there’s a match.
* **LEFT JOIN (OUTER JOIN)**: Combines all rows from the left table, and matching rows from the right table.
* **RIGHT JOIN (OUTER JOIN)**: Combines all rows from the right table, and matching rows from the left table.
* **FULL JOIN**: Not natively supported in MySQL (but can be mimicked using `LEFT` and `RIGHT JOIN`).

---

### **Slide 5: INNER JOIN Example**

* **Syntax**:

  ```sql
  SELECT columns
  FROM table1
  INNER JOIN table2
  ON table1.column = table2.column;
  ```

* **Explanation**:

  * The query returns only matching rows from both tables.
  * **Example**:

    * `employees` table and `departments` table, where the join condition matches the `department_id`.

* **Visual Aid**:

  * Venn diagram showing intersection of two tables (INNER JOIN).

---

### **Slide 6: LEFT JOIN Example**

* **Syntax**:

  ```sql
  SELECT columns
  FROM table1
  LEFT JOIN table2
  ON table1.column = table2.column;
  ```

* **Explanation**:

  * Returns all rows from the **left** table, and matching rows from the **right** table.
  * If there is no match, returns `NULL` for the right table’s columns.

* **Visual Aid**:

  * Venn diagram showing the left table plus the intersection with the right table.

---

### **Slide 7: RIGHT JOIN Example**

* **Syntax**:

  ```sql
  SELECT columns
  FROM table1
  RIGHT JOIN table2
  ON table1.column = table2.column;
  ```

* **Explanation**:

  * Returns all rows from the **right** table, and matching rows from the **left** table.
  * If there is no match, returns `NULL` for the left table’s columns.

* **Visual Aid**:

  * Venn diagram showing the right table plus the intersection with the left table.

---

### **Slide 8: FULL JOIN (Conceptual)**

* **Definition**: Retrieves all records when there is a match in either the left or right table.

* **Note**: MySQL doesn’t support `FULL JOIN` directly, but you can combine `LEFT JOIN` and `RIGHT JOIN` to achieve similar results.

* **Workaround Example**:

  ```sql
  SELECT columns
  FROM table1
  LEFT JOIN table2 ON table1.column = table2.column
  UNION
  SELECT columns
  FROM table1
  RIGHT JOIN table2 ON table1.column = table2.column;
  ```

---

### **Slide 9: When to Use Each Type of Join**

* **INNER JOIN**: When you only need matching rows from both tables.
* **LEFT JOIN**: When you need all rows from the left table and matching data from the right table.
* **RIGHT JOIN**: When you need all rows from the right table and matching data from the left table.
* **FULL JOIN**: When you need all rows from both tables, whether they match or not.

---

### **Slide 10: Introduction to Subqueries**

* **Definition**: A subquery is a query nested inside another query. It’s often used to perform complex filtering or data retrieval in multiple steps.

---

### **Slide 11: Subquery Syntax**

* **Single-Row Subquery**: Returns a single value (scalar).

  ```sql
  SELECT column
  FROM table
  WHERE column = (SELECT MAX(column) FROM table);
  ```

* **Multi-Row Subquery**: Returns multiple values.

  ```sql
  SELECT column
  FROM table
  WHERE column IN (SELECT column FROM table WHERE condition);
  ```

* **Correlated Subquery**: Depends on the outer query and is re-executed for each row in the outer query.

  ```sql
  SELECT column
  FROM table t
  WHERE t.column > (SELECT AVG(column) FROM table WHERE condition = t.condition);
  ```

---

### **Slide 12: Subqueries in the WHERE Clause**

* **Example**: Find employees who earn more than the average salary in their department.

  ```sql
  SELECT name
  FROM employees e
  WHERE salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);
  ```
* **Explanation**: The subquery calculates the average salary for each department, and the outer query returns employees earning more than that average.

---

### **Slide 13: Subqueries in the SELECT Clause**

* **Example**: Find the highest salary in each department.

  ```sql
  SELECT department_name, 
         (SELECT MAX(salary) FROM employees WHERE department_id = departments.department_id) AS highest_salary
  FROM departments;
  ```
* **Explanation**: The subquery retrieves the maximum salary for each department.

---

### **Slide 14: Combining Joins and Subqueries**

* **Example**: Retrieve the department with the highest average salary.

  ```sql
  SELECT department_name
  FROM departments
  WHERE department_id = (SELECT department_id
                          FROM employees
                          GROUP BY department_id
                          ORDER BY AVG(salary) DESC LIMIT 1);
  ```

---

### **Slide 15: Lab Exercise Introduction**

* **Goal**: Apply what you’ve learned to real-world data.
* **Tasks**:

  * Perform **INNER JOIN**, **LEFT JOIN**, and **RIGHT JOIN** queries.
  * Create **subqueries** to filter and aggregate data.
  * Combine **joins** and **subqueries** to solve complex data retrieval problems.

---

### **Slide 16: Recap and Key Takeaways**

* **Joins**: Allow combining related data from different tables.

  * **INNER JOIN**: Matches rows from both tables.
  * **LEFT JOIN**: Returns all rows from the left table.
  * **RIGHT JOIN**: Returns all rows from the right table.
* **Subqueries**: Help in complex data filtering and calculations.

  * Can be used in **SELECT**, **WHERE**, and **FROM** clauses.
* **Combining Joins and Subqueries**: Powerful for solving advanced data retrieval tasks.

---

### **Slide 17: Q&A**

* **Any Questions?**

  * Open the floor to questions and discussion.
  * Address any common points of confusion or deeper inquiries.

---

### **Slide 18: Next Steps**

* **Tomorrow’s Lesson**: Introduction to **Database Normalization** and **Best Practices** for efficient database design.

---

This **slide deck** provides a comprehensive yet digestible overview of **Joins** and **Subqueries**, ensuring that learners not only understand the syntax but also see practical examples and use cases. The slides are designed to be interactive with plenty of visual aids, like Venn diagrams, to help learners grasp complex concepts.

