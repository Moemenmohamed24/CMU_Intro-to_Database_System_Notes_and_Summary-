# Some of the important definition

# Data Models :
It is how we think and imagine the formation of personal data within the system.

| **Type**            | **Database Examples**           | **Common Use**                            |
| ------------------- | ------------------------------- | ----------------------------------------- |
| **Hierarchical**    | IBM IMS                         | Simple hierarchical organization          |
| **Network**         | IDMS                            | Complex relationships                     |
| **Relational**      | MySQL, PostgreSQL               | Most applications                         |
| **ER Model**        | —                               | Database design                           |
| **Object-Oriented** | db4o, ObjectDB                  | OOP-based applications                    |
| **Document**        | MongoDB (JSON/XML-like objects) | Semi-structured data                      |
| **Key-Value**       | Redis, DynamoDB                 | High performance and speed (small apps)   |
| **Column-Family**   | Cassandra, HBase                | Big data storage                          |
| **Graph**           | Neo4j                           | Networks and relationship analysis        |
| **Time-Series**     | InfluxDB                        | Time-based metrics and measurements       |
| **Array**           | SciDB, TileDB                   | Scientific computing and machine learning |


# Schema in a Database :

It is the actual implementation of the data model inside the database.
In other words, the schema is the detailed blueprint that defines:

Table names

Column names

Data types ( INT, VARCHAR, DATE)

Keys (Primary Key, Foreign Key)

Relationships between tables

So, the schema represents how the data model is physically structured and stored in the database system.

----------------------------------------------------------------------------------------------------------------------------------
# Storage

Data is stored in tables, and each table consists of rows (the actual data) and columns (the attributes or fields).
Every table has a primary key that uniquely identifies each row and prevents duplication.

# Data Access

Data is accessed using SQL (Structured Query Language).
Users write logical queries, and the DBMS (Database Management System) takes care of executing them and handling the technical details of how the data is retrieved from the storage.

# Physical Storage

This refers to how the DBMS actually stores data on disk.
Data is saved in files, which are divided into pages, and indexes are used to make data access faster.
The main goal is to ensure efficient reading and writing of data.


# Structure

Refers to the organization and layout of data inside the database.

It is defined by the schema, which specifies the tables, columns, data types, and relationships.

It shows how the data is arranged and connected.

 Example:
A table called Students with columns StudentID, Name, and Grade — this is part of the database structure.

# Integrity

Ensures that the data is accurate, correct, and consistent within the database.
This is maintained through constraints, such as:

Primary Key: prevents duplicate records.

Foreign Key: ensures valid relationships between tables.

Check Constraint: validates specific conditions (e.g., grade must be between 0 and 100).

Not Null: prevents empty (null) values in certain columns.

✅ Goal: Protect data from errors or inconsistencies.

# Manipulation

Refers to all operations users perform on the data after it has been stored, such as:

Insert: add new records to the database.

Update: modify existing data.

Delete: remove unwanted data.

Select: retrieve or view data based on specific conditions.

# Data indebendance :

# Simple Explanation 

When you are working at a certain level in the database architecture,
you don’t need to care about the details of the other levels.

# For example:
If you are working at the Logical Schema level — designing tables, attributes, and relationships —
you don’t care how the data is physically stored on the disk.
Your focus is only on the logical structure (how data is organized conceptually).

This separation of concerns is exactly what Data Independence means.

<img width="1202" height="702" alt="image" src="https://github.com/user-attachments/assets/9606aad6-350e-4604-b43b-e7db66da74c7" />

Data Independence in DBMS

Definition:
Data Independence means the ability of a Database Management System (DBMS) to change the structure or storage of data without affecting the applications or users that access it.

In simple terms:
 It’s the separation between data and the programs that use that data.

Types of Data Independence
1. Physical Data Independence

Refers to the ability to change the internal (physical) level without affecting the logical level.

In other words, you can modify how the data is physically stored on the disk — like file structures, indexing methods, or record organization — without changing how the data is logically represented.

 Example:
If you change the table’s storage method from a heap file to an indexed file,
the SQL queries used by the user remain exactly the same.

Why?
Because the DBMS is responsible for translating SQL queries into low-level physical operations.

2. Logical Data Independence

Refers to the ability to change the conceptual (logical) level without affecting the external (user) level.

In other words, you can modify the database design — such as tables, relationships, or adding new attributes — without needing to change the applications or user interfaces that access the data.

 Example:
If you add a new column (e.g., email) to the Students table,
the existing applications that don’t use that column will continue to work normally.

 Relationship with the 3-Level Architecture
Level	Description	Affected by
Internal Level	How data is physically stored	Physical Storage
Conceptual Level	Overall logical design (tables, relationships)	Logical Design
External Level	How users view the data (views)	User Applications

 Relationship Summary:

Changes between Internal ↔ Conceptual → provide Physical Data Independence

Changes between Conceptual ↔ External → provide Logical Data Independence

# Relational Algebra operation:

<img width="738" height="453" alt="image" src="https://github.com/user-attachments/assets/25b87cb9-6a46-4a72-b9c5-db3f5a1eb2aa" />

