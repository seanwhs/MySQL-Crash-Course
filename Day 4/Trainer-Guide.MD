# **Trainer Guide - Day 4: Joins and Subqueries**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 4

---

## **Objective for Trainers**

The goal for Day 4 is to guide learners through the concepts of **Joins** and **Subqueries**, two essential techniques for working with relational databases. By the end of the day, learners should be able to:

1. Understand and apply **INNER JOIN**, **LEFT JOIN**, **RIGHT JOIN**, and **FULL JOIN** (conceptually).
2. Write and execute **subqueries** in various SQL clauses, including **WHERE**, **SELECT**, and **FROM**.
3. Combine **Joins** and **Subqueries** to solve more complex problems and retrieve data from multiple related tables.

---

## **Session Outline**

### **1. Introduction to Joins (15 min)**

* **Objective**: Explain the purpose and use cases of joins in relational databases.

* **Key Points**:

  * **What is a join?**

    * Joins allow you to retrieve and combine data from two or more tables in a relational database.
    * Joins help when data is normalized and spread across multiple tables.
  * **Why Joins Matter?**

    * Without joins, you would have to query each table separately, leading to duplication and inconsistencies.
    * Joins allow you to work with more meaningful data by linking tables together.

* **Delivery Tip**: Use visual aids, such as Venn diagrams, to illustrate the concept of **INNER JOIN**, **LEFT JOIN**, and **RIGHT JOIN**.

* **Discussion**: Ask learners to consider a scenario where they need to retrieve employee and department details. How would they solve this problem using joins?

---

### **2. Types of Joins (30 min)**

* **Objective**: Teach the different types of joins (INNER, LEFT, RIGHT) with real-world examples.

* **Content to Cover**:

  1. **INNER JOIN**:

     * Combines rows from both tables where there is a match.
     * Non-matching rows are excluded.
     * Example Query:

       ```sql
       SELECT employees.name, departments.department_name
       FROM employees
       INNER JOIN departments
       ON employees.department_id = departments.department_id;
       ```

  2. **LEFT JOIN (OUTER JOIN)**:

     * Includes all rows from the left table, and matching rows from the right table.
     * Non-matching rows from the right table are returned as `NULL`.
     * Example Query:

       ```sql
       SELECT employees.name, departments.department_name
       FROM employees
       LEFT JOIN departments
       ON employees.department_id = departments.department_id;
       ```

  3. **RIGHT JOIN (OUTER JOIN)**:

     * Includes all rows from the right table, and matching rows from the left table.

     * Non-matching rows from the left table are returned as `NULL`.

     * Example Query:

       ```sql
       SELECT employees.name, departments.department_name
       FROM employees
       RIGHT JOIN departments
       ON employees.department_id = departments.department_id;
       ```

  * **Activity**: Walk learners through an example using sample data (e.g., `employees` and `departments`).
  * **Visualization**: Show Venn diagrams for each type of join to highlight how data is retrieved.

* **Delivery Tip**: After explaining each join type, ask learners to provide their own use cases for when they might use each join.

---

### **3. Subqueries (30 min)**

* **Objective**: Introduce learners to **subqueries**, how to write them, and how to use them in various SQL clauses.

* **Key Points**:

  * **What is a subquery?**

    * A subquery is a query nested inside another query, which allows you to perform more complex operations, such as filtering, aggregation, or performing calculations.
  * **Where can subqueries be used?**

    * In the **SELECT**, **WHERE**, **FROM**, and **HAVING** clauses.

* **Types of Subqueries**:

  1. **Single-row Subqueries** (return a single value):

     * Example: Find the employee with the highest salary:

       ```sql
       SELECT name
       FROM employees
       WHERE salary = (SELECT MAX(salary) FROM employees);
       ```

  2. **Multi-row Subqueries** (return multiple values):

     * Example: Find employees who work in departments with a budget greater than $500,000:

       ```sql
       SELECT name
       FROM employees
       WHERE department_id IN (SELECT department_id FROM departments WHERE budget > 500000);
       ```

  3. **Correlated Subqueries** (reference outer query values):

     * Example: Find employees who earn more than the average salary of their department:

       ```sql
       SELECT e.name
       FROM employees e
       WHERE e.salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);
       ```

* **Activity**:

  * Have learners write a **subquery** to filter out employees earning more than the average salary in their respective department.
  * Provide additional subquery examples and have them identify whether the subquery is single-row, multi-row, or correlated.

* **Delivery Tip**: Emphasize the difference between correlated and non-correlated subqueries. A correlated subquery references columns from the outer query, while a non-correlated subquery operates independently.

---

### **4. Combining Joins and Subqueries (20 min)**

* **Objective**: Teach learners how to combine joins and subqueries to solve complex queries.

* **Key Points**:

  * Subqueries can be used inside joins to retrieve values that are not directly stored in the table.
  * Example: Retrieve the department with the highest average salary:

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

* **Activity**:

  * Provide a problem where learners need to write a query that combines both joins and subqueries. Example: Retrieve employees who earn more than the average salary in their department.
  * Allow learners to practice this in groups and ask them to share their solutions.

* **Delivery Tip**: Walk learners through a combined join and subquery example step by step, highlighting how the subquery works inside the `WHERE` clause.

---

### **5. Hands-On Lab (30 min)**

* **Objective**: Reinforce the concepts through hands-on practice.

* **Lab Tasks**:

  1. Use **INNER JOIN** and **LEFT JOIN** to retrieve employee and department details.
  2. Write a **subquery** to find employees earning more than the average salary in their department.
  3. Combine **joins** and **subqueries** to solve a problem, such as finding the department with the highest average salary.

* **Delivery Tip**: Walk around the room and provide assistance to learners as they work through the exercises. Answer questions and guide them through any problems they encounter.

---

### **6. Wrap-up and Review (15 min)**

* **Objective**: Summarize key concepts and reinforce the learning from the day.

* **Key Points**:

  * **Joins**: They allow you to combine related data from different tables. The most common types are **INNER JOIN**, **LEFT JOIN**, and **RIGHT JOIN**.
  * **Subqueries**: These are powerful tools for filtering, calculating, and manipulating data inside other queries.
  * **Combining Joins and Subqueries**: You can use both in the same query to solve more complex data retrieval problems.

* **Q&A**: Open the floor for any final questions. Clarify any confusion about joins, subqueries, or the combination of both.

* **Homework/Next Steps**:

  * Suggest that learners try out additional exercises using **joins** and **subqueries** in different contexts (e.g., working with more complex datasets).
  * Mention that tomorrow’s session will cover **Database Normalization** and **Best Practices** for designing efficient databases.

---

## **Additional Tips for Trainers**

1. **Be Patient**: Joins and subqueries can be challenging for beginners. Take time to explain each concept with simple examples before moving on to more complex scenarios.
2. **Encourage Group Work**: Encourage learners to work in small groups during the hands-on lab. Collaborative problem-solving helps reinforce learning.
3. **Use Real-World Examples**: Whenever possible, tie the concepts back to real-world scenarios (e.g., retrieving employee and department data, analyzing sales performance, etc.).
4. **Visual Aids**: Use Venn diagrams to show the behavior of different types of joins. This helps learners visualize the intersection and union of tables.
5. **Practice Exercises**: Provide learners with extra practice queries or small challenges after class to ensure they get enough practice with joins and subqueries.

---

## **Conclusion**

By the end of Day 4, learners will have a solid understanding of **Joins** and **Subqueries** and will be able to use these tools to retrieve and analyze data from relational databases. Your role as a trainer is to ensure that learners grasp these concepts, practice writing SQL queries, and apply their new knowledge to real-world problems.

