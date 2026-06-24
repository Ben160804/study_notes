MAKAUT DBMS — TEST 10
PCC-CS601 / PCCCS601
Time: 3 Hours    Full Marks: 70
[Hard-mode retest — decompositions + scheduling + file org focus]

Instructions: Figures in the margin indicate full marks. Give answers in your own words as far as practicable.

------------------------------------------------------------------
GROUP A  (1 x 10 = 10)  — Very Short Answer Type
------------------------------------------------------------------

1. The full form of ACID is atomicity, consistency, isolation and _______.
2. In ER modeling, an attribute that can have multiple values for a single
   entity is called a _______ attribute.
3. A relation in BCNF is always in _______.
4. The SQL command to roll back an incomplete transaction is _______.
5. _______ transparency hides how data is divided into fragments in a DDBMS.
6. What is the full form of ODBC?
7. A node in a B-tree is called a/an _______ if it has no child nodes.
8. The _______ property of ACID ensures that the database remains consistent
   before and after a transaction.
9. What is a superkey?
10. _______ concurrency control allows readers and writers to proceed in
    parallel without blocking each other.

------------------------------------------------------------------
GROUP B  (5 x 3 = 15)  — Short Answer Type
------------------------------------------------------------------

11. Explain schema refinement through normalization. Why is redundancy
    harmful in relational databases? [5]

12. Differentiate between SELECT, PROJECT and JOIN operations in relational
    algebra with small examples. [5]

13. What is locking? Differentiate between shared lock (S) and exclusive
    lock (X). [5]

14. Explain the difference between horizontal fragmentation and vertical
    fragmentation in DDBMS. [5]

15. What is object-oriented DBMS? What advantages does it have over RDBMS
    for certain application domains? [5]

------------------------------------------------------------------
GROUP C  (15 x 3 = 45)  — Long Answer Type
------------------------------------------------------------------

16.
    (a) Explain the ACID properties with one example each. [5]
    (b) What is serializability? Differentiate between serial schedule and
        serializable schedule. Define conflict serializable and view
        serializable schedules. [5]
    (c) Given the following schedule S on transactions T1, T2, T3:

        T1: R(X) W(X)
        T2: R(X) R(Y) W(X)
        T3: R(Y) W(X)

        Construct the precedence graph and determine whether S is conflict
        serializable. [5]

17.
    (a) Consider R(A,B,C,D,E,F) with FDs:
        F = {A→B, B→C, C→D, D→E, DE→F, F→A}.
        Find the candidate key(s) of R. [4]
    (b) Decompose R into BCNF showing each step with the violating FD picked
        for decomposition. [6]
    (c) Is the final BCNF decomposition dependency preserving? Explain why
        or why not. [5]

18.
    (a) Explain the file organization types: sequential, indexed sequential,
        and hashed. Compare them in terms of access time, storage efficiency
        and update flexibility. [7]
    (b) What is a B+ tree? Explain why it is preferred as a primary index
        structure over B-tree. [4]
    (c) What is blocking factor? Show the formula and use it to compare the
        I/O cost of full table scan, dense index scan and sparse index
        scan for a relation of 10,000 records stored in blocks of size 1KB
        with record size 100 bytes. [4]

19.
    (a) Explain immediate-update recovery with undo/redo logging. Give an
        example log sequence for a transaction that updates two data items
        and then commits. [7]
    (b) What is a checkpoint? How does it improve recovery time? Explain
        with a simple example. [4]
    (c) What is ARIES? Briefly describe its three main phases. [4]

20.
    (a) What is an ER diagram? Explain the terms: entity, entity set,
        relationship set, degree, and cardinality ratio. [5]
    (b) Explain relational model concepts: domain, tuple, attribute,
        relation, and tuple variable. [5]
    (c) What is a tuple relational calculus expression? Give its general
        syntax and one query example. [5]

------------------------------------------------------------------
END OF TEST 10
------------------------------------------------------------------
