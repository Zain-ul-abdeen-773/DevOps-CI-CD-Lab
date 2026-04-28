# Lab: Data Persistence in Docker (MariaDB)

## Objective

By the end of this lab, you will:

* Observe how data is **lost** when a container is removed
* Understand why this happens
* Use **Docker volumes** to persist database data

---

## Part 1: Setup Environment

1. Create a Docker network named `devops`
2. Run:

   * A **MariaDB container**
   * A **database management UI tool** (e.g., Adminer)
3. Ensure:

   * The database is accessible via your browser
   * You can log in using the root credentials

   *Hint:* You’ll need to expose a port for the UI container.

---

## Part 2: Create Sample Data

1. Connect to your MariaDB instance using the UI tool
2. Perform the following:

   * Create a database named `devops`
   * Create a table called `student` with a single column `studentId`
   * Insert at least **one record**

   ```bash
     CREATE DATABASE devops;

     CREATE TABLE devops.student (
     studentId char(8) NOT NULL
   ) ENGINE='InnoDB';
   
   INSERT INTO devops.student VALUES('u2023000');
   ```
---

## Part 3: Observe the Problem

1. Stop and remove the MariaDB container
2. Start a **new MariaDB container** (same configuration as before)
3. Reconnect using the UI tool

**Questions:**

* What happened to your database and table?
* Why do you think this happened?

---

## Part 4: Investigate

Research and answer:

* Where does MariaDB store its data inside the container?
* What happens to container data when the container is removed?

---

## Part 5: Apply the Solution

1. Create a **Docker volume**
2. Start a new MariaDB container, but this time:

   * Attach the volume to the correct internal database directory
3. Repeat:

   * Create the `devops` database
   * Create the `student` table
   * Insert data

---

## Part 6: Verify Persistence

1. Remove the MariaDB container again
2. Start a new container **using the same volume**
3. Reconnect via the UI tool

**Questions:**

* Is your data still there?
* What changed compared to Part 3?

---

## Part 7: Reflection

Answer briefly:

1. What is the difference between:

   * Container storage
   * Docker volumes
2. When should you use volumes in real-world applications?

---

## Bonus Challenge
* Try using a **different container name** with the same volume
* Does the data still persist? Why?

---

## Notes

* Do **not** copy commands from others — try to build them yourself
* Focus on understanding *why* the issue happens
* Ask questions if something doesn’t behave as expected

---
