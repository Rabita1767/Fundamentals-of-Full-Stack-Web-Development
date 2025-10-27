# Database Overview

## What is a Database?

A database is a structured collection of electronic data, typically managed by a Database Management System (DBMS).

---

## Difference Between DBMS and RDBMS

### DBMS (Database Management System)

DBMS is a broader concept. It refers to software responsible for managing data efficiently, including data creation, retrieval, and manipulation.

### RDBMS (Relational Database Management System)

RDBMS is a specialized type of DBMS where data is stored in a more organized format, such as tabular structures.

---

## Features Comparison: DBMS vs. RDBMS

| Feature                | DBMS                                                               | RDBMS                                                                                 |
| ---------------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| **Data Structure**     | Data can be stored in hierarchical, network, or flat-file formats. | Data is stored in a tabular format, with rows and columns.                            |
| **Data Relationships** | Data lacks relationships between files.                            | Relationships are defined between tables using keys (e.g., primary and foreign keys). |
| **Data Redundancy**    | High data redundancy is possible.                                  | Data redundancy is eliminated through normalization.                                  |
| **Data Fetching**      | Data fetching is slower due to manual navigation through files.    | Data fetching is faster and more efficient due to the relational model and indexing.  |
| **Security**           | Lower security due to limited security measures.                   | Higher security, with features like authentication and authorization.                 |
| **User Access**        | Typically supports only one user at a time.                        | Supports multiple users simultaneously.                                               |
| **Examples**           | Windows Registry, Microsoft Access.                                | MySQL, Oracle, SQL Server.                                                            |

---

## Types of Databases: Relational, NoSQL, In-memory

### Relational

- Data is stored in a tabular format (rows and columns).
- Each table represents an entity, and each row represents a record.
- Relationships between tables are maintained using Primary Key and Foreign Key concepts.
- Data redundancy is minimized using techniques like normalization.

---

### NoSQL

NoSQL databases store data in a more flexible format and are mostly used for large, dynamic datasets. Examples include MongoDB, Redis, and DynamoDB.

- **Document Databases**: Store data in flexible, semi-structured documents (e.g., JSON, BSON). Examples: MongoDB, Couchbase.
- **Key-Value Stores**: Store data as simple key-value pairs. Examples: Redis, Amazon DynamoDB.
- **Column-Family Stores**: Store data in columns rather than rows, optimized for analytical workloads. Examples: Cassandra, HBase.

---

### In-memory

- Data is stored directly in main memory (RAM) instead of disk storage.
- This allows for faster data access.
- Example: Redis.

---

## Table, Row, Column

- **Table**: The fundamental unit of RDBMS. It has a predefined schema with names and data types.
- **Row**: Represents a record or tuple in the table.
- **Column**: Represents an attribute or field in the table.

---

## Primary Key, Foreign Key, Candidate Key

- **Primary Key**: A single column or a set of columns that uniquely identifies a row (record) in a table. Each table can have only one primary key, and it cannot be null.
- **Foreign Key**: A single column or a set of columns that is the primary key of another table. It can contain duplicate values and can be null (unless the `NOT NULL` constraint is applied). A table can have multiple foreign keys. It is used to establish relationships between tables.
- **Candidate Key**: A single column or a set of columns that uniquely identifies each row (record) in a table. A table can have multiple candidate keys. One of them is designated as the primary key, while the others are known as alternate keys. Candidate keys can be null and can be used to establish relationships with other tables via foreign keys.

---

## Composite Key & Surrogate Key

- **Composite Key**: When a single column is insufficient to uniquely identify each record (row) in a table, a composite key is used. It is created by combining two or more columns to serve as the primary key of the table.
- **Surrogate Key**: A system-generated unique identifier that acts as the primary key of a table. It is used when the existing data in a table cannot serve as a primary key, or when the data is complex or subject to frequent changes.

---

## Entity and Attributes

- **Entity**: A real-world object or concept. Example: Student, Course.
- **Attribute**: Properties or characteristics that define an entity.

