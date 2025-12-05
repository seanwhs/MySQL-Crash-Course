# **MySQL 1-Week Crash Course Cheat Sheet**

### **General MySQL Commands**

* **Connect to MySQL**:

  ```bash
  mysql -u root -p
  ```
* **Show Databases**:

  ```sql
  SHOW DATABASES;
  ```
* **Use a Database**:

  ```sql
  USE <database_name>;
  ```
* **Show Tables**:

  ```sql
  SHOW TABLES;
  ```
* **Describe a Table**:

  ```sql
  DESCRIBE <table_name>;
  ```

---

### **Creating and Modifying Databases and Tables**

* **Create a Database**:

  ```sql
  CREATE DATABASE <database_name>;
  ```

* **Create a Table**:

  ```sql
  CREATE TABLE <table_name> (
      column1 datatype,
      column2 datatype,
      ...
  );
  ```

* **Add a Column to an Existing Table**:

  ```sql
  ALTER TABLE <table_name> ADD COLUMN <column_name> <datatype>;
  ```

* **Modify a Column**:

  ```sql
  ALTER TABLE <table_name> MODIFY COLUMN <column_name> <new_datatype>;
  ```

* **Drop a Column**:

  ```sql
  ALTER TABLE <table_name> DROP COLUMN <column_name>;
  ```

* **Drop a Table**:

  ```sql
  DROP TABLE <table_name>;
  ```

---

### **Data Manipulation (CRUD Operations)**

* **Insert Data**:

  ```sql
  INSERT INTO <table_name> (column1, column2, ...)
  VALUES (value1, value2, ...);
  ```

* **Update Data**:

  ```sql
  UPDATE <table_name> 
  SET column1 = value1, column2 = value2
  WHERE condition;
  ```

* **Delete Data**:

  ```sql
  DELETE FROM <table_name>
  WHERE condition;
  ```

* **Select Data**:

  ```sql
  SELECT column1, column2, ...
  FROM <table_name>
  WHERE condition
  ORDER BY column;
  ```

* **Select All Columns**:

  ```sql
  SELECT * FROM <table_name>;
  ```

---

### **Joins**

* **Inner Join**:

  ```sql
  SELECT * FROM table1
  INNER JOIN table2
  ON table1.id = table2.id;
  ```

* **Left Join** (All records from the left table):

  ```sql
  SELECT * FROM table1
  LEFT JOIN table2
  ON table1.id = table2.id;
  ```

* **Right Join** (All records from the right table):

  ```sql
  SELECT * FROM table1
  RIGHT JOIN table2
  ON table1.id = table2.id;
  ```

* **Full Outer Join**:

  ```sql
  SELECT * FROM table1
  FULL OUTER JOIN table2
  ON table1.id = table2.id;
  ```

---

### **Transactions**

* **Start a Transaction**:

  ```sql
  START TRANSACTION;
  ```

* **Commit a Transaction**:

  ```sql
  COMMIT;
  ```

* **Rollback a Transaction**:

  ```sql
  ROLLBACK;
  ```

* **Savepoint** (Mark a point in the transaction):

  ```sql
  SAVEPOINT <savepoint_name>;
  ```

* **Rollback to Savepoint**:

  ```sql
  ROLLBACK TO SAVEPOINT <savepoint_name>;
  ```

* **Set Isolation Level**:

  ```sql
  SET TRANSACTION ISOLATION LEVEL <level>;
  ```

  **Isolation Levels**:

  * `READ UNCOMMITTED`
  * `READ COMMITTED`
  * `REPEATABLE READ`
  * `SERIALIZABLE`

---

### **Advanced SQL Features**

#### **Stored Procedures**

* **Create a Stored Procedure**:

  ```sql
  DELIMITER $$

  CREATE PROCEDURE <procedure_name>(param1 datatype, param2 datatype)
  BEGIN
      -- SQL statements here
  END $$

  DELIMITER ;
  ```

