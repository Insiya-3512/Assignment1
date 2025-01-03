# Section 1

History and evolution of Databses 

Brief timeline : 
-> 1950s - 1960s : Data was stored in flkat files and tree - like structure like punch cards and magnetic tapes
-> 1970s : Edgar F. Codd introduced relational databse model, combination of tables rows and columns
-> 1980s : Normalization was introduced to standardise data modelling concepts
-> 1990s : Distributed and Object oriented database 
-> 2000s - present : No SQL, Cloud database

Types of Databses 

1. RDBMS : Data stored in tables, rows and columns and keys for relationships Ex : MySQL, Oracle, PostgreSQL
   Advantages : Consistency, ACID, Structured data.
2. No-SQL : Flexible data models, which can store unstructured or semi-structured data Ex : Mongo DB, Cassandra
   Advantages : Flexible, scalable, and better for Un-structured data.

Database Overview : 
Software to interact with databases, ensuring storage, retrieval, manipulation and integration
Defintion -> CREATION
Manipulation -> CRUD
Security and Access controls
Query Optimisation

Key Differences between SQL VS No-SQL Databases :

-> SQL
1. Tabular data model
2. Fixed and Predefined schema
3. Good for structured data
4. ACID transaction
5. Vertical Scaling (Adding more power to single server)
   
-> No SQL
1. Flexible data model
2. Dynamic schema
3. Good for Large and Un-structured data
4. Horizontally scalable (adding more servers)

# Section 2

Relational Database Fundamentals

Database Design Concepts:
Design of database is crucial to ensure data is stored efficiently and consistently
Combination of entities, attributes and relations

Entity relationship model:
Visual representation used to design database 
-> Entities are represented by rectangles.
-> Attributes are represented by ovals connected to the entity.
-> Primary Keys are underlined in the entity's attributes.
-> Relationships are depicted by diamonds, connecting entities.

Tables, Rows, and Columns:
Table: A collection of related data organized in rows and columns.
Rows: Each row represents a single record of an entity.
Columns: Each column represents an attribute of the entity.

Keys in Database Design:

Primary Key:
-> A primary key uniquely identifies each record in a table.
-> Must be unique for each row and cannot be NULL.
-> Examples: CustomerID, OrderID.

Foreign Key:
-> A foreign key is an attribute in a table that creates a link to another table.
-> The foreign key in one table points to the primary key in another table, establishing a relationship.
-> Example: In an "Order" table, CustomerID can be a foreign key that refers to the CustomerID primary key in the "Customer" table.

Normalization:
Normalization is the process of organizing data in a database to minimize redundancy and dependency.

-> 1 NF : Eliminate duplicate records and ensure each column contains atomic values.
Criteria:
Each table cell should contain only a single value.
Each record must be unique.
Example: A table with multiple phone numbers in one column would violate 1NF.

-> 2 NF : Eliminate partial dependency (when non-key attributes depend on part of a composite primary key).
Criteria:
The table should be in 1NF.
Every non-key column must be fully dependent on the primary key.

-> 3 NF : Eliminate transitive dependency (when non-key attributes depend on other non-key attributes).
Criteria:
The table should be in 2NF.
No non-key attribute should depend on another non-key attribute.

-> Boyce-Codd Normal Form (BCNF): Strengthen 3NF by ensuring that for every functional dependency, the left side is a superkey.
Criteria:
The table should be in 3NF.
For every functional dependency, the determinant must be a superkey.

Denormalization:
Denormalization is the process of intentionally introducing redundancy into a database by merging tables or adding redundant columns.
When to Use:
1. To improve query performance.
2. When frequent joins negatively impact query performance.
3. When aggregating data for reporting and analysis.

# Section 3
Basic SQL Commands:

-> Data Definition Language:
1. Data Definition Language (DDL)
DDL commands are used to define or modify database structures, such as tables and schemas.
CREATE: Defines a new table, view, or other database object.
ALTER: Modifies an existing database object, such as adding or deleting a column.
DROP: Deletes an existing database object, such as a table or view.

-> Data Manipulation Language (DML)
DML commands are used to manage the data within tables.
SELECT: Retrieves data from a database.
INSERT: Inserts new data into a table.
UPDATE: Modifies existing data.
DELETE: Removes data from a table.

-> Data Control Language (DCL)
DCL commands control access to data in the database by granting or revoking permissions.
GRANT: Provides privileges to a user.
REVOKE: Removes privileges from a user.

-> Transaction Control Language (TCL)
TCL commands are used to manage transactions in a database. Transactions ensure that a sequence of SQL statements are executed in a way that maintains data integrity.
BEGIN: Marks the beginning of a transaction.
COMMIT: Commits the current transaction (makes changes permanent).
ROLLBACK: Undoes the current transaction (reverts changes).

# Section 4

Advanced SQL Queries:

Joins:
Joins combine data from two or more tables based on a related column.
1. Inner Join : Returns records that have matching values in both tables.
2. Outer Joins : Outer joins return rows even if there is no match between the tables.
   Left Outer Join (LEFT JOIN): Returns all records from the left table and matching records from the right table. If no match, NULLs will     appear for the right table's columns.
   Right Outer Join (RIGHT JOIN): Returns all records from the right table and matching records from the left table.
3. Full Outer Join (FULL JOIN): Returns all records when there is a match in either left or right table. Non-matching rows will have NULLs     for missing columns.
4. Cross Join : Returns the Cartesian product of the two tables (every row of the first table is combined with every row of the second         table).

Subqueries & Correlated Subqueries:
-> Subquery: A query nested inside another query. It can return a single value, a list of values, or a table.
-> Correlated Subquery: A subquery that refers to columns of the outer query.

Set Operations:
Set operations allow you to combine the results of two or more queries.
-> UNION: Combines results from two queries, removing duplicates.
-> INTERSECT: Returns only the rows that appear in both result sets.
-> EXCEPT: Returns rows from the first query that do not appear in the second query.

Window Functions:
Window functions perform calculations across a set of rows related to the current row. They are used for analytics and ranking purposes.
-> ROW_NUMBER(): Assigns a unique row number to each row within a partition.
-> RANK(): Assigns a rank to each row within a partition, with gaps in ranking for ties.
-> DENSE_RANK(): Similar to RANK(), but without gaps in ranking.
-> NTILE(): Divides the result set into a specified number of groups and assigns a bucket number to each row.
-> LAG(): Returns the value of a column from a previous row within the same result set.

Common Table Expressions (CTEs) & Recursive Queries:
-> CTE (Common Table Expression): A temporary result set defined within a WITH clause, often used for simplifying complex queries.
-> Recursive Queries: CTEs can also be used for recursive queries, such as hierarchical data traversal.

Pivoting and Unpivoting Data:
Pivoting : Converting rows into columns.
Unpivoting : Convertying columns into rows.