---

## Types of Attributes

- **Single Valued and Multi-Valued**: Age is single-valued, and a phone number can be multi-valued.
- **Simple and Composite**: Email is a simple attribute as it can't be divided further, but a name can be a composite attribute as it can consist of firstName, middleName, and lastName.
- **Stored and Derived**: Date of Birth is a stored attribute, but age is a derived attribute as it can be calculated from Date of Birth.
- **Key and Non-key**: Email can be a key attribute as it is unique for all users, but Name, Age, etc., can be non-key attributes.

---

## Relationships

Relationships between tables are a fundamental concept of Relational Database Management Systems (RDBMS). They define how data in those tables are linked to each other. They are implemented through Primary Key and Foreign Key.

### Types of Relationships

1. **One-to-One**: When one record from a table is linked with only one record of another table.  
   **Example**: A person has only one passport, and one passport belongs to only one person.

2. **One-to-Many**: A single record in one table can be linked to multiple records in another.  
   **Example**: A Customers table and an Orders table, where one customer can place many orders, but each order is tied to a single customer.

3. **Many-to-Many**: Multiple records in one table link to multiple records in another. This requires an intermediate or "junction" table.  
   **Example**: A Students table and a Courses table, where a student can enroll in multiple courses, and a course can have many students. A junction table like Enrollments would contain foreign keys from both tables.

---

## Why Relationships Are Important

- **Data Redundancy**: Reduced by organizing data into separate tables.
- **Efficient Data Retrieval**: Ensured by using complex queries that join data from multiple tables.

---

## Classification of DBMS Architecture

### One-Tier Architecture

In this architecture, the presentation layer, application server, and database are all inside the same application.  
**Example**: Microsoft Excel.

### Two-Tier Architecture

In this architecture, the client end directly communicates with the database on the server side. The server side is responsible for query processing and transaction management functionalities.

### Three-Tier Architecture

There is another layer between the client and the server. The client does not directly communicate with the database. Instead, it communicates with the application server, which further communicates with the database.

---

## ACID Properties

ACID properties are fundamental principles that ensure the reliability and integrity of database transactions.

### Atomicity

- **Definition**: Ensures that a transaction is treated as a single, indivisible unit. Either all operations within the transaction are executed successfully, or none are.
- **Example**: In a bank transfer, if one account is debited, the other must be credited. If any part of the transaction fails, the entire transaction is rolled back.

### Consistency

- **Definition**: Guarantees that a database remains in a valid state before and after a transaction, adhering to all defined rules and constraints.
- **Example**: A transaction that would result in a negative account balance violates constraints and is canceled.

### Isolation

- **Definition**: Ensures that transactions are executed independently of one another. Partial or uncommitted changes made by one transaction are not visible to other transactions.
- **Example**: Two users updating the same account balance simultaneously will not interfere with each other.

### Durability

- **Definition**: Ensures that once a transaction is committed, its changes are permanent, even in the event of a system crash.
- **Example**: After a successful transaction, the updated account balances remain intact even if the database server restarts.

---

## BASE Properties

This is a consistency model for distributed database systems like NoSQL.

- **Basically Available**: The system is responsive and available, meaning it will respond to requests even if some parts of it are unavailable. It prioritizes the system's responsiveness to reads and writes rather than immediate availability of all data across all nodes.
- **Soft State**: The system might not be fully synchronized yet, but without any input, background processes and asynchronous operations will eventually make the system consistent.
- **Eventually Consistent**: Data consistency will be achieved across all nodes after a certain period of time.

### Example

Suppose you are ordering an iPhone from Amazon. You click on the "Buy Now" button, and your order is confirmed immediately. Here, the data might have been updated in your region but might not be fully updated across all regions. However, you do not receive any error, and you get an immediate response. This represents the **Basically Available** state of a system.