* **Call a Stored Procedure**:

  ```sql
  CALL <procedure_name>(param1_value, param2_value);
  ```

#### **Triggers**

* **Create a Trigger**:

  ```sql
  DELIMITER $$

  CREATE TRIGGER <trigger_name>
  BEFORE/AFTER INSERT/UPDATE/DELETE ON <table_name>
  FOR EACH ROW
  BEGIN
      -- Trigger logic here
  END $$

  DELIMITER ;
  ```

* **Example**: Set a `last_modified` timestamp on an update:

  ```sql
  CREATE TRIGGER update_employee_timestamp
  BEFORE UPDATE ON employees
  FOR EACH ROW
  SET NEW.last_modified = NOW();
  ```

#### **Views**

* **Create a View**:

  ```sql
  CREATE VIEW <view_name> AS
  SELECT column1, column2
  FROM <table_name>
  WHERE condition;
  ```

* **Query a View**:

  ```sql
  SELECT * FROM <view_name>;
  ```

* **Replace a View**:

  ```sql
  CREATE OR REPLACE VIEW <view_name> AS
  SELECT column1, column2
  FROM <table_name>;
  ```

---

### **Aggregate Functions**

* **COUNT**:

  ```sql
  SELECT COUNT(*) FROM <table_name>;
  ```

* **SUM**:

  ```sql
  SELECT SUM(column_name) FROM <table_name>;
  ```

* **AVG**:

  ```sql
  SELECT AVG(column_name) FROM <table_name>;
  ```

* **MAX**:

  ```sql
  SELECT MAX(column_name) FROM <table_name>;
  ```

* **MIN**:

  ```sql
  SELECT MIN(column_name) FROM <table_name>;
  ```

---

### **Other Useful Commands**

* **Group By**:

  ```sql
  SELECT column1, COUNT(*)
  FROM <table_name>
  GROUP BY column1;
  ```

* **Order By**:

  ```sql
  SELECT * FROM <table_name>
  ORDER BY column1 DESC;
  ```

* **Limit**:

  ```sql
  SELECT * FROM <table_name>
  LIMIT 10;
  ```

* **Distinct**:

  ```sql
  SELECT DISTINCT column1 FROM <table_name>;
  ```

* **Like** (Pattern matching):

  ```sql
  SELECT * FROM <table_name>
  WHERE column1 LIKE '%pattern%';
  ```

* **Between** (Range checking):

  ```sql
  SELECT * FROM <table_name>
  WHERE column1 BETWEEN 10 AND 20;
  ```

---

### **Indexing and Optimization**

* **Create an Index**:

  ```sql
  CREATE INDEX index_name
  ON <table_name> (column_name);
  ```

* **Show Indexes**:

  ```sql
  SHOW INDEXES FROM <table_name>;
  ```

* **Explain Query** (Optimization):

  ```sql
  EXPLAIN SELECT * FROM <table_name>;
  ```

---

### **Backup and Restore**

* **Backup a Database**:

  ```bash
  mysqldump -u root -p <database_name> > backup.sql
  ```

* **Restore a Database**:

  ```bash
  mysql -u root -p <database_name> < backup.sql
  ```

---

### **Key Concepts to Remember**

* **ACID**: Atomicity, Consistency, Isolation, Durability (Transaction properties).
* **Normalization**: Process of organizing data to reduce redundancy.
* **Joins**: Combine rows from two or more tables based on related columns.
* **Stored Procedures/Triggers/Views**: Automation and encapsulation of SQL logic for efficiency and reusability.
* **Indexes**: Speed up retrieval of data but may slow down inserts and updates.

---

### **Further Learning**

* **MySQL Documentation**: [https://dev.mysql.com/doc/](https://dev.mysql.com/doc/)
* **SQL Performance Optimization**: Look into query optimization techniques, indexing strategies, and performance tuning in MySQL.

---

This **Cheat Sheet** covers all the key concepts, SQL commands, and techniques that learners should have mastered by the end of the course. It serves as a quick reference for revising and practicing MySQL queries. 