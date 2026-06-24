MAKAUT DBMS — TEST 7
PCC-CS601 / PCCCS601
Time: 3 Hours    Full Marks: 70
[ER-to-relational + joining the dots — integrated paper]

Instructions: Figures in the margin indicate full marks. Give answers in your own words as far as practicable.

------------------------------------------------------------------
GROUP A  (1 x 10 = 10)  — Very Short Answer Type
------------------------------------------------------------------

1. The person responsible for database design, security and maintenance is
   called the _______.
2. The normal form which eliminates transitive dependency is called _______.
3. _______ is a language used to describe the structure of a database.
4. In a distributed database, the property that hides the fact that data is
   fragmented is called _______ transparency.
5. What is the full form of NOSQL?   (No, just kidding.) What is the full
   form of ODBC?
6. A relationship that associates three entity sets is called a
   _______ relationship.
7. In SQL, _______ command is used to change the structure of a table.
8. What is the full form of PL/SQL?
9. The rule that allows us to infer A → C from A → B and B → C in FDs is
   called _______.
10. _______ keeps multiple versions of data so that readers do not block
    writers and vice versa.

------------------------------------------------------------------
GROUP B  (5 x 3 = 15)  — Short Answer Type
------------------------------------------------------------------

11. Differentiate between object-oriented DBMS and relational DBMS. [5]

12. What is a candidate key? How is it different from a primary key? What
    is an alternate key? [5]

13. What is referential integrity? Explain with an example involving two
    relations. [5]

14. Explain block addressing and blocking factor in file organizations. [5]

15. State the problems caused by redundancy in a database. How does
    normalization reduce them? [5]

------------------------------------------------------------------
GROUP C  (15 x 3 = 45)  — Long Answer Type
------------------------------------------------------------------

16.
    (a) Draw an ER diagram for an Examination System including entities:
        Student, Course, Exam, Result, and Instructor. Specify keys and
        at least 3 relationships with cardinality ratios. [5]
    (b) Convert your ER diagram into a relational schema. [5]
    (c) Suppose the Result relation stores grade, which depends on both
        Student and Course. Identify the functional dependencies and
        check whether the schema is in 3NF. [5]

17.
    (a) Explain the three-schema ANSI-SPARC architecture. How does logical
        data independence differ from physical data independence? Give one
        example of each. [7]
    (b) What is a data dictionary? How does a DBMS use it for integrity
        enforcement and query optimization? [8]

18.
    (a) Consider the relation R(A, B, C, D, E, F) and FDs:
        F = {A → BC, B → D, CD → E, E → F, FB → A}.
        Find all candidate keys of R. [5]
    (b) Decompose R into 3NF. Show each relation, its key, and the
        preserved FDs. [5]
    (c) Explain how you would check whether a given BCNF decomposition is
        also dependency preserving or not. [5]

19.
    (a) Explain the following in detail:
        (i) Dirty read (ii) Non-repeatable read (iii) Phantom read.
        Use a concrete schedule showing how each anomaly occurs. [5]
    (b) Explain 2PL with a diagram showing growing phase and shrinking phase.
        What is strict 2PL and why is it used in practice? [5]
    (c) What is the difference between timestamp protocol and 2PL? Which
        one prevents deadlocks more naturally? [5]

20.
    (a) Insert the following keys into a B+ tree of order 4:
        10, 20, 30, 40, 50, 25, 26, 27, 28, 29.
        Show all intermediate states clearly. [7]
    (b) What is extendible hashing? How does it avoid bucket overflow without
        reorganizing the entire file? [4]
    (c) Differentiate between foreign key and primary key with examples. [4]

------------------------------------------------------------------
END OF TEST 7
------------------------------------------------------------------
