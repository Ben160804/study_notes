MAKAUT DBMS — TEST 8
PCC-CS601 / PCCCS601
Time: 3 Hours    Full Marks: 70
[Full-coverage retest — best for final 2-day dry run]

Instructions: Figures in the margin indicate full marks. Give answers in your own words as far as practicable.

------------------------------------------------------------------
GROUP A  (1 x 10 = 10)  — Very Short Answer Type
------------------------------------------------------------------

1. _______ is called the "father of the relational model."
2. _______ normal form is based on multivalued dependencies.
3. A weak entity set is identified by its _______ entity set.
4. In three-schema architecture, the _______ schema describes the logical
   structure of the entire database.
5. The SQL command to remove a table and its data permanently is _______.
6. What is the full form of DBA?
7. In a B-tree of order m, every node except the root must have at least
   _______ and at most _______ children.
8. The _______ protocol prevents deadlocks naturally by aborting the
   younger transaction.
9. What is the full form of MAC?
10. The process of grouping frequently accessed data together is called
    _______ in a data warehouse.

------------------------------------------------------------------
GROUP B  (5 x 3 = 15)  — Short Answer Type
------------------------------------------------------------------

11. Explain the concept of specialization and generalization in ER model
    with a diagram. [5]

12. What is a functional dependency? Explain augmentation and transitivity
    rules with examples. [5]

13. Explain transaction logs. What information does a log record typically
    contain? [5]

14. What is a data warehouse? List and explain its key characteristics. [5]

15. Write short notes on: (i) DAC (ii) MAC (iii) RBAC. [5]

------------------------------------------------------------------
GROUP C  (15 x 3 = 45)  — Long Answer Type
------------------------------------------------------------------

16.
    (a) Differentiate between 1NF, 2NF, 3NF and BCNF with examples showing
        a relation that satisfies 3NF but not BCNF. [5]
    (b) What is a join dependency? Explain 4NF and its relation to BCNF. [5]
    (c) Decompose the following relation into 3NF:
        R(OrderId, CustomerName, ProductName, Quantity, Price, Total).
        Assume FDs: OrderId → CustomerName, ProductName → Price,
        OrderId,ProductName → Quantity. [5]

17.
    (a) What is metadata? What is a data dictionary? How does a DBMS use
        metadata for security enforcement? [5]
    (b) Explain entity integrity and referential integrity constraints.
        How do they help maintain data quality in a relational database? [5]
    (c) What is a derived attribute in ER model? Explain with an example.
        What is a multivalued attribute? [5]

18.
    (a) Explain serializability in DBMS. What is a precedence graph?
        How do you use it to check conflict serializability? Draw and
        explain for a given schedule. [7]
    (b) Explain the following anomalies with examples: dirty read, non-
        repeatable read, phantom read, lost update and write skew. [8]

19.
    (a) What is a B+ tree? Explain with a diagram. Insert the keys:
        15, 25, 35, 10, 20, 30, 40, 45, 50, 55, 60 into a B+ tree of
        order 4 from scratch, showing each intermediate step. [7]
    (b) Explain static hashing, extendible hashing and linear hashing.
        What is the main disadvantage of static hashing and how do dynamic
        hashing techniques solve it? [4]
    (c) What is blocking factor? How is it calculated? Show an example I/O
        cost difference between dense index and sparse index using blocking
        factor. [4]

20.
    (a) Explain ARIES recovery algorithm with the Analysis, Redo and Undo
        phases. What role does a checkpoint play? [7]
    (b) Explain view-based security in DBMS. How does a view help restrict
        access to sensitive data? [4]
    (c) What is a web-based database management system? List its components
        and how JDBC/ODBC fits into the architecture. [4]

------------------------------------------------------------------
END OF TEST 8
------------------------------------------------------------------
