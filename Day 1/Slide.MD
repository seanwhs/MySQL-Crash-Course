# **Day 1 – Slides: Introduction & Setup**

---

## **Slide 1: Title Slide**

**Title:** MySQL 1-Week Hands-On Crash Course – Day 1
**Subtitle:** Introduction & Setup
**Visuals:** MySQL logo, laptop/server icons
**Speaker Notes:**

* Welcome participants
* Briefly explain the course structure
* Mention that today’s goal is to set up the environment and understand basic database concepts

---

## **Slide 2: Learning Objectives**

**Content:** By the end of Day 1, learners will be able to:

* Explain what a database is
* Describe relational vs non-relational databases
* Install MySQL Server and MySQL Workbench
* Navigate the MySQL CLI and Workbench GUI
* Create their first database and explore basic commands
  **Visuals:** Checklist or icons representing each objective
  **Speaker Notes:** Highlight the practical nature of the day: hands-on environment setup

---

## **Slide 3: What is a Database?**

**Content:**

* A **database** is an organized collection of data
* Types of databases:

  * Relational (tables, rows, columns)
  * Non-relational (NoSQL: key-value, document, graph)
* Databases are used to store and retrieve information efficiently
  **Visuals:** Diagram showing tables with rows and columns
  **Speaker Notes:** Give simple examples: Employee records, inventory lists

---

## **Slide 4: Relational vs Non-Relational Databases**

**Content:**

| Feature          | Relational (MySQL)    | Non-Relational (MongoDB)     |
| ---------------- | --------------------- | ---------------------------- |
| Structure        | Tables, rows, columns | JSON, key-value, documents   |
| Schema           | Fixed schema          | Flexible schema              |
| Example Use Case | Banking, ERP systems  | Real-time analytics, caching |

**Speaker Notes:** Emphasize why MySQL is popular in enterprise applications

---

## **Slide 5: Why MySQL?**

**Content:**

* Open-source and widely used
* Cross-platform support (Windows, macOS, Linux)
* Reliable for small to large-scale applications
* Strong community and documentation

**Visuals:** MySQL logo + stats chart of popularity
**Speaker Notes:** Mention companies using MySQL for real-world credibility

---

## **Slide 6: Installing MySQL**

**Content:**

1. Download MySQL Server from official site
2. Install MySQL Workbench (GUI tool)
3. Verify installation:

   ```bash
   mysql --version
   ```

**Visuals:** Screenshot of download page or installation wizard
**Speaker Notes:** Explain OS differences and why Workbench is helpful for beginners

---

## **Slide 7: MySQL CLI vs GUI**

**Content:**

* **CLI (Command Line Interface)**

  * Fast, precise, scripting-friendly
* **GUI (Workbench)**

  * Visual, easier to explore tables and databases

**Visuals:** Split screen showing CLI vs Workbench
**Speaker Notes:** Encourage trying both approaches; CLI for real-world jobs

---

## **Slide 8: Connecting to MySQL**

**Content:**

* Open CLI:

  ```bash
  mysql -u root -p
  ```
* Enter password → connected!
* In Workbench:

  * Click “+” to add new connection
  * Fill host, port, username, password

**Visuals:** Screenshot of Workbench connection setup
**Speaker Notes:** Demonstrate connecting live if possible

---

## **Slide 9: Creating Your First Database**

**Content:**

```sql
CREATE DATABASE company_db;
USE company_db;
SHOW DATABASES;
```

**Visuals:** Screenshot of Workbench showing `company_db`
**Speaker Notes:** Walk through command execution in CLI and GUI

---

## **Slide 10: Exploring Databases**

**Content:**

* `SHOW DATABASES;` → lists all databases
* `USE database_name;` → switch to a database
* `SHOW TABLES;` → lists all tables in the database

**Visuals:** CLI screenshots
**Speaker Notes:** Explain that today’s exercises are about exploration, not creating tables yet

---

## **Slide 11: Mini Project**

**Content:**

* Create a database named `company_db`
* Explore databases and tables using commands
* Document steps in a text file

**Visuals:** Checklist icon or laptop with database diagram
**Speaker Notes:** Encourage hands-on practice; this sets up for Day 2

---

## **Slide 12: Tips for Success**

**Content:**

* Always end SQL statements with `;`
* Use Workbench for visualization, CLI for speed
* Don’t worry about creating tables today

**Visuals:** Lightbulb icon or tip box
**Speaker Notes:** Reinforce that Day 1 is foundational

---

## **Slide 13: Next Steps**

**Content:**

* Tomorrow: Tables & Data Types
* You will learn how to design tables and define columns properly

**Visuals:** Calendar icon highlighting Day 2
**Speaker Notes:** Build anticipation for hands-on table creation

