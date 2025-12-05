# **Day 1 – Lab: Introduction & Setup**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 1
**Topic:** Introduction & Setup
**Duration:** 1–2 hours
**Objective:** Set up MySQL environment, create your first database, and explore basic commands.

---

## **Lab Setup**

Before starting the lab:

1. Ensure MySQL Server and MySQL Workbench are installed.
2. Have access to the MySQL root user or a created user with administrative privileges.
3. Open a terminal/command prompt for CLI exercises and Workbench for GUI exercises.

---

## **Exercise 1: Verify Installation**

**CLI:**

```bash
mysql --version
```

**Workbench:**

* Open Workbench → Check if you can connect to the local MySQL server.

**Expected Outcome:**

* CLI should return the MySQL version.
* Workbench should successfully connect to your server.

---

## **Exercise 2: Connect to MySQL**

**CLI:**

```bash
mysql -u root -p
```

* Enter your password when prompted.

**Workbench:**

* Open Workbench → Click on your connection → Enter password → Connect

**Expected Outcome:**

* You are connected to the MySQL server and ready to execute queries.

---

## **Exercise 3: Create Your First Database**

**Task:** Create a database called `company_db`.

**SQL Command:**

```sql
CREATE DATABASE company_db;
```

**Verify Creation:**

```sql
SHOW DATABASES;
```

**Expected Outcome:**

* `company_db` should appear in the list of databases.

---

## **Exercise 4: Switch to Your Database**

**Task:** Select `company_db` as the active database.

**SQL Command:**

```sql
USE company_db;
```

**Expected Outcome:**

* You are now working inside `company_db`. Any tables created later will belong to this database.

---

## **Exercise 5: Explore Tables in the Database**

**Task:** Check for tables in `company_db`.

**SQL Command:**

```sql
SHOW TABLES;
```

**Expected Outcome:**

* Currently, there are no tables. This is expected, as table creation will start on Day 2.

---

## **Exercise 6: Document Your Work**

**Task:**

* Create a simple text file called `day1_lab_notes.txt`.
* Record:

  * MySQL version
  * Commands used (`CREATE DATABASE`, `SHOW DATABASES`, `USE`, `SHOW TABLES`)
  * Screenshots or notes from Workbench connection

**Purpose:**

* Reinforces learning
* Serves as a reference for future exercises

---

## **Optional Challenge**

* Try creating a second database called `test_db` and explore it using `SHOW DATABASES;` and `USE test_db;`.
* Compare results with `company_db`.

---

## **Lab Completion Checklist**

* [ ] Verified MySQL installation
* [ ] Connected to MySQL via CLI and Workbench
* [ ] Created `company_db` database
* [ ] Explored tables using `SHOW TABLES;`
* [ ] Documented all steps in `day1_lab_notes.txt`

---

This lab ensures learners are comfortable with the MySQL environment before moving on to creating tables and working with data.

