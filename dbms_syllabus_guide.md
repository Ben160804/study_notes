# Database Management Systems — Complete Syllabus-Aligned Study Guide

## Syllabus (PCC-CS601, 36L, 6 Units)

| Unit | Hours | Topics | Status |
|------|-------|--------|--------|
| Unit 1 | 9 | Architecture, abstraction, independence, DDL/DML, data models (network, OO, relational, ER), integrity constraints | ✅ Covered |
| Unit 2 | 13 | Relational algebra/calculus (tuple + domain), SQL3, DDL/DML, MySQL/Oracle/DB2/SQL Server, normalization (FD, Armstrong's axioms, 1NF-3NF-BCNF, dependency preservation, lossless join), query processing/optimization | ✅ Covered with gaps closed |
| Unit 3 | 3 | Storage strategies: Indices, B-trees, Hashing | ✅ Covered with hashing added |
| Unit 4 | 5 | Transactions: ACID, serializability, locking & timestamp schedulers, multiversion & optimistic CC, recovery | ✅ Covered with all CC methods added |
| Unit 5 | 3 | Security: authentication, authorization, DAC/MAC/RBAC, intrusion detection, SQL injection | ✅ Covered |
| Unit 6 | 3 | Advanced: OO DB, ORDBMS, logical DBs, web DBs, DDBMS, DWDM | ✅ Covered |

Primary files:
- /home/bigfoot/SEM-6-CSE/study_notes/dbms_organizer_study_notes.md
- /home/bigfoot/SEM-6-CSE/study_notes/dbms_remaining_topics.md

---

## UNIT 1: Architecture, Keys, ER Model, Data Models (9 hrs)

### PYQs (from organizer)
- Three-schema architecture — WBUT 2006, 2013
- DBA role/functions — WBUT 2006, 2008, 2017, 2018
- Logical vs physical data independence — WBUT 2006, 2015
- Candidate / super / primary / alternate key — WBUT 2006, 2013, 2015, 2017, 2019
- Data abstraction levels — WBUT 2015
- Data dictionary — WBUT 2013, 2015, 2017, 2019
- Weak vs strong entity — WBUT 2006, 2010, 2016, 2019
- Cardinality ratio — WBUT 2013, 2017
- Degree of relationship — WBUT 2015
- Attribute types — WBUT 2017
- Specialization / generalization — WBUT 2010, 2011

### Must-know

**1. Three-schema architecture**
- External level (user views)
- Conceptual level (logical structure)
- Internal level (physical storage)
- Mappings between levels

**2. Data independence**
- Logical data independence: change conceptual without changing external
- Physical data independence: change internal without changing conceptual

**3. Key hierarchy**
- Superkey: uniquely identifies a row
- Candidate key: minimal superkey
- Primary key: chosen candidate key
- Alternate key: candidate keys not chosen as primary

**4. ER Model**
- Entity, relationship, attributes
- Cardinality ratio: 1:1, 1:N, M:N
- Degree of relationship: number of entities participating
- Weak entity: depends on another entity for identification
- Strong entity: independent existence
- Specialization / generalization: top-down / bottom-up hierarchy

**5. Data models**
- Relational model: tables, rows, columns
- Network model: sets, owner-member relationships
- Object-oriented model: objects, classes, inheritance, methods
- Entity-relationship model: conceptual view

**6. Integrity constraints**
- Entity integrity: primary key cannot be NULL
- Referential integrity: foreign key must reference existing primary key or be NULL
- Domain integrity: valid range of values
- User-defined integrity: custom business rules

**7. Data dictionary / catalog**
- Stores metadata: table names, column names, types, constraints, indexes
- Used by DBMS to manage schema

---

## UNIT 2: Relational Model, SQL, Normalization (13 hrs)

### PYQs (from organizer)
- Relational algebra MCQ / short notes — WBUT 2007, 2019
- Theta join — WBUT 2009
- Tuple relational calculus — model question
- Domain relational calculus — WBUT (relevant per syllabus)
- Functional dependencies and closure — recurring
- Armstrong’s axioms — WBUT 2008, 2009, 2010, 2012, 2017, 2018
- 1NF / 2NF / 3NF / BCNF definitions and decomposition — recurring
- Lossless join + dependency preservation — recurring
- BCNF is stricter than 3NF — WBUT 2009
- PLANE_INFO BCNF-style decomposition — WBUT PYQ
- Query processing / optimization — covered, lower frequency

### Must-know

**1. Relational algebra**
- Selection (σ)
- Projection (π)
- Union (∪), Set difference (-)
- Cartesian product (×)
- Rename (ρ)
- Join (⋈): theta join, equi-join, natural join

**2. Tuple relational calculus**
- {t | P(t)} — set of tuples satisfying predicate P
- Non-procedural: describes what, not how

**3. Domain relational calculus** (syllabus-required)
- {<x1, x2, ...> | P(x1, x2, ...)}
- Uses domain variables instead of tuple variables

**4. SQL3**
- Object-relational extensions
- User-defined types (UDTs)
- Inheritance in SQL
- Reference types
- Array and multiset types

**5. DDL / DML**
- DDL: CREATE, ALTER, DROP — defines schema
- DML: SELECT, INSERT, UPDATE, DELETE — manipulates data
- DCL: GRANT, REVOKE — controls access
- TCL: COMMIT, ROLLBACK, SAVEPOINT — transaction control

**6. DBMS products**
- MySQL: open-source, widely used, Oracle-owned
- Oracle: commercial, enterprise-grade
- DB2: IBM product
- SQL Server: Microsoft product

**7. Functional dependencies (FD)**
- X → Y means Y is functionally determined by X
- Trivial FD: Y ⊆ X
- Non-trivial FD: Y ⊄ X
- Fully non-trivial: X ∩ Y = ∅

**8. Armstrong’s axioms**
- Reflexivity: Y ⊆ X → X → Y
- Augmentation: X → Y → XZ → YZ
- Transitivity: X → Y, Y → Z → X → Z
- Derived: Union, Decomposition, Pseudo-transitivity

**9. Normalization workflow**
- 1NF: atomic values, no repeating groups
- 2NF: 1NF + no partial dependency on candidate key
- 3NF: 2NF + no transitive dependency on candidate key
- BCNF: every determinant must be superkey (stricter than 3NF)

**10. Normalization checklist**
1. Write all FDs clearly
2. Compute candidate key by closure
3. State current NF
4. Identify violating dependencies
5. Decompose step-by-step
6. Mention lossless join / dependency preservation

**11. Lossless join**
- Decomposition R → (R1, R2) is lossless if R1 ∩ R2 → R1 or R1 ∩ R2 → R2
- Guarantees no spurious tuples on join

**12. Dependency preservation**
- Decomposition preserves FD if union of projected FDs implies all original FDs
- BCNF decomposition may not preserve dependencies

---

## UNIT 3: Storage, Indexing, B-tree, Hashing (3 hrs)

### PYQs (from organizer)
- B-tree vs B+tree — WBUT 2008, 2011, 2016
- Dense vs sparse index — WBUT 2011
- Primary / secondary / clustering index — WBUT 2006, 2011, 2013, 2018
- Block factor — WBUT 2015

### Must-know

**1. Index types**
- Primary index: on primary key, physically ordered file
- Secondary index: on non-key field, may be dense or sparse
- Clustering index: on non-key field but records with same value stored together

**2. Dense vs sparse index**
- Dense: index entry for every search key value
- Sparse: index entry for some search key values (usually primary index)

**3. B-tree**
- Balanced tree
- Keys and data in internal + leaf nodes
- Search may stop at internal node
- Variable fanout

**4. B+tree**
- All data in leaf nodes
- Internal nodes are routing only
- Leaf nodes linked sequentially → excellent for range queries
- Higher fanout than B-tree → fewer levels

**5. B-tree vs B+tree comparison**
| | B-tree | B+tree |
|--|--------|--------|
| Data location | Internal + leaf nodes | Leaf nodes only |
| Range query | Must traverse internal | Follow leaf links |
| Search | May stop early | Always reaches leaf |
| Fanout | Lower | Higher |
| Use | Fewer records | Many records / range scans |

**6. Hashing** (syllabus-required)
- Static hashing: bucket = hash(key) mod M
- Bucket overflow → chaining or open addressing
- Dynamic hashing: extendible hashing / linear hashing
- Hash index: O(1) expected equality search
- Problem: range queries terrible

**7. Blocking factor**
- floor(B / R) where B = block size, R = record size
- Number of records that fit in one disk block

---

## UNIT 4: Transactions, Concurrency, Recovery (5 hrs)

### PYQs (from organizer)
- ACID — WBUT 2007, 2009, 2013, 2015, 2016, 2017, 2019
- 2PL — WBUT 2008, 2012, 2015, 2017, 2018
- 2PL MCQs — WBUT 2006, 2007, 2008, 2019
- Locking vs timestamp / 2PL vs timestamp — WBUT 2014, 2019
- Log-based recovery / checkpoints — WBUT 2010, 2014, 2016, 2017, 2018, 2019

### Must-know

**1. ACID properties**
- Atomicity: all-or-nothing
- Consistency: transaction preserves DB invariants
- Isolation: concurrent transactions don’t interfere
- Durability: committed changes survive failures

**2. Serializability**
- Schedule is serializable if it is equivalent to some serial schedule
- Conflict-serializable: if conflict graph is acyclic
- View-serializable: equivalent by read/write view
- Conflict-serializable is stricter and easier to test

**3. Two-Phase Locking (2PL)**
- Growing phase: acquire locks, no releases
- Shrinking phase: release locks, no new acquires
- Guarantees conflict-serializability
- Strict 2PL: holds exclusive locks until commit → easy recovery

**4. Locking types**
- Shared lock (S): read, multiple allowed
- Exclusive lock (X): write, exclusive access

**5. Timestamp-based concurrency control**
- Each transaction gets timestamp on start
- Read/Write checks against timestamps
- Older transactions get priority
- Wound-wait / wait-die schemes
- Can cause cascading aborts

**6. Multiversion concurrency control (MVCC)**
- Keeps multiple versions of data items
- Readers don’t block writers
- Writers don’t block readers
- Each transaction reads appropriate version based on timestamp
- Used in PostgreSQL, Oracle, etc.

**7. Optimistic concurrency control**
- No locks during execution
- Three phases: read (collect read/write sets), validation (check for conflicts), write (commit if valid)
- Works best when conflict probability is low

**8. Comparison: CC methods**

| Method | Locking | Priority | Writers block readers? |
|--------|---------|----------|----------------------|
| 2PL | Yes | By lock order | Yes |
| Timestamp | No | By age (timestamp) | No, but aborts |
| MVCC | No | By version | No |
| Optimistic | No | By validation | No |

**9. Recovery concepts**

Immediate update vs deferred update:
- Immediate update: pages can be updated during transaction (UNDO + REDO needed)
- Deferred update: pages updated only at commit (REDO only)

Write-Ahead Logging (WAL):
- Log written before actual data modification
- log force = write log to stable storage before commit

Checkpoint:
- Periodically flush modified pages to disk
- Write checkpoint record to log
- Recovery after crash starts from last checkpoint
- REDO: reapply committed but not-flushed transactions
- UNDO: rollback uncommitted transactions

---

## UNIT 5: Security (3 hrs)

### PYQs (from organizer)
- Authentication vs authorization
- GRANT / REVOKE
- DAC / MAC / RBAC
- SQL injection basics
- Intrusion detection short notes

### Must-know

**1. Authentication**
- Verifying identity: who are you?
- Methods: password, biometrics, Kerberos, digital certificates

**2. Authorization**
- What resources you can access after authentication

**3. DAC (Discretionary Access Control)**
- Owner sets permissions
- GRANT / REVOKE in SQL
- Flexible but harder to audit centrally

**4. MAC (Mandatory Access Control)**
- System-enforced labels (Top Secret, Secret, Confidential, Unclassified)
- No overrides by users
- Bell-LaPadula model: no read up, no write down

**5. RBAC (Role-Based Access Control)**
- Permissions assigned to roles
- Users assigned to roles
- Easier administration in large orgs

**6. SQL injection**
- Malicious input alters query semantics
- Example: `' OR '1'='1` in login form
- Prevention: parameterized queries / prepared statements

---

## UNIT 6: Advanced Topics (3 hrs)

### PYQs (from organizer)
- OO DB short notes
- ORDBMS
- Logical DBs
- Web DBs
- DDBMS
- Data Warehousing & Mining

### Must-know (short-note depth)

**1. Object-oriented DB (OODB)**
- Stores objects instead of rows
- Supports complex data types, inheritance, methods
- ODL / OQL

**2. Object-relational DB (ORDBMS)**
- Extends RDBMS with object features
- User-defined types, inheritance, table functions
- Examples: PostgreSQL, Oracle object extensions

**3. Logical DBs**
- Deductive databases
- Datalog, rules, inference
- Knowledge in addition to data

**4. Web DBs**
- Database accessible via web
- CGI, PHP, ASP, JDBC/ODBC connectors
- Server-side scripting

**5. Distributed DBs**
- Already covered in DDBMS subject
- Here: short-note contrast with centralized

**6. Data Warehousing & Mining**
- Already covered in DWDM subject
- Here: short-note contrast with operational DBs

---

## Absolute Priority Order for DBMS
1. Normalization + FDs + Armstrong
2. ACID + 2PL + Recovery + all CC methods
3. ER Model + Keys + Architecture
4. B+tree + Indexing + Hashing
5. Security
6. Advanced topics

---

## Fast Revision Sheet

Must know cold:
- 3-schema architecture
- Data independence (logical + physical)
- Key hierarchy
- ER model basics
- Armstrong’s axioms
- 1NF / 2NF / 3NF / BCNF
- Lossless join / dependency preservation
- ACID
- 2PL and strict 2PL
- Serializability (conflict-serializable)
- All 4 CC methods: 2PL, Timestamp, MVCC, Optimistic
- WAL / checkpoint / REDO / UNDO
- Primary / secondary / clustering index
- Dense vs sparse index
- B-tree vs B+tree
- Hashing basics
- DAC / MAC / RBAC
- SQL injection

---

## Where each existing note fits
- dbms_organizer_study_notes.md = broad PYQ bank
- dbms_remaining_topics.md = best for final revision of ACID, 2PL, recovery, indexing, Armstrong, ER model

Recommended use:
1. Use this file for syllabus map and priority.
2. Use dbms_remaining_topics.md for memorization and exam answers.
3. Use dbms_organizer_study_notes.md only when you need original PYQ wording.

---

## Honest exam strategy
If time is short, DBMS marks come mostly from:
- normalization
- ACID / 2PL / recovery / all CC methods
- ER model
- indexing / B+tree

Those four buckets alone can carry the paper.
