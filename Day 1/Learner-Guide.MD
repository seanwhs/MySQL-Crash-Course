# **Day 1 – Learner Guide**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 1
**Topic:** Introduction & Setup
**Duration:** 2–3 hours

---

## **Welcome**

Welcome to Day 1! Today you will:

* Understand what a database is
* Install and configure MySQL and Workbench
* Connect to MySQL using CLI and Workbench
* Create your first database and explore basic commands

By the end of this session, you will have your MySQL environment ready for more advanced tasks in the following days.

---

## **Step 1: Understanding Databases**

### **What is a Database?**

A database is a structured collection of data that allows you to efficiently store, retrieve, and manage information.

**Types of Databases:**

* **Relational Databases (RDBMS)**: Store data in tables with rows and columns (e.g., MySQL, PostgreSQL)
* **Non-Relational Databases (NoSQL)**: Store data in documents, key-value pairs, or graphs (e.g., MongoDB, Redis)

**Why MySQL?**

* Open-source, free to use
* Widely adopted in industry
* Reliable for small and large applications
* Cross-platform support

---

## **Step 2: Install MySQL and Workbench**

### **Installing MySQL Server**

1. Download MySQL Server from [https://dev.mysql.com/downloads/mysql/](https://dev.mysql.com/downloads/mysql/)
2. Follow the installation wizard for your OS
3. During installation, set a root password

### **Installing MySQL Workbench**

1. Download Workbench from [https://dev.mysql.com/downloads/workbench/](https://dev.mysql.com/downloads/workbench/)
2. Install following the wizard
3. Open Workbench and configure a connection to your local server

**Tip:** Workbench provides a visual interface that is easier for beginners, but CLI is essential for real-world usage.

---

## **Step 3: Connecting to MySQL**

### **Using CLI**

```bash
mysql -u root -p
```

* Enter the root password when prompted
* You should see the MySQL prompt (`mysql>`)

### **Using Workbench**

1. Open Workbench
2. Click “+” to create a new connection
3. Fill in host (`localhost`), username (`root`), and password
4. Click **Test Connection**, then **Connect**

**Tip:** Try both CLI and Workbench to understand the differences

---

## **Step 4: Creating Your First Database**

**Command to create a database:**

```sql
CREATE DATABASE company_db;
```

**Switch to the database:**

```sql
USE company_db;
```

**Check all databases:**

```sql
SHOW DATABASES;
```

**Check tables in the database:**

```sql
SHOW TABLES;
```

**Observation:**

* At this point, `company_db` exists but has no tables. You will create tables on Day 2.

---

## **Step 5: Lab Exercises**

Follow the Day 1 Lab to practice:

1. Verify installation
2. Connect to MySQL via CLI and Workbench
3. Create `company_db`
4. Explore databases and tables
5. Document steps in a text file

---

## **Tips for Learners**

* Always end SQL statements with a semicolon (`;`)
* Use Workbench to visualize databases and CLI for practice with real queries
* Don’t worry about tables today; focus on setting up and exploring

---

## **Reflection**

After completing the exercises, answer these questions in your notes:

1. What is the difference between a relational and non-relational database?
2. What command did you use to create a database?
3. How do you list all databases in MySQL?
4. What did you notice when you ran `SHOW TABLES;` in a new database?

**Tip:** Documenting your reflections helps reinforce learning and prepares you for Day 2.

---

## **Next Steps**

Tomorrow, you will dive into **Tables & Data Types**, where you will learn how to structure data effectively using tables and columns.
