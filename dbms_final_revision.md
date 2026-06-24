# DBMS Final Revision Guide — PCC-CS601

Syllabus-first. Exam-first. No fluff.

Note on recent papers:
- Verified MAKAUT DBMS PYQs available to me in this session: 2022, 2023, 2024, 2025.
- I also checked public archives for 2020 and 2021, but I could not verify separate DBMS paper pages for those years in a reliable way.
- Organizer PYQs below cover the older MAKAUT/WBUT bank and are grouped topic-wise.

---

## Unit 1 — Architecture, Keys, ER Model, Data Models, Integrity

### 1) Database architecture + abstraction + independence
Must know:
- 3 levels: external, conceptual, internal
- data abstraction levels
- logical vs physical data independence
- data dictionary / metadata / system catalog

Organizer PYQs:
- Three-schema architecture — L30, L219
- Data abstraction levels — L218
- Logical vs physical data independence — L235, L517-L519
- Data dictionary / metadata — L9, L341, L345, L515, L616

Recent MAKAUT papers:
- 2025: subsystems of a typical database system structure; data abstraction help in managing complexity
- 2024: data dictionary; database system structure; DBA role
- 2023: metadata; data dictionary

### 2) DBA
Must know:
- schema definition
- storage/access methods
- authorization/GRANT/REVOKE
- integrity constraints
- security and backup
- routine maintenance

Organizer PYQs:
- DBA role/functions — L60, L62, L64, L66
- Security-related DBA duties — L82-L100

Recent MAKAUT papers:
- 2025: DBA security responsibilities
- 2024: DBA role in data abstraction question
- 2023: DBA functions

### 3) Keys
Must know:
- superkey, candidate key, primary key, alternate key, foreign key
- candidate key = minimal superkey

Organizer PYQs:
- Key hierarchy — L262, L264, L267, L390, L393, L478, L504-L507

Recent MAKAUT papers:
- 2025: keys and commonly used keys in DBMS
- 2024: key-related MCQs via relational/ER questions
- 2023: primary key / foreign key style questions appear repeatedly

### 4) ER model
Must know:
- entity, attribute, relationship
- entity set, relationship set
- degree of relationship
- cardinality ratio
- weak entity / strong entity
- specialization and generalization
- types of attributes

Organizer PYQs:
- Weak entity / strong entity — L330, L448, L450-L459, L489
- Cardinality ratio — L396, L940
- Degree of relationship — L414, L416
- Attribute types — L460, L474
- Specialization/generalization — L229, L501, L581

Recent MAKAUT papers:
- 2025: multivalued attribute; strong entity; generalization/specialization; ER extensions; degree of relationship
- 2024: rectangles in ER diagram, weak entity, cardinality, E-R construction question
- 2023: strong entity, weak entity, derived attribute

### 5) Data models
Must know:
- relational model: tables, rows, columns
- network model: owner-member/set based
- object-oriented model: objects, classes, inheritance, methods
- ER model: conceptual design model

Organizer PYQs:
- Data model / DBMS vs file system / specialization-generalization — assorted around L258, L406, L418, L863

Recent MAKAUT papers:
- 2024: top-to-bottom relationship / hierarchical schema MCQ, DBMS vs Google MCQ
- 2025: homogeneous vs heterogeneous DBMS

### 6) Integrity constraints
Must know:
- entity integrity: primary key cannot be NULL
- referential integrity: FK must reference existing PK or be NULL
- domain integrity: valid range/format
- user-defined integrity: business rules

Organizer PYQs:
- Integrity constraints — L3541
- Entity integrity MCQ — L642
- Referential integrity lines — L300, L725-L732

Recent MAKAUT papers:
- 2024: referential integrity MCQ

---

## Unit 2 — Relational Model, SQL, Normalization, Query Optimization

### 1) Relational algebra
Must know:
- selection, projection, union, difference, cartesian product, rename
- joins: theta, equi, natural

Organizer PYQs:
- Relational algebra MCQ/shorts — L635, L648, L746, L849
- Theta join — L635+ around the query block