Now, the period during which the data across all regions is not fully synchronized is referred to as the **Soft State**. For instance, the data in your region (e.g., Dhaka region) might be updated, but in another region (e.g., Singapore region), it might not be updated yet. Someone from the Singapore region might see outdated data temporarily.

After a certain period of time, the data across all regions will be updated. This is referred to as **Eventual Consistency**.

---

## State of a Transaction

- **Active**
- **Partially Committed**
- **Failed**
- **Aborted**
- **Committed**

---

## What is SQL?

Structured Query Language (SQL) is a programming language used to retrieve and manipulate databases.

---

## Types of SQL Statements

| SQL Type                               | Commands                              | Description                                                          |
| -------------------------------------- | ------------------------------------- | -------------------------------------------------------------------- |
| **Data Definition Language (DDL)**     | `CREATE`, `ALTER`, `DROP`, `TRUNCATE` | Statements that define the data and data structure (schema objects). |
| **Data Manipulation Language (DML)**   | `INSERT`, `UPDATE`, `DELETE`          | Statements that manipulate the data.                                 |
| **Data Control Language (DCL)**        | `GRANT`, `REVOKE`                     | Statements to limit access to the data.                              |
| **Transaction Control Language (TCL)** | `COMMIT`, `ROLLBACK`, `SAVEPOINT`     | Statements to control the transactions in a session.                 |
| **Data Query Language (DQL)**          | `SELECT`                              | Statements used to view the data.                                    |

## Introduction to Normalization

Normalization is the process of organizing attributes in such a way that data redundancy is reduced or eliminated, and anomalies like insertion, deletion, and update anomalies are resolved.

### Data Redundancy

#### Row-Level Data Redundancy

- Row-level redundancy can be reduced by assigning a primary key to a table.

#### Column-Level Data Redundancy

Column-level redundancy is responsible for creating insertion, deletion, and update anomalies. Consider the following example:

- **Insertion Anomaly**:  
   Suppose we have a `student_course` table with columns such as `student_id`, `student_name`, `course_name`, `instructor_name`, and `salary`.  
   If the university introduces a new course called "MBBS" and we try to insert this record into the `student_course` table, it will fail. Why? Because no student has enrolled in this course yet, so the `student_id` is missing in the record. Since `student_id` is the primary key of this table, it is required. This is called an **insertion anomaly**.

- **Deletion Anomaly**:  
   Suppose a course named "Bangla" is instructed by Mr. Patwary with a salary of 35,000. Only one student, with `student_id` 5 and `student_name` "Rabita," is enrolled in this course. If we delete the record for `student_id` 5, it will also remove the course-related information. Since this was the only record containing the course details, the course information is unintentionally lost. This is called a **deletion anomaly**.

- **Update Anomaly**:  
   Suppose two students, with `student_id` 1 and 2, are enrolled in the course "English." If we update the salary for `student_id` 2, it will change the salary for that record. However, another record also contains information about this course but does not reflect the updated salary value. This inconsistency is called an **update anomaly**. Now you can think why not update the salary targeting the course_name. Yes, we can absulately do that. It does solve the inconsistency issue but it's going to create time complexity issue as the update going to happen in multiple rows.

## 1st Normal Form (1NF)

A table should not contain multi-valued attributes.

### Example

If we have a table with three columns: `student_id`, `student_name`, and `course_name`, a student can be enrolled in more than one course. In this case, the `course_name` attribute will contain multiple values, indicating that the table is not in 1NF.

### Methods to Achieve 1NF

#### Method 1: Create Separate Rows for Multi-Valued Attributes

- Assign a primary key so that each primary key is associated with a single record only.
- If needed, use a composite key as the primary key.
- **Example**: In our case, we can make `student_id` and `course_name` the composite primary key. This will transform the table into 1NF.

#### Method 2: Create Separate Columns for Multi-Valued Attributes

- Create additional columns for each value of the multi-valued attribute.
- **Issues**: This approach is inefficient because:
  - The number of columns required depends on the maximum number of values, which can vary.
  - Most cells may remain `NULL` if many students are enrolled in only one course.

