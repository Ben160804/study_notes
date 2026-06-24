MAKAUT DBMS — TEST 4
PCC-CS601 / PCCCS601
Time: 3 Hours    Full Marks: 70
[Normalization-heavy / organizer classic]

Instructions: Figures in the margin indicate full marks. Give answers in your own words as far as practicable.

------------------------------------------------------------------
GROUP A  (1 x 10 = 10)  — Very Short Answer Type
------------------------------------------------------------------

1. The father of relational databases is _______.
2. _______ property of transaction states that either all operations of a
   transaction are reflected in the database or none.
3. _______ is the process of assigning temporary names to relations in
   relational algebra.
4. A key that uniquely identifies each row and cannot be NULL is called
   the _______ key.
5. In a B+ tree, data pointers are present only in the _______ nodes.
6. The full form of ACID is _______.
7. _______ index stores index entries for only some of the search-key values.
8. What is the full form of GRANT?
9. Which normal form handles transitive dependencies? (a) 1NF (b) 2NF (c) 3NF (d) BCNF
10. The rules used to find logically implied functional dependencies are
    called _______ axioms.

------------------------------------------------------------------
GROUP B  (5 x 3 = 15)  — Short Answer Type
------------------------------------------------------------------

11. State Armstrong's three axioms. [5]
12. Differentiate between dense index and sparse index. [5]
13. Explain the phases of strict two-phase locking (2PL). [5]
14. What is a data dictionary? How is it different from metadata? [5]
15. Write short notes on fragmentation and allocation transparency in DDBMS. [5]

------------------------------------------------------------------
GROUP C  (15 x 3 = 45)  — Long Answer Type
------------------------------------------------------------------

16.
    (a) What is a functional dependency (FD)? Explain the closure of a set
        of FDs with an example. [5]
    (b) Explain lossless join decomposition. Under what condition is a
        decomposition guaranteed to be lossless? [5]
    (c) Differentiate between 3NF and BCNF. Give an example where 3NF is
        satisfied but BCNF is not. [5]

17.
    (a) Consider the relation R(Id, Name, Dept, Course, Instructor) with
        F = {Id → Name, Id → Dept, Dept → Course, Course → Instructor}.
        Decompose R into BCNF. Show each step. [7]
    (b) Explain the need for query optimization. Describe a heuristic
        optimization strategy that uses: (i) cascade of σ, (ii) commute σ
        and π, (iii) commute σ and ×. [8]

18.
    (a) Insert the following keys into a B-tree of order 4:
        50, 30, 70, 20, 40, 60, 80, 35, 45, 55, 65.
        Show all intermediate tree states clearly. [7]
    (b) Explain hashing techniques used in DBMS. What is bucket overflow?
        How is it handled in static and dynamic hashing? [8]

19.
    (a) Explain the ACID properties of a transaction with one example for
        each property. [5]
    (b) What is serializability? Differentiate between conflict serializable
        and view serializable schedules. [5]
    (c) Explain timestamp-based concurrency control with a read/write
        example showing Thomas Write Rule. [5]

20.
    (a) Differentiate between centralized databases and distributed databases.
        What are the key responsibilities of a DBA in a DDBMS? [5]
    (b) Explain the following data warehouse characteristics with examples:
        subject-oriented, integrated, time-variant, non-volatile. [5]
    (c) What is the difference between an OODBMS and an ORDBMS? Give two
        advantages of ORDBMS over RDBMS. [5]

------------------------------------------------------------------
END OF TEST 4
------------------------------------------------------------------