Recent MAKAUT papers:
- 2025: joins in SQL; relational algebra + SQL on Student/Course/Instructor schema
- 2024: fundamental relational algebra operation = Cartesian product
- 2023: relational algebra queries; Cartesian product

### 2) Relational calculus
Must know:
- tuple relational calculus: {t | P(t)}
- domain relational calculus: uses domain variables
- non-procedural meaning

Organizer PYQs:
- Tuple relational calculus — L931
- Domain relational calculus — syllabus-required / scattered in organizer

Recent MAKAUT papers:
- 2023: features of tuple relational calculus

### 3) SQL and command families
Must know:
- DDL: CREATE, ALTER, DROP, TRUNCATE
- DML: SELECT, INSERT, UPDATE, DELETE
- DCL: GRANT, REVOKE
- TCL: COMMIT, ROLLBACK, SAVEPOINT
- SQL3: UDTs, inheritance, arrays, multisets, references

Organizer PYQs:
- DDL/DML and SQL command questions are scattered through the organizer
- DELETE/TRUNCATE/DROP — L2023 paper style, also organizer question bank around DDL/DML blocks

Recent MAKAUT papers:
- 2025: differences between DROP, TRUNCATE, DELETE; JOINs supported by SQL
- 2024: DML definition; SQL injection MCQ; granularities
- 2023: ALTER column; DELETE/TRUNCATE/DROP; SQL character function; DML/TCL/metadata

### 4) Functional dependencies and Armstrong’s axioms
Must know:
- FD: X → Y
- closure of F, attribute closure
- Armstrong axioms: reflexivity, augmentation, transitivity
- derived rules: union, decomposition, pseudo-transitivity

Organizer PYQs:
- Armstrong axioms — L1818, L1941, L1973
- FD / closure / composite keys — L1531, L1603, L1682, L1702

Recent MAKAUT papers:
- 2023: Armstrong’s three axioms; functional dependency; join dependency; closure mentioned

### 5) Normalization
Must know:
- 1NF: atomic values
- 2NF: no partial dependency
- 3NF: no transitive dependency
- BCNF: every determinant is a superkey
- dependency preservation
- lossless join

Organizer PYQs:
- Normalization / anomalies — L1513-L1560
- BCNF vs 3NF — L1576-L1605, L1691
- Lossless decomposition — L1649-L1667, L1706-L1721, L1922, L1962, L2023, L2039
- 3NF decomposition — L2182-L2211
- Advantages of normalization — L1761

Recent MAKAUT papers:
- 2025: none as a direct long question, but normalization is a recurring core bucket
- 2024: heuristic optimization + anomalies
- 2023: lossless and lossy decomposition; 3NF decomposition; 4NF MCQ; update anomalies

### 6) Query optimization / query processing
Must know:
- why optimization is needed
- heuristic-based optimization
- query execution plan
- rewrite and cost-based choice

Organizer PYQs:
- Query optimization — L687, L794, L812-L841

Recent MAKAUT papers:
- 2024: heuristic based optimization
- 2025: SQL query solving + joins, grouped counts

---

## Unit 3 — Storage, Indexing, B-tree, Hashing

### 1) Index basics
Must know:
- index = auxiliary structure for fast retrieval
- primary, secondary, clustering index
- ordered index

Organizer PYQs:
- Primary / secondary / clustering index — L2657-L2681, L2777-L2781, L2958-L2959

Recent MAKAUT papers:
- 2025: index where index table and database table have same records -> dense index idea
- 2024: indexing MCQs
- 2023: B-tree / B+tree short notes

### 2) Dense vs sparse
Must know:
- dense: entry for every key
- sparse: entry for some keys only

Organizer PYQs:
- Dense vs sparse — L2863-L2873, L2784-L2785

### 3) Blocking factor
Must know:
- bfr = floor(B/R)
- number of records per block

Organizer PYQs:
- Blocking factor — L2682-L2693, L2928-L2946

Recent MAKAUT papers:
- 2024: granularity MCQ; blocking factor in organizer and recent B-tree questions

### 4) B-tree and B+tree
Must know:
- B-tree: balanced multiway tree, data can appear in internal and leaf nodes
- B+tree: data only in leaf nodes, internal nodes route search
- B+tree leaf links help range queries

