# **Quiz - Day 6: Database Indexing and Query Optimization**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 6
**Topic**: Database Indexing and Query Optimization

---

### **Section 1: Multiple Choice Questions**

1. **What is the primary purpose of an index in a database?**

   a) To store data in a table
   b) To speed up data retrieval operations
   c) To enforce referential integrity
   d) To perform complex joins automatically

   **Answer**: b) To speed up data retrieval operations

2. **Which of the following statements is true about composite indexes?**

   a) Composite indexes can only be created on two columns.
   b) A composite index is useful when a query involves multiple columns in the `WHERE` clause.
   c) Composite indexes always improve the performance of `UPDATE` queries.
   d) Composite indexes are automatically created for all `JOIN` operations.

   **Answer**: b) A composite index is useful when a query involves multiple columns in the `WHERE` clause.

3. **What is the output of the `EXPLAIN` statement for a query that performs a full table scan?**

   a) `range`
   b) `index`
   c) `ALL`
   d) `ref`

   **Answer**: c) `ALL`

4. **Which of the following types of indexes ensures that all values in a column are unique?**

   a) Primary Key Index
   b) Unique Index
   c) Full-Text Index
   d) Foreign Key Index

   **Answer**: b) Unique Index

5. **Which of the following statements about indexes is true?**

   a) Indexes always improve both read and write operations.
   b) Indexes improve query performance but can slow down write operations.
   c) Indexes always make the database slower.
   d) Indexes are only useful for SELECT queries.

   **Answer**: b) Indexes improve query performance but can slow down write operations.

---

### **Section 2: True/False Questions**

6. **Indexes are only helpful for queries that use `JOIN` operations.**

   **Answer**: False
   **Explanation**: Indexes are beneficial for any query that filters or sorts data (e.g., using `WHERE`, `ORDER BY`, `GROUP BY`, or `JOIN`).

7. **The `EXPLAIN` keyword can be used to analyze the execution plan of a query and understand how MySQL is processing it.**

   **Answer**: True

8. **Creating indexes on columns with low cardinality (such as a `gender` field) generally improves query performance.**

   **Answer**: False
   **Explanation**: Indexes on columns with low cardinality (few distinct values) are not very useful and may not improve performance.

9. **Composite indexes can only be used when filtering by all columns in the index.**

   **Answer**: True
   **Explanation**: For a composite index to be used efficiently, the query should filter by the leading (first) column(s) in the index.

10. **The `EXPLAIN` command helps identify whether an index is being used in a query and provides insights into query optimization.**

**Answer**: True

---

### **Section 3: Practical/Short Answer Questions**

11. **Create an index on the `email` column of a `users` table. Write the SQL query to do so.**

**Answer**:

```sql
CREATE INDEX idx_email ON users (email);
```

12. **You are given a query that performs slowly due to a large dataset. The query is:**

```sql
SELECT * FROM employees WHERE department_id = 3 ORDER BY last_name;
```

* What would you recommend to optimize the query?
* Provide the SQL to create the necessary index to improve performance.

**Answer**:

* **Recommendation**: Create a composite index on `department_id` and `last_name` to speed up filtering by department and ordering by last name.
* **SQL to create the index**:

```sql
CREATE INDEX idx_dept_lastname ON employees (department_id, last_name);
```

13. **After running a query with `EXPLAIN`, you notice that MySQL is doing a full table scan (`ALL`). What does this indicate, and what can you do to improve the query performance?**

**Answer**:

* **Explanation**: A full table scan indicates that no index is being used for the query, and MySQL is scanning all rows in the table.
* **Improvement**: Consider creating an index on the column(s) involved in the `WHERE` clause or `ORDER BY` clause to speed up the query. For example, if filtering by `department_id`, create an index on that column:

```sql
CREATE INDEX idx_department_id ON employees (department_id);
```

14. **You have a query with the following `EXPLAIN` output:**

| id | select_type | table     | type | key  | rows | Extra       |
| -- | ----------- | --------- | ---- | ---- | ---- | ----------- |
| 1  | SIMPLE      | employees | ALL  | NULL | 1000 | Using where |

* What does the `ALL` in the `type` column indicate, and how can you improve the query performance?

**Answer**:

* The `ALL` in the `type` column indicates a full table scan, which is inefficient for large tables.
* **Improvement**: Create an index on the `WHERE` condition column(s) to optimize the query. For example, if filtering by `department_id`:

```sql
CREATE INDEX idx_department_id ON employees (department_id);
```

15. **You have optimized a query by creating an index on a column, but after executing the query again, you find that the performance has not improved. What could be the reason, and what should you check next?**

**Answer**:

* **Reason**: There may be multiple reasons, such as:

  * The query might still not be using the index due to how the query is written (e.g., using functions or non-SARGable conditions in the `WHERE` clause).
  * The index might not be useful for that specific query if the column has low cardinality.
* **Next Steps**: Use `EXPLAIN` to analyze the query execution plan again, ensuring that the index is being used. Also, check if the index is created on the correct columns involved in filtering or sorting.

---

### **Section 4: Bonus Question (Advanced)**

16. **You have a table with a `TEXT` column that you frequently search for specific keywords. What type of index would you create for this scenario, and why?**

**Answer**:

* **Answer**: Create a **full-text index** on the `TEXT` column. This type of index is designed for efficient text searches, such as finding specific keywords or phrases in a large body of text.
* **SQL**:

```sql
CREATE FULLTEXT INDEX idx_text_column ON table_name (text_column);
```

---

### **Quiz Completion**

* **Scoring**: Each multiple-choice question and true/false question is worth 1 point. Practical questions should be scored based on accuracy and completeness.

* **Time Limit**: 20-30 minutes.

---

### **Review and Discussion (Optional)**

* After the quiz, spend some time reviewing the answers with the learners. Focus on any areas of difficulty and discuss common misconceptions.
* Use the practical examples to show how learners can apply the concepts in real-world scenarios.

---

This **Day 6 Quiz** is designed to assess both theoretical knowledge and hands-on application. It provides a comprehensive review of indexing and query optimization concepts, and it will help learners reinforce the skills they’ve learned during the session. 