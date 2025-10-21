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