Organizer PYQs:
- B-tree vs B+tree — L2682-L2709, L2836-L2841, L2860-L2907, L2951-L2959

Recent MAKAUT papers:
- 2025: sparse index, data structure questions, indexing topic cluster
- 2024: B-tree insertion question
- 2023: B-tree vs B+tree; insert in B-tree of order 4

### 5) Hashing
Must know:
- static hashing: fixed buckets
- collisions cause bucket overflow
- dynamic hashing: extendible/linear hashing
- good for equality search, bad for range queries

Organizer PYQs:
- Bucket overflow in hash file organization — L2822-L2835

Recent MAKAUT papers:
- 2023: different hashing techniques

---

## Unit 4 — Transactions, Concurrency Control, Recovery

### 1) Transaction basics and ACID
Must know:
- atomicity, consistency, isolation, durability
- transaction = all-or-nothing unit of work

Organizer PYQs:
- ACID — L3077-L3085, L3335 onward, L4587

Recent MAKAUT papers:
- 2025: ACID, dirty read
- 2024: ACID
- 2023: ACID, isolation, checkpoint

### 2) Serializability
Must know:
- serial schedule
- serializable schedule
- conflict serializability = precedence graph acyclic
- view serializability is theoretical and harder to test

Organizer PYQs:
- Serializability / deadlock / schedule problems — around L3435-L3450 and the transaction sections

Recent MAKAUT papers:
- 2025: 2PL and schedule-related concept questions
- 2024: locking vs timestamp

### 3) Locking and 2PL
Must know:
- shared lock (S)
- exclusive lock (X)
- growing phase and shrinking phase
- strict 2PL: hold X locks until commit

Organizer PYQs:
- 2PL — L3003-L3008, L3043-L3075, L3638-L3650
- Locking vs timestamp — L3210-L3257, L3435-L3437

Recent MAKAUT papers:
- 2025: 2PL phases
- 2024: locking vs timestamp protocol
- 2023: timestamp vs locking, 2PL-based questions

### 4) Timestamp, MVCC, optimistic CC
Must know:
- timestamp protocols order transactions by age
- MVCC keeps multiple versions
- optimistic CC uses read/validate/write phases

Organizer PYQs:
- Timestamp / locking comparisons — L3214-L3257, L3464-L3474
- Concurrency problems — L3437, L3570

Recent MAKAUT papers:
- 2024: locking vs timestamp

### 5) Recovery
Must know:
- log-based recovery
- immediate update: UNDO + REDO
- deferred update: REDO only
- WAL
- checkpoint
- ARIES basics if asked

Organizer PYQs:
- Log-based recovery / checkpoint — L3090-L3172, L3265-L3281, L3508-L3529, L3627-L3637

Recent MAKAUT papers:
- 2025: checkpoint definition
- 2024: recovery / trigger / types of failures short notes in long section
- 2023: checkpoint

### 6) Concurrency anomalies and deadlock
Must know:
- dirty read
- lost update
- unrepeatable read
- phantom
- deadlock prevention / detection / recovery

Organizer PYQs:
- Anomalies, deadlock, wait-die / wound-wait — L3015-L3021, L3286-L3300, L3401-L3419, L3664-L3726

Recent MAKAUT papers:
- 2025: dirty read
- 2024: different anomalies with examples; deadlock avoidance
- 2023: different concurrency problems; deadlock avoidance/protocols

---

## Unit 5 — Security

### 1) Authentication vs authorization
Must know:
- authentication = who are you?
- authorization = what can you access?
- access control enforces permissions

Organizer PYQs:
- Authentication / authorization — L3747-L3758

Recent MAKAUT papers:
- 2025: RBAC; MAC; security mechanisms
- 2024: SQL injection; DML/DDL/security MCQs

### 2) GRANT / REVOKE and views
Must know:
- GRANT gives privilege
- REVOKE removes privilege
- views can hide sensitive columns/rows

Organizer PYQs:
- GRANT / REVOKE — L124-L125, L3769-L3778

Recent MAKAUT papers:
- 2025: security mechanisms in DB
- 2024: view-based security via long questions

