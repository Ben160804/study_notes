MAKAUT DBMS — TEST 3
PCC-CS601 / PCCCS601
Time: 3 Hours    Full Marks: 70
[Focused on 2024–2025 high-frequency + organizer weak spots]

Instructions: Figures in the margin indicate full marks. Give answers in your own words as far as practicable. Answer ANY 10 from Group-A, ANY 3 from Group-B, ANY 3 from Group-C.

------------------------------------------------------------------
GROUP A  (1 x 10 = 10)  — Very Short Answer Type
------------------------------------------------------------------

1. What is the full form of RDBMS?
2. _______ is used to roll back a transaction to a previously saved state.
3. Which normal form deals with multivalued dependencies?  (a) 3NF (b) 4NF
4. The process of assigning privileges to users is called _______.
5. In ER model, a relationship that connects more than two entity sets is
   called an _______ relationship.
6. What is a weak entity set?
7. Which SQL command removes all rows from a table but keeps the structure? 
   (a) DROP   (b) DELETE   (c) TRUNCATE   (d) ALTER
8. What is log-based recovery in DBMS?
9. Under which normal form is every non-prime attribute fully functionally
   dependent on every candidate key?
10. Which concurrency control protocol orders transactions based on their
    timestamps? (a) 2PL (b) Timestamp protocol (c) MVCC (d) Optimistic CC

------------------------------------------------------------------
GROUP B  (5 x 3 = 15)  — Short Answer Type
------------------------------------------------------------------

11. What are the different types of attributes in ER model? Explain each
    with an example. [5]

12. Differentiate between 1NF, 2NF and 3NF with suitable examples. [5]

13. Write short notes on strong entity set and weak entity set with examples. [5]

14. Explain the difference between centralized and distributed database
    systems. List the advantages of DDBMS. [5]

15. What is SQL injection? How can it be prevented? [5]

------------------------------------------------------------------
GROUP C  (15 x 3 = 45)  — Long Answer Type
------------------------------------------------------------------

16.
    (a) With a neat diagram, explain the three-schema architecture. What do
        you mean by logical data independence and physical data independence?
        Explain with examples. [5]
    (b) Explain the concept of serializability. How does a precedence graph
        help in checking conflict serializability? Draw a precedence graph
        for a given schedule if asked. [5]
    (c) What is a checkpoint in recovery management? Explain how it reduces
        recovery time in ARIES-style recovery. [5]

17.
    (a) What is a B+ tree? How does it differ from a B-tree? Insert the
        following keys into a B+ tree of order 3:
        1, 4, 7, 10, 17, 20, 35, 42.
        Show intermediate steps clearly. [5]
    (b) What are different concurrency anomalies? Explain dirty read,
        unrepeatable read, phantom read and lost update with concrete examples. [5]
    (c) Explain heuristic query optimization with an example showing the
        transformation sequence from an initial query tree. [5]

18.
    (a) Consider a relation R(A, B, C, D, E) and functional dependencies:
        F = {A → BC, B → D, CD → E, E → A}.
        (i) Find the candidate keys of R. [2]
        (ii) Is the decomposition into R1(A,B,C) and R2(C,D,E) lossless? [2]
        (iii) Is the above decomposition dependency preserving? [1]
    (b) Explain vertical and horizontal fragmentation in DDBMS with diagrams
        or examples. What is allocation transparency? [5]
    (c) What is a data warehouse? How does it differ from a transactional
        (OLTP) database? List its characteristics. [5]

19.
    (a) Explain the GRANT and REVOKE commands with syntax and examples.
        How does a view-based security mechanism restrict access to sensitive
        columns? [5]
    (b) Differentiate between DAC, MAC and RBAC with examples of each.
        Which model is most commonly used in modern DBMS and why? [5]
    (c) What is the difference between a trigger and a stored procedure?
        Explain with examples. [5]

20.
    (a) What is an ER diagram? Draw an ER diagram for a Library Management
        System with at least 4 entity sets, 2 relationships, and appropriate
        attributes including one weak entity set. [5]
    (b) Explain DDL and DML commands with examples for each. Also write the
        difference between TRUNCATE, DELETE and DROP. [5]
    (c) What is meant by blocking factor? How does it affect I/O cost in
        index-based retrieval? [5]

------------------------------------------------------------------
END OF TEST 3
------------------------------------------------------------------
