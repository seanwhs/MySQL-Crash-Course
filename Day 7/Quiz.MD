# **Day 7 Quiz: Transaction Management and Advanced SQL Features**

**Course**: MySQL 1-Week Hands-On Crash Course
**Day**: 7
**Topic**: Transaction Management and Advanced SQL Features

---

### **Part 1: Multiple Choice Questions (MCQs)**

1. **Which of the following is true about transactions in MySQL?**

   * A) A transaction must always be committed immediately after starting.
   * B) A transaction can be rolled back if there is an error.
   * C) Once a transaction is rolled back, it cannot be committed again.
   * D) Transactions cannot be used in MySQL.

   **Answer**: **B) A transaction can be rolled back if there is an error.**

2. **Which isolation level in MySQL prevents dirty reads but allows non-repeatable reads?**

   * A) READ UNCOMMITTED
   * B) READ COMMITTED
   * C) REPEATABLE READ
   * D) SERIALIZABLE

   **Answer**: **B) READ COMMITTED**

3. **Which SQL statement is used to undo all changes made during a transaction?**

   * A) ROLLBACK
   * B) COMMIT
   * C) SAVEPOINT
   * D) ROLLBACK TO

   **Answer**: **A) ROLLBACK**

4. **What does the `SAVEPOINT` command in a transaction allow you to do?**

   * A) Commit a transaction.
   * B) Roll back part of a transaction.
   * C) Set a point in the transaction that can be rolled back to if needed.
   * D) Start a new transaction.

   **Answer**: **C) Set a point in the transaction that can be rolled back to if needed.**

5. **Which of the following is NOT a valid SQL trigger event?**

   * A) INSERT
   * B) DELETE
   * C) UPDATE
   * D) SELECT

   **Answer**: **D) SELECT**

6. **What is the primary purpose of a stored procedure in MySQL?**

   * A) To store temporary data.
   * B) To allow repeated execution of a set of SQL queries with different parameters.
   * C) To automatically delete old records.
   * D) To ensure that data is always consistent.

   **Answer**: **B) To allow repeated execution of a set of SQL queries with different parameters.**

7. **Which SQL statement is used to view the structure of a trigger in MySQL?**

   * A) SHOW TRIGGERS
   * B) DESCRIBE TRIGGER
   * C) SHOW CREATE TRIGGER
   * D) SELECT TRIGGER INFO

   **Answer**: **C) SHOW CREATE TRIGGER**

8. **What will happen if you attempt to execute a transaction under the `READ UNCOMMITTED` isolation level?**

   * A) Dirty reads may occur, where transactions can see uncommitted changes.
   * B) Data will be locked and no other transactions can access it.
   * C) The database will enforce full transaction isolation.
   * D) The transaction will be automatically rolled back.

   **Answer**: **A) Dirty reads may occur, where transactions can see uncommitted changes.**

---

### **Part 2: True/False Questions**

9. **Transactions in MySQL are automatically committed unless explicitly rolled back.**

   * True
   * False

   **Answer**: **False**
   (Transactions are not automatically committed unless explicitly told to do so with `COMMIT`.)

10. **A `ROLLBACK` command in MySQL can only be used within a transaction.**

    * True
    * False

    **Answer**: **True**

11. **A stored procedure can be invoked without any parameters in MySQL.**

    * True
    * False

    **Answer**: **True**
    (Stored procedures can be executed with or without parameters.)

12. **Triggers can be used to automatically update fields such as `last_modified` when a record is updated.**

    * True
    * False

    **Answer**: **True**

13. **You can change the isolation level of a transaction in MySQL by using the `SET TRANSACTION ISOLATION LEVEL` command.**

    * True
    * False

    **Answer**: **True**

---

### **Part 3: Short Answer Questions**

14. **What is the purpose of the `COMMIT` command in MySQL?**

    **Answer**:
    The `COMMIT` command is used to save all changes made during the current transaction permanently to the database. Once a transaction is committed, the changes are final and cannot be undone.

15. **Explain the difference between `BEFORE` and `AFTER` triggers in MySQL.**

    **Answer**:
    A **`BEFORE` trigger** is executed before an operation (INSERT, UPDATE, DELETE) is performed on a table, allowing you to modify the data before it is written. An **`AFTER` trigger** is executed after the operation, meaning it can be used to perform actions based on the final state of the data after the operation is completed.

16. **What is the primary difference between a view and a stored procedure in MySQL?**

    **Answer**:
    A **view** is a virtual table that contains the result of a `SELECT` query and can be queried like a table. It does not store data but simplifies complex queries. A **stored procedure**, on the other hand, is a precompiled set of SQL statements that can be executed as a unit, often used for repetitive tasks or encapsulating business logic.

17. **Describe the ACID properties of transactions and give a brief example of each.**

    **Answer**:

    * **Atomicity**: A transaction is treated as a single unit, meaning either all operations are completed, or none of them are (e.g., transferring money between accounts).
    * **Consistency**: The database moves from one valid state to another (e.g., after a transfer, the sum of the amounts in both accounts is consistent).
    * **Isolation**: Transactions are isolated from each other. For example, no transaction sees the intermediate state of another transaction.
    * **Durability**: Once a transaction is committed, the changes are permanent, even if the system crashes immediately after (e.g., a successful payment will remain in the database).

---

### **Part 4: Scenario-Based Questions**

18. **Scenario**:
    You are working in a banking system and need to transfer money from one account to another. The system must ensure that:

    * The balance of the sender is reduced.
    * The balance of the recipient is increased.
    * If an error occurs, the entire transfer is canceled, and no partial changes are made.

    **Question**:
    How would you implement this process using MySQL transactions?

    **Answer**:

    * **Start a transaction** to ensure atomicity.
    * **Update the sender's account** balance.
    * **Update the recipient's account** balance.
    * If there is any error during the process, use **`ROLLBACK`** to revert the changes.
    * If successful, use **`COMMIT`** to save the changes permanently.

    Example:

    ```sql
    START TRANSACTION;
    UPDATE accounts SET balance = balance - 100 WHERE account_id = 1;
    UPDATE accounts SET balance = balance + 100 WHERE account_id = 2;
    COMMIT;
    ```

    If an error occurs:

    ```sql
    ROLLBACK;
    ```

---

### **Part 5: Bonus Question (Optional)**

19. **What is the impact of using the `SERIALIZABLE` isolation level on the performance of a system?**

    **Answer**:
    The `SERIALIZABLE` isolation level provides the highest level of transaction isolation, ensuring that transactions are executed one at a time, without overlap. While this guarantees maximum consistency and avoids issues like dirty reads, non-repeatable reads, and phantom reads, it can also significantly decrease concurrency, leading to reduced performance, especially in systems with high transaction volume.

---

### **Answer Key:**

1. B
2. B
3. A
4. C
5. D
6. B
7. C
8. A
9. False
10. True
11. True
12. True
13. True
14. The `COMMIT` command saves all changes made during the current transaction permanently.
15. `BEFORE` triggers are executed before the operation, while `AFTER` triggers are executed after the operation.
16. A view is a virtual table, while a stored procedure is a set of SQL statements that can be executed.
17. ACID properties include Atomicity, Consistency, Isolation, and Durability, ensuring reliable and predictable transactions.
18. **Scenario Solution**: Use a transaction to update both the sender's and recipient's balances, rolling back if there is an error and committing if successful.
19. `SERIALIZABLE` ensures strict isolation but reduces performance due to limited concurrency.

---

This **Day 7 Quiz** tests both theoretical understanding and practical application of transaction management, isolation levels, and advanced SQL features like stored procedures, triggers, and views. 
