MAKAUT DBMS — TEST 5
PCC-CS601 / PCCCS601
Time: 3 Hours    Full Marks: 70
[ER + SQL + Indexing cluster]

Instructions: Figures in the margin indicate full marks. Give answers in your own words as far as practicable.

------------------------------------------------------------------
GROUP A  (1 x 10 = 10)  — Very Short Answer Type
------------------------------------------------------------------

1. _______ is a software system that manages databases.
2. What is the full form of DML?
3. The _______ key is a candidate key chosen by the database designer to
   uniquely identify tuples.
4. In which normal form are all attributes fully functionally dependent on
   every candidate key and no partial dependency exists?
5. _______ is a balanced tree structure used as an index.
6. What is a heterogeneous database system?
7. The _______ is the high-level description of the database structure in a
   three-schema architecture.
8. What is a trigger in SQL?
9. The process of avoiding concurrent transactions interfering with each
   other is called _______ control.
10. _______ is a system of storing data across multiple geographically
    dispersed sites.

------------------------------------------------------------------
GROUP B  (5 x 3 = 15)  — Short Answer Type
------------------------------------------------------------------

11. Explain the different types of attributes in ER model with examples. [5]

12. What are the different types of indexes in DBMS? Differentiate between
    primary, secondary and clustering index. [5]

13. Explain join dependency with an example. [5]

14. What are the different commands in SQL? Briefly describe DDL, DML,
    DCL and TCL. [5]

15. Write short notes on: B-tree and B+ tree index structures. [5]

------------------------------------------------------------------
GROUP C  (15 x 3 = 45)  — Long Answer Type
------------------------------------------------------------------

16.
    (a) Draw an ER diagram for an Online Shopping System including at least
        5 entity sets, their attributes (with key attributes underlined),
        and relationships with proper cardinality ratios. State any
        assumptions you make. [7]
    (b) Convert the ER diagram from part (a) into relational schema. Specify
        the keys for each relation. [8]

17.
    (a) Explain the concept of data abstraction in DBMS. What are the three
        levels of data abstraction in ANSI-SPARC architecture? Describe each
        with an example. [7]
    (b) What is an ER model? Explain the terms: entity, attribute, entity set,
        relationship set, and degree of a relationship with examples. [8]

18.
    (a) Consider R(A, B, C, D, E, F) with FDs:
        F = {A → B, B → CD, E → F, AEF → B}.
        Find candidate keys for R. [4]
        (b) Is the decomposition of R into R1(A,B,C,D) and R2(A,E,F)
            lossless? Justify. [3]
        (c) Decompose R into 3NF if not already in 3NF. [4]
        (d) Is the above decomposition dependency preserving? [2]
        (e) Explain why dependency preservation is important. [2]

19.
    (a) What is serializability? Define serial schedule and serializable
        schedule. Explain conflict serializability with an example schedule. [5]
    (b) Describe timestamp-based concurrency control. Explain Thomas Write Rule
        with an example. [5]
    (c) Explain the ARIES recovery algorithm steps:
        (i) Analysis, (ii) Redo, (iii) Undo.
        How does a checkpoint help ARIES? [5]

20.
    (a) Write any 5 DDL commands in SQL with syntax. [3]
        Write any 5 DML commands in SQL with syntax. [2]
    (b) What is a view in SQL? Explain how views can be used for security
        with examples. [5]
    (c) Write short notes on MAC, DAC and RBAC in DBMS security. [5]

------------------------------------------------------------------
END OF TEST 5
------------------------------------------------------------------