### 3) DAC, MAC, RBAC
Must know:
- DAC = owner-controlled
- MAC = label-controlled
- RBAC = role-controlled

Organizer PYQs:
- Security/control topics are scattered; MAC/RBAC are explicitly asked in modern MAKAUT papers

Recent MAKAUT papers:
- 2025: RBAC, MAC
- 2024: DAC/MAC

### 4) SQL injection and intrusion detection
Must know:
- SQL injection = malicious input changes query meaning
- prevent with prepared statements and validation
- intrusion detection = detect suspicious access/attack patterns

Recent MAKAUT papers:
- 2024: SQL injection MCQs

---

## Unit 6 — Advanced Topics

### 1) OODBMS
Must know:
- stores objects
- object identity, encapsulation, inheritance, methods
- good fit for OOP applications

Organizer PYQs:
- OODBMS advantages / short note — L3979-L4029

Recent MAKAUT papers:
- 2025: homogeneous vs heterogeneous DBMS; object-oriented ideas appear in advanced section
- 2023: DDBMS vs OODBMS

### 2) ORDBMS
Must know:
- relational DB + object features
- complex objects, classes, inheritance, dynamic binding, extensible types

Organizer PYQs:
- ORDBMS mandatory features — L3983-L3999

### 3) Logical databases
Must know:
- deductive database
- facts + rules + inference
- Datalog-style reasoning

Recent MAKAUT papers:
- syllabus-required, less direct organizer pressure

### 4) Web databases
Must know:
- database used through web apps
- JDBC / ODBC / CGI / PHP / ASP

Organizer PYQs:
- ODBC support / DSN / web access style material — L4125-L4143

### 5) DDBMS
Must know:
- data spread across multiple sites, managed as one logical DB
- fragmentation transparency
- location transparency
- replication transparency
- local mapping transparency

Organizer PYQs:
- Distributed database definition — L3810-L3819
- Centralized vs distributed advantages — L3821-L3850
- DDBMS vs OODBMS — L3851-L3881
- Transparency / fragmentation / allocation — L4088-L4116

Recent MAKAUT papers:
- 2025: fragmentation in distributed database
- 2023: vertical vs horizontal fragmentation; short notes on DDBMS

### 6) Data warehouse and data mining
Must know:
- warehouse = subject-oriented, integrated, time-variant, non-volatile
- mining = discover patterns from data

Organizer PYQs:
- Data warehouse definition / characteristics — L4144-L4156

Recent MAKAUT papers:
- 2025: replication / distributed data handling
- 2023: data warehouse appears in advanced section indirectly via DWDM subject overlap

---

## High-priority revision order
If time is short, revise in this order:
1. Unit 2 normalization + FDs + Armstrong + BCNF
2. Unit 4 ACID + 2PL + recovery + timestamps
3. Unit 1 ER model + keys + data independence
4. Unit 3 indexing + B-tree + B+tree + hashing
5. Unit 5 security
6. Unit 6 advanced topics

---

## Last 5 years MAKAUT paper snapshot I verified
Verified on public archives in this session:
- 2025 paper: ER attributes, indexing, 2PL, RBAC, DDBMS fragmentation, joins, ACID, dirty read, DBA, data abstraction, SQL queries
- 2024 paper: ER notation, relational algebra, SQL injection, granularity, DML, data dictionary, weak entity, ACID, locking vs timestamp, heuristic optimization, anomalies, B-tree, DAC/MAC, recovery, views, triggers
- 2023 paper: metadata, ALTER, TCL, ACID, isolation, anomalies, Armstrong axioms, FD, join dependency, lossless decomposition, B-tree/B+tree, data dictionary, 3NF/BCNF, hashing, fragmentation, DDBMS, web DB
- 2022 paper: metadata, ALTER-style SQL, TCL, ACID, functional dependency, join dependency, lossless and lossy decomposition, B-tree/B+tree, blocking factor, hashing, vertical vs horizontal fragmentation, DDBMS, web-based DBMS
- 2020-2021: I could not verify separate DBMS paper pages from a reliable public archive in this session

If you want, I can do one more pass and convert this into a 2-page ultra-cram sheet with only definitions, formulas, and MCQ traps.