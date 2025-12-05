Absolutely! Let’s start with **Day 1 – README.md** for your MySQL 1-Week Hands-On Crash Course. I’ll make it detailed and structured so it can be directly shared with learners.

---

# **Day 1 – README.md**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 1
**Topic:** Introduction & Setup
**Duration:** 2–3 hours

---

## **Welcome to Day 1**

Congratulations! You are starting your journey into the world of MySQL. Today’s focus is on understanding what a relational database is, why MySQL is widely used, and setting up your environment so you can start running your own queries.

By the end of today, you will be able to:

* Understand the concept of databases and relational databases
* Install MySQL and MySQL Workbench (GUI)
* Navigate the MySQL Command Line Interface (CLI)
* Create your first database
* Explore basic MySQL commands like `SHOW DATABASES` and `SHOW TABLES`

---

## **Pre-requisites**

Before starting Day 1, ensure you have:

* A computer with internet access
* Administrative privileges to install software
* Basic understanding of computers and file systems

---

## **Day 1 Outline**

1. **Introduction to Databases**

   * What is a database?
   * Relational vs Non-relational databases
   * Why MySQL is popular in the industry

2. **Installing MySQL**

   * Installing MySQL Server
   * Installing MySQL Workbench
   * Verifying the installation

3. **Using MySQL**

   * Introduction to CLI vs GUI
   * Connecting to MySQL server
   * Creating your first database

4. **Basic Commands**

   * `SHOW DATABASES;`
   * `CREATE DATABASE database_name;`
   * `USE database_name;`
   * `SHOW TABLES;`

5. **Mini Project**

   * Create a database called `company_db`
   * Explore databases and table structure

---

## **Getting Started**

### **Step 1: Install MySQL**

Follow official documentation for your OS: [MySQL Installation Guide](https://dev.mysql.com/doc/refman/8.0/en/installing.html)

### **Step 2: Launch MySQL Workbench**

* Open MySQL Workbench
* Connect to your local MySQL server (use root or a user you created)

### **Step 3: Create Your First Database**

```sql
CREATE DATABASE company_db;
USE company_db;
SHOW DATABASES;
```

### **Step 4: Explore**

* `SHOW TABLES;` (You will see no tables yet, but this is how you explore)
* Familiarize yourself with CLI and Workbench interface

---

## **Suggested Reading**

* MySQL Official Documentation: [https://dev.mysql.com/doc/](https://dev.mysql.com/doc/)
* “Introduction to Databases” – online tutorials

---

## **Mini Project**

Create a database named `company_db` and verify it exists. Try exploring the structure using `SHOW DATABASES;` and `SHOW TABLES;`. Document your steps in a text file for reference.

---

## **Tips**

* Always end SQL statements with a semicolon (`;`)
* Use Workbench for a visual approach, CLI for faster execution
* Don’t worry about creating tables yet; today is all about setup and exploration

---

## **Next Steps**

Tomorrow, we will dive into **tables and data types**, learning how to structure your data effectively.

