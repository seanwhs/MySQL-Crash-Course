# **Day 1 – Quiz: Introduction & Setup**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 1
**Duration:** 15–20 minutes
**Format:** Multiple Choice, True/False, Short Answer

---

## **Section 1: Conceptual Questions**

**Q1.** What is a database?
A) A program to edit text
B) A structured collection of data for efficient storage and retrieval
C) A type of operating system
D) A programming language

**Answer:** B

---

**Q2.** Which of the following is an example of a relational database?
A) MySQL
B) MongoDB
C) Redis
D) Cassandra

**Answer:** A

---

**Q3.** True or False: Relational databases store data in tables consisting of rows and columns.

**Answer:** True

---

**Q4.** Name two reasons why MySQL is widely used in industry.

**Sample Answer:**

* Open-source and free to use
* Cross-platform and reliable for small to large applications

---

## **Section 2: Practical / Commands**

**Q5.** Which SQL command is used to create a new database?
A) CREATE TABLE
B) CREATE DATABASE
C) INSERT DATABASE
D) NEW DATABASE

**Answer:** B

---

**Q6.** What command lists all databases in your MySQL server?
A) SHOW TABLES;
B) LIST DATABASES;
C) SHOW DATABASES;
D) SELECT DATABASES;

**Answer:** C

---

**Q7.** Which command is used to switch to a specific database?
A) USE database_name;
B) SELECT database_name;
C) CHANGE database_name;
D) SWITCH database_name;

**Answer:** A

---

**Q8.** True or False: When you create a new database, it already contains some tables.

**Answer:** False

---

**Q9.** Match the interface to its description:

| Interface | Description                            |
| --------- | -------------------------------------- |
| CLI       | A visual interface to manage databases |
| Workbench | A command-line tool to execute queries |

**Answer:**

* CLI → A command-line tool to execute queries
* Workbench → A visual interface to manage databases

---

**Q10.** Optional Practical Question:

* Connect to MySQL via CLI and create a database called `test_lab_db`.
* Switch to `test_lab_db` and run `SHOW TABLES;`.
* What do you observe?

**Expected Answer:**

* Database `test_lab_db` is created successfully
* `SHOW TABLES;` returns empty because no tables exist yet

