# **Day 1 – Trainer Guide**

**Course:** MySQL 1-Week Hands-On Crash Course
**Day:** 1
**Topic:** Introduction & Setup
**Duration:** 2–3 hours

---

## **Trainer Objectives**

By the end of this session, learners should be able to:

1. Explain what a database is and distinguish relational vs non-relational databases
2. Install and configure MySQL Server and Workbench
3. Connect to MySQL using CLI and Workbench
4. Create a database and explore basic commands (`SHOW DATABASES`, `USE`, `SHOW TABLES`)
5. Demonstrate basic confidence navigating the MySQL environment

---

## **Preparation Checklist**

Before the session:

* Ensure MySQL Server and Workbench are installed on all participant machines
* Prepare sample screenshots of installation, Workbench connections, and CLI prompts
* Prepare a projector or shared screen to demonstrate commands live
* Test all lab exercises on your environment

---

## **Session Flow & Trainer Notes**

### **1. Introduction (10–15 min)**

**Content:**

* Welcome participants
* Explain course objectives and schedule for the week
* Briefly discuss real-world applications of MySQL

**Trainer Tips:**

* Ask participants if they have any prior database experience
* Share examples of companies using MySQL (e.g., Facebook, YouTube, Airbnb)

---

### **2. Database Concepts (20 min)**

**Content:**

* Definition of a database
* Relational vs non-relational databases
* Why MySQL is widely used

**Demo:**

* Show a simple table diagram with rows and columns
* Compare to a JSON document for NoSQL

**Discussion Points:**

* Ask learners to give examples of data they might store in a database
* Highlight use cases: employee records, inventory, transactions

---

### **3. Installing MySQL & Workbench (20 min)**

**Content:**

* Walk through installation steps for MySQL Server and Workbench
* Verify installation

**Demo:**

* Open CLI → `mysql --version`
* Open Workbench and create a sample connection

**Trainer Tips:**

* Address common installation issues (e.g., port conflicts, firewall)
* Encourage learners to test connections immediately

---

### **4. Connecting to MySQL (20 min)**

**Content:**

* CLI: `mysql -u root -p`
* Workbench connection setup

**Demo:**

* Show connecting via CLI and Workbench
* Demonstrate switching between CLI and GUI for same operations

**Trainer Tips:**

* Encourage learners to try both methods
* Reinforce importance of passwords and connection security

---

### **5. Creating First Database (30 min)**

**Content:**

* `CREATE DATABASE company_db;`
* `USE company_db;`
* `SHOW DATABASES;`
* `SHOW TABLES;`

**Demo:**

* Execute each command live in both CLI and Workbench
* Show expected output

**Trainer Tips:**

* Emphasize the semicolon at the end of commands
* Explain that `SHOW TABLES;` returns empty because no tables exist yet

---

### **6. Lab Session (30–40 min)**

**Tasks for Learners:**

1. Verify installation
2. Connect to MySQL via CLI and Workbench
3. Create `company_db`
4. Explore databases and tables
5. Document all steps in a text file

**Trainer Role:**

* Circulate and assist learners with errors
* Prompt learners to reflect on their steps and document observations

---

### **7. Wrap-Up & Reflection (10–15 min)**

**Content:**

* Review key concepts: database, relational DB, CLI vs Workbench
* Ask learners to share any challenges faced
* Highlight next day: Tables & Data Types

**Trainer Tips:**

* Encourage learners to review commands at home
* Ask reflection questions from Learner Guide

---

## **Common Issues & Troubleshooting**

| Issue                          | Solution                                        |
| ------------------------------ | ----------------------------------------------- |
| MySQL service not running      | Start the MySQL service from OS service manager |
| Cannot connect in Workbench    | Check hostname, port, and username/password     |
| `mysql` command not recognized | Add MySQL bin directory to system PATH          |

---

## **Additional Trainer Notes**

* Encourage participation by asking learners to predict results before executing commands
* Use real-world examples to make concepts relatable
* Ensure learners document steps; it reinforces learning

