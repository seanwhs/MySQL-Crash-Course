# **Day 6: Lab Exercise - Database Indexing and Query Optimization**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 6
**Topic**: Database Indexing and Query Optimization

---

### **Objective**

The goal of this lab is to give you hands-on experience with creating and managing indexes, using the `EXPLAIN` command to analyze query performance, and optimizing queries for better speed.

By the end of this lab, you should be able to:

1. Create, modify, and drop indexes on MySQL tables.
2. Use `EXPLAIN` to analyze the execution plan of SQL queries.
3. Optimize queries using indexes and compare performance.

---

### **Pre-requisites**

Ensure that you have access to a MySQL environment and a sample database like `sakila` or `employees`. The tables you’ll be working with include `employees`, `departments`, and `orders`.

---

## **Lab Tasks**

### **Task 1: Creating Indexes on Individual Columns**

1. **Objective**: Create a simple index on a column frequently used in queries.

2. **Instructions**:

   * Open your MySQL environment and connect to your database.
   * Use the `employees` table (or any table with sufficient data).
   * Create an index on the `last_name` column of the `employees` table:

   ```sql
   CREATE INDEX idx_last_name ON employees (last_name);
   ```

3. **Test the Query**:

   * Run a `SELECT` query to retrieve all employees with the last name 'Smith':

   ```sql
   SELECT * FROM employees WHERE last_name = 'Smith';
   ```

4. **Using `EXPLAIN`**:

   * Before and after creating the index, use `EXPLAIN` to check how the query is executed.

   ```sql
   EXPLAIN SELECT * FROM employees WHERE last_name = 'Smith';
   ```

   * Compare the execution plan:

     * Without index, MySQL may perform a full table scan (`ALL` in the `type` column).
     * After the index is created, you should see a more efficient scan type, such as `ref`.

---

### **Task 2: Creating a Composite Index**

1. **Objective**: Create an index on multiple columns that are frequently queried together.

2. **Instructions**:

   * Use the `orders` table, which contains columns like `customer_id` and `order_date`.
   * Create a composite index on both the `customer_id` and `order_date` columns to optimize queries filtering by both fields:

   ```sql
   CREATE INDEX idx_customer_order_date ON orders (customer_id, order_date);
   ```

3. **Test the Query**:

   * Run a query to find orders for a specific customer within a certain date range:

   ```sql
   SELECT * FROM orders 
   WHERE customer_id = 1001 AND order_date BETWEEN '2023-01-01' AND '2023-12-31';
   ```

4. **Using `EXPLAIN`**:

   * Run the query with `EXPLAIN` before and after creating the composite index:

   ```sql
   EXPLAIN SELECT * FROM orders 
   WHERE customer_id = 1001 AND order_date BETWEEN '2023-01-01' AND '2023-12-31';
   ```

   * Check whether MySQL uses the composite index to optimize the query.

---

### **Task 3: Dropping an Index**

1. **Objective**: Learn how to drop an index when it's no longer needed.

2. **Instructions**:

   * Drop the index `idx_last_name` that you created in Task 1:

   ```sql
   DROP INDEX idx_last_name ON employees;
   ```

3. **Test the Query Again**:

   * After dropping the index, run the same `SELECT` query from Task 1 to see if the performance changes:

   ```sql
   SELECT * FROM employees WHERE last_name = 'Smith';
   ```

4. **Using `EXPLAIN`**:

   * Use `EXPLAIN` to check the execution plan again and observe any differences. You should notice that without the index, MySQL may perform a full table scan once more.

   ```sql
   EXPLAIN SELECT * FROM employees WHERE last_name = 'Smith';
   ```

---

### **Task 4: Analyzing Query Performance with `EXPLAIN`**

1. **Objective**: Use `EXPLAIN` to analyze the performance of a query before and after optimizing it.

2. **Instructions**:

   * Start with a slow query. For example, find all employees working in a specific department:

   ```sql
   SELECT * FROM employees WHERE department_id = 3;
   ```

3. **Using `EXPLAIN`**:

   * Run the query with `EXPLAIN` to see the execution plan:

   ```sql
   EXPLAIN SELECT * FROM employees WHERE department_id = 3;
   ```

   * Check the `type` column to see if a full table scan is happening (`ALL`).

4. **Optimizing the Query**:

   * Create an index on the `department_id` column:

   ```sql
   CREATE INDEX idx_department_id ON employees (department_id);
   ```

5. **Test the Optimized Query**:

   * Run the same query again to check if it’s optimized:

   ```sql
   EXPLAIN SELECT * FROM employees WHERE department_id = 3;
   ```

6. **Compare the Results**:

   * Compare the execution plan before and after optimization. You should notice that MySQL now uses an index (`ref` or `range`) to speed up the query.

---

### **Task 5: Query Optimization Best Practices**

1. **Objective**: Apply best practices for query optimization in MySQL.

2. **Instructions**:

   * Write a query that retrieves all employees from a specific department and orders them by their last name:

   ```sql
   SELECT * FROM employees WHERE department_id = 3 ORDER BY last_name;
   ```

3. **Optimizing the Query**:

   * Consider adding indexes on columns used in the `WHERE` clause (`department_id`) and the `ORDER BY` clause (`last_name`).

   ```sql
   CREATE INDEX idx_dept_lastname ON employees (department_id, last_name);
   ```

4. **Test the Optimized Query**:

   * After creating the index, re-run the query to ensure it’s faster and the query execution plan is efficient:

   ```sql
   EXPLAIN SELECT * FROM employees WHERE department_id = 3 ORDER BY last_name;
   ```

5. **Conclusion**:

   * Analyze the performance improvement and check if `EXPLAIN` now shows the index usage in the `key` column.

---

### **Conclusion and Next Steps**

* **Review**: Throughout the lab, you’ve learned how to create, modify, and drop indexes in MySQL, as well as how to analyze query performance using `EXPLAIN`.
* **Key Takeaways**:

  * Indexes are essential for improving query performance, especially for large datasets.
  * Use `EXPLAIN` to analyze and optimize your queries, ensuring they use indexes effectively.
  * Apply indexing best practices to reduce query execution time and improve overall database performance.

---

### **Further Exploration**

* **Challenge**: Try creating a composite index with more than two columns and see how it affects complex queries.
* **Explore**: Research more advanced indexing techniques, such as **full-text indexes** and **spatial indexes**, depending on your project needs.

---

This **Lab Exercise** gives learners practical experience with creating and managing indexes, analyzing performance, and optimizing queries in MySQL. The goal is to ensure learners can confidently use these techniques in real-world scenarios. 