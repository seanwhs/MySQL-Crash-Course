Here’s the **Day 2 Quiz** for your **MySQL 1-Week Hands-On Crash Course**. This quiz is designed to test learners’ understanding of the concepts covered on Day 2, including **tables**, **data types**, and **constraints** in MySQL.

---

# **Day 2 – Quiz: Tables & Data Types**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 2
**Duration:** 15–20 minutes
**Format:** Multiple Choice, True/False, Short Answer

---

## **Section 1: Conceptual Questions**

### **Q1.** What is the primary purpose of a `PRIMARY KEY` in a MySQL table?

A) To store a unique value for each row in a table
B) To store the data types for each column
C) To create a column that can store `NULL` values
D) To define the size of a column

**Answer:** A

---

### **Q2.** Which data type would you use for a column that stores a person’s full name?

A) `INT`
B) `VARCHAR`
C) `DATETIME`
D) `TEXT`

**Answer:** B

---

### **Q3.** True or False: You can insert a row into a table without providing a value for the `PRIMARY KEY` column if it has `AUTO_INCREMENT` set.

**Answer:** True

---

### **Q4.** Which of the following commands would you use to add a new column `phone_number` (VARCHAR(15)) to an existing `users` table?

A) `ALTER TABLE users ADD COLUMN phone_number VARCHAR(15);`
B) `ALTER TABLE users CREATE COLUMN phone_number VARCHAR(15);`
C) `ALTER TABLE users MODIFY COLUMN phone_number VARCHAR(15);`
D) `ALTER TABLE users UPDATE COLUMN phone_number VARCHAR(15);`

**Answer:** A

---

### **Q5.** When would you use the `UNIQUE` constraint on a column?

A) To prevent two rows from having the same value in that column
B) To prevent the column from storing any `NULL` values
C) To allow only text data in that column
D) To automatically assign values to the column

**Answer:** A

---

### **Q6.** True or False: The `DATETIME` data type can store both date and time values.

**Answer:** True

---

### **Q7.** What is the default value of a column with a `DEFAULT` constraint, if not explicitly set in an `INSERT` statement?

A) `NULL`
B) An empty string
C) The system’s current date and time
D) The value specified in the `DEFAULT` constraint

**Answer:** D

---

### **Q8.** Which of the following is NOT a valid MySQL data type for storing numeric values?

A) `INT`
B) `FLOAT`
C) `VARCHAR`
D) `DECIMAL`

**Answer:** C

---

## **Section 2: Practical/Commands**

### **Q9.** You need to create a `products` table with the following columns:

* `product_id`: INT, primary key, auto-increment
* `name`: VARCHAR(100)
* `price`: DECIMAL(10, 2)
* `created_at`: DATETIME, default to the current timestamp

What would the `CREATE TABLE` statement look like?

**Answer:**

```sql
CREATE TABLE products (
    product_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    price DECIMAL(10, 2),
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

---

### **Q10.** Which command would you use to modify the `status` column in the `users` table to disallow `NULL` values and set the default to `'active'`?

**Answer:**

```sql
ALTER TABLE users MODIFY COLUMN status VARCHAR(50) NOT NULL DEFAULT 'active';
```

---

### **Q11.** What does the following command do?

```sql
ALTER TABLE employees ADD COLUMN department VARCHAR(50) NOT NULL;
```

**Answer:**

* This command adds a new column called `department` to the `employees` table with a `VARCHAR(50)` data type and sets it as `NOT NULL` (it cannot store `NULL` values).

---

### **Q12.** True or False: If you try to insert a duplicate value into a column with a `UNIQUE` constraint, MySQL will generate an error.

**Answer:** True

---

## **Section 3: Scenario-Based Questions**

### **Q13.** You are asked to create a `students` table with the following requirements:

* A primary key column `student_id` that auto-increments
* A `first_name` and `last_name` column with `VARCHAR(100)` data type
* An `email` column with `VARCHAR(150)` data type, which must be unique
* A `date_of_birth` column with `DATE` data type
* A `status` column with `VARCHAR(50)` data type, which defaults to `'active'`

Write the SQL query to create this table.

**Answer:**

```sql
CREATE TABLE students (
    student_id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(100),
    last_name VARCHAR(100),
    email VARCHAR(150) UNIQUE,
    date_of_birth DATE,
    status VARCHAR(50) DEFAULT 'active'
);
```

---

### **Q14.** In a `customers` table, you want to add a new column `address` of type `TEXT`. However, you realize that you need to add this column after the `email` column. Which command will correctly modify the table?

**Answer:**

```sql
ALTER TABLE customers ADD COLUMN address TEXT AFTER email;
```

---

## **Section 4: Practical Troubleshooting**

### **Q15.** You tried to insert a new record into the `users` table without providing a value for the `email` column. The query failed, and you received an error message. What is the most likely cause?

**Answer:**

* The `email` column likely has a `NOT NULL` constraint, so it cannot accept `NULL` values. You must provide a value for this column when inserting data, unless it has a `DEFAULT` constraint.

---

### **Q16.** You accidentally inserted a record into the `employees` table with a duplicate email value. You want to remove the duplicate record without affecting the other data. What should you do?

**Answer:**

* You can delete the duplicate record using a `DELETE` query, such as:

```sql
DELETE FROM employees WHERE email = 'duplicate@example.com' LIMIT 1;
```

* Alternatively, you could update the `email` column to be unique before attempting to insert new data, ensuring no duplicates in the future.

---

## **Quiz Completion**

Please submit your answers to the quiz and ensure you’ve completed all exercises in the **Day 2 Lab**.
Tomorrow, we will cover **CRUD operations** (Create, Read, Update, Delete), where you’ll be able to interact with your tables and manage real data.

---

This **Day 2 Quiz** assesses learners on their understanding of the theoretical concepts (data types, constraints, and table creation) and their ability to write and execute SQL queries to work with tables. It also includes some troubleshooting scenarios to help learners think critically about common issues in database design.