#### Method 3: Create Multiple Tables (Recommended)

- Split the data into two tables:
  1. **Base Table**: Contains `student_id` and `student_name`. Here, `student_id` is the primary key.
  2. **Reference Table**: Contains `student_id` and `course_name`. In this table:
     - `student_id` acts as a foreign key.
     - The combination of `student_id` and `course_name` forms the composite primary key.

This method ensures data normalization and avoids redundancy.

## 2nd Normal Form (2NF)

For a table to be in 2nd Normal Form, it must satisfy the following conditions:

1. The table should be in 1st Normal Form (1NF).
2. Every non-prime attribute must be fully functionally dependent on the candidate key(s). This means no partial dependency should exist for non-prime attributes.

### Example

Consider a table with the following attributes:

- `customer_id`
- `store_id`
- `location`

Here:

- The candidate key is a combination of `customer_id` and `store_id`.
- `location` is a non-prime attribute.

In this case, `location` is determined by only a part of the candidate key (`store_id`) rather than the entire candidate key (`customer_id` and `store_id`). This partial dependency means the table is not in 2nd Normal Form.

### Solution

To resolve this issue, we can split the table into two separate tables:

1. **Store Table**:

   - Attributes: `store_id`, `location`
   - Candidate Key: `store_id`
   - The non-prime attribute `location` is fully dependent on the candidate key `store_id`.

2. **Customer-Store Table**:
   - Attributes: `customer_id`, `store_id`
   - Candidate Key: A combination of `customer_id` and `store_id`
   - No non-prime attributes are present.

By restructuring the data into these two tables, we eliminate partial dependency and ensure the tables are in 2nd Normal Form.

## 🧩 3rd Normal Form (3NF)

### Conditions for 3NF

1. The table should be in **Second Normal Form (2NF)**
2. There should be **no transitive dependency**

---

### What is a Transitive Dependency?

When a non-key attribute can be determined by another non-key attribute which is determined by a key attribute, then it's called transitive dependency.

In other words, if:  
A → B → C

and **A** is the primary key, then **A → C** is a **transitive dependency**.

Transitive dependencies cause **data redundancy** and **anomalies**, such as:

- **Insertion anomalies**
- **Deletion anomalies**
- **Update anomalies**

---

### 📘 Example

Consider a table named **`Student`** with the following attributes:

| student_id | batch_id | batch_name |
| ---------- | -------- | ---------- |
| 1          | B01      | CSE 2021   |
| 2          | B01      | CSE 2021   |
| 3          | B02      | EEE 2021   |

- **Primary Key:** `student_id`
- **Direct dependency:** `student_id → batch_id`
- **Transitive dependency:** `student_id → batch_id → batch_name`

Here is an example of a table called student with three attributes, student_id, batch_id and batch_name. student_id is the primary key of this table and batch_id a non-key attribute is determined by student_id. This is a direct relationship. But, a non-key attribute batch_name can be determined by another non-key attribute batch_id, which is determined by primary key student_id. This is an indirect relationship and is called transitive dependency.
`batch_name` depends on `batch_id`, which depends on `student_id`.  
This indirect dependency (`student_id → batch_name`) violates **3NF**.

---

### Solution

To solve this we can create two separate tables. One is Student table with student_id and batch_id and another is Batch table with batch_id and batch_name. student_id is the primary key of Student table and batch_id is the primary key of Batch table.

#### 1. **Student Table**

| student_id | batch_id |
| ---------- | -------- |
| 1          | B01      |
| 2          | B01      |
| 3          | B02      |

**Primary Key:** `student_id`

#### 2. **Batch Table**

| batch_id | batch_name |
| -------- | ---------- |
| B01      | CSE 2021   |
| B02      | EEE 2021   |

**Primary Key:** `batch_id`

Now, the data redundancy is eliminated, and both tables can be joined using `batch_id` to retrieve the necessary data.
