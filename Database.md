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

## Entity and Attributes

- **Entity**: A real world object or concept. Example: Student, Course
- **Attribute**: Properties or characteristics that define an entity.

## Types of Attrubutes

- **Single Valued and Multi Valued**: Age is single valued ands phone number can be multi valued
- **Simple and Composite**:email is a simple attribute as it can't be divided into anything else but name can be a composite attribute as it can be created using 3 part like firstName,middleName and lastName
- **Stored and Derived**:Date of Birth is a stored attribute but age is a derived attribute as it can be calculated from Date of Birth
- **Key and Non-key**:Email can be a key attribute as it can be unique for all users but Name,Age etc can be non-key attribute

## Relationships

Relationships between tables are fundamental concept of Relational Database Management System(RDBMS). It's a logical connection between two or more tables that defines how data in those tables are linked to each-other.
They are implemented through Primary Key and Foreign Key.
3 types of relationships
1.One to One
2.One to Many
3.Many to Many

- **One to One**: When One record from a table is linked with only one record of another table then this relationship is defined as One to One relationship. Example: A Person has only one Passport. One Passport belongs to only one Person.
- **One to Many**: A single record in one table can be linked to multiple records in another. This is the most prevalent type in relational databases. A Customers table and an Orders table, where one customer can place many orders, but each order is tied to a single customer.
- **Many to Many**: A many-to-many relationship involves multiple records in one table linking to multiple records in another. This requires an intermediate or "junction" table to function in a relational database, establishing two one-to-many relationships. Example: A Students table and a Courses table, where a student can enroll in multiple courses, and a course can have many students. A junction table like Enrollments would contain foreign keys from both tables.

## Why relationships are important

Data redundency is reduced by organizing data into separate tables.
Efficient Data retrival is ensured by using complex queries that join data from multiple tables
