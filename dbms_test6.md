MAKAUT DBMS — TEST 6
PCC-CS601 / PCCCS601
Time: 3 Hours    Full Marks: 70
[Recovery / Concurrency / Heuristics / B-tree deep dives]

Instructions: Figures in the margin indicate full marks. Give answers in your own words as far as practicable.

------------------------------------------------------------------
GROUP A  (1 x 10 = 10)  — Very Short Answer Type
------------------------------------------------------------------

1. _______ is a no-overwrite recovery method where the database is not
   updated until the transaction commits.
2. A schedule that is equivalent to some serial schedule is called a
   _______ schedule.
3. The _______ protocol allows only exclusive locks and no lock conversions.
4. A B+ tree leaf node contains _______ pointers to the next leaf node
   for fast range queries.
5. _______ is the property that allows a transaction to see its own
   uncommitted changes during execution.
6. What is the full form of WAL?
7. In hashing, a hash function maps a search key to a _______.
8. What is a multivalued dependency? (one-line answer)
9. What is the full form of MVCC?
10. The two types of failures addressed by ARIES are system failures and
    _______ failures.

------------------------------------------------------------------
GROUP B  (5 x 3 = 15)  — Short Answer Type
------------------------------------------------------------------

11. What are the ACID properties? Explain each with one example. [5]

12. Explain the difference between immediate update and deferred update
    recovery techniques. [5]

13. What are the phases of two-phase locking (2PL)? Explain strict 2PL. [5]

14. Explain the difference between B-tree and B+ tree. Why is B+ tree
    preferred for database indexing? [5]

15. What is a data warehouse? How does it differ from a traditional
    operational database? [5]

------------------------------------------------------------------
GROUP C  (15 x 3 = 45)  — Long Answer Type
------------------------------------------------------------------

16.
    (a) What is a transaction? Explain the ACID properties in detail with
        suitable examples. [5]
    (b) Explain the concept of serializability. How do you check conflict
        serializability using a precedence graph? Given a schedule, show
        how to construct the graph and detect cycles. [5]
    (c) What is dirty read? Explain with an example. What is lost update?
        How does strict 2PL prevent lost updates? [5]

17.
    (a) Explain log-based recovery using immediate update with UNDO/REDO.
        Write the log sequence for a simple transaction example. [7]
    (b) What is a checkpoint in recovery? Explain how ARIES analysis,
        redo and undo phases work with checkpoint support. [8]

18.
    (a) Differentiate between:
        (i) Static hashing and dynamic hashing
        (ii) Extendible hashing and linear hashing.
        (iii) Good hashing function properties. [7]
    (b) Explain blocking factor (bfr). How does blocking factor affect the
        cost of a full table scan versus an indexed scan? [4]
    (c) What is the difference between ordered index and hash index?
        When would you use each? [4]

19.
    (a) What is heuristic query optimization? Describe the standard
        heuristic rules used in query optimization with examples. [7]
    (b) Consider the following RA expression:
        σDept='CSE'(Employee ⋈ Department)
        Show one optimization step using: selection before join. [3]
        Explain why this rewriting improves performance. [5]

20.
    (a) Explain the following integrity constraints in DBMS with examples:
        (i) Entity integrity (ii) Referential integrity (iii) Domain
        integrity (iv) User-defined integrity. [5]
    (b) Differentiate between DAC, MAC and RBAC with a table comparing
        ownership, labels, flexibility and common use cases. [5]
    (c) What is SQL injection? Give one example. How do prepared statements
        prevent it? [5]

------------------------------------------------------------------
END OF TEST 6
------------------------------------------------------------------
