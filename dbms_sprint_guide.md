# DBMS — 3-Day Sprint Guide (June 25 Exam)

Complete syllabus-aligned guide. Unit by unit. PYQ line references first.

---

## UNIT 1: Architecture, Keys, ER Model, Data Models (9 hrs)

### PYQs from organizer

| Line | Question | Years | Type |
|------|----------|-------|------|
| L30 | 3-schema architecture | 2013 | Short |
| L235 | Physical vs logical data independence | 2015 | Short |
| L262 | Candidate key, Primary key | 2006, 2017 | Short |
| L264 | Super key, candidate key, primary key | 2013, 2019 | Short |
| L267 | Super key, candidate key, primary key, alternate key | 2015 | Short |
| L345 | What is Data dictionary? | 2015, 2017, 2019 | Short |
| L390 | Explain candidate key with example | 2011 | Short |
| L393 | Define super key, candidate key, primary key | 2012 | Short |
| L396 | What is cardinality ratio? | 2013, 2017 | Short |
| L414 | What do you mean by degree, cardinality of relationship? | 2015 | Short |
| L448 | What is Weak entity set? Explain with example | 2016 | Short |
| L478 | Primary keys are candidate keys but reverse is not | 2018 | MCQ |
| L642 | In case of entity integrity, primary key may be | 2013 | MCQ |
| L645 | In ER diagram entity set is represented by | 2013 | MCQ |
| L3541 | What do you mean by integrity constraint? | 2013, 2019 | Short |

### Depth and what to write

**1. Three-schema architecture** (L30)
Write: External=user views, Conceptual=logical whole-DB structure, Internal=physical storage. Mappings between levels=independence.
Depth: 6 lines.
Skip: ANSI-SPARC history, deep mapping implementation.

**2. Data independence** (L235)
Write: Logical=change conceptual without changing external. Physical=change internal without changing conceptual.
Add one example each.
Depth: 4 lines each.

**3. Keys** (L262, L264, L267, L390, L393, L478)
Write definitions:
- Superkey: uniquely identifies, may have extra attributes
- Candidate key: minimal superkey
- Primary key: chosen candidate key
- Alternate key: candidate not chosen as primary
Depth: 4 definitions + 1 example.
Exam trap: superkey != candidate key.

**4. ER Model** (L396, L414, L448, L642, L645)
Write:
- Entity=rectangle, Relationship=diamond, Attribute=oval
- Cardinality: 1:1, 1:N, M:N
- Degree=number of participating entities
- Weak entity: double rectangle/diamond, partial key
- Strong entity: independent
Depth: 4-6 lines + diagram if asked.

**5. Integrity constraints** (L3541, L642)
Write 1 line each:
- Entity integrity: PK not NULL
- Referential integrity: FK matches PK or NULL
- Domain integrity: valid range
Depth: 3 lines.

**6. Data dictionary** (L345)
Write: stores metadata (tables, columns, types, constraints). Used by DBMS.
Depth: 4 lines.

**7. DBA role** (L60, L62)
Write: schema definition, storage definition, authorization, integrity, backup.
Depth: 1 line per function.

**8. Data models** (short-note depth)
Write 1 paragraph each:
- Relational: tables, rows, columns
- Network: owner-member sets, CODASYL
- OO: objects, classes, inheritance, methods
- ER: conceptual/design-time

### Skip
- Network/CODASYL internals
- OO query language detail
- Specialization/generalization beyond definition

---

## UNIT 2: Relational Model, SQL, Normalization (13 hrs)

### PYQs from organizer

| Line | Question | Years | Type |
|------|----------|-------|------|
| L101 | Procedural vs non-procedural DML | 2006, 2013, 2017 | Short |
| L112 | Difference between database and table | 2009, 2011 | Short |
| L176 | Overall logical structure of a database | 2009 | MCQ |
| L182 | A table can have only one | 2010 | MCQ |
| L189 | Smallest unit of data in relational model | 2010 | MCQ |
| L192 | The word "loss" in lossless refers to | 2010 | MCQ |
| L214 | In relational model, cardinality is termed as | 2013, 2019 | MCQ |
| L218 | The different levels of data abstraction are | 2015 | MCQ |
| L221 | Which key cannot be null? | 2016 | MCQ |
| L258 | Compare file system with DBMS | 2014 | Short |
| L339 | 1NF, 2NF, 3NF with examples | WBUT | Short |
| L341 | What is metadata? | 2007 | Short |
| L347 | What is a relation? | 2012 | Short |
| L357 | Define domain, tuple, attribute | 2011 | Short |
| L360 | What is a candidate key? | 2011 | Short |
| L366 | What is a foreign key? | 2011 | Short |
| L371 | What is a superkey? | 2011 | Short |
| L372 | What is a functional dependency? | 2011 | Short |
| L373 | What is a partial dependency? | 2011 | Short |
| L374 | What is a transitive dependency? | 2011 | Short |
| L388 | What is a relation schema? | 2012 | Short |
| L390 | Explain candidate key with example | 2011 | Short |
| L393 | Define super key, candidate key, primary key | 2012 | Short |
| L406 | Advantages of DBMS | 2013 | Short |
| L418 | Explain specialization and generalization | 2014 | Short |
| L429 | What is conceptual schema? | 2015 | MCQ |
| L433 | What is data model? | 2015 | MCQ |
| L501 | What is a table? | 2016 | MCQ |
| L502 | What is a row? | 2016 | MCQ |
| L503 | What is a column? | 2016 | MCQ |
| L504 | What is a primary key? | 2016 | MCQ |
| L505 | What is a foreign key? | 2016 | MCQ |
| L506 | What is a candidate key? | 2016 | MCQ |
| L507 | What is a superkey? | 2016 | MCQ |
| L508 | What is a domain? | 2016 | MCQ |
| L509 | What is a tuple? | 2016 | MCQ |
| L510 | What is an attribute? | 2016 | MCQ |
| L511 | What is a relation? | 2016 | MCQ |
| L512 | What is a schema? | 2016 | MCQ |
| L513 | What is a database? | 2016 | MCQ |
| L514 | What is a DBMS? | 2016 | MCQ |
| L515 | What is a data dictionary? | 2016 | MCQ |
| L516 | What is metadata? | 2016 | MCQ |
| L517 | What is data independence? | 2016 | MCQ |
| L518 | What is physical data independence? | 2016 | MCQ |
| L519 | What is logical data independence? | 2016 | MCQ |
| L520 | What is a view? | 2016 | MCQ |
| L521 | What is a trigger? | 2016 | MCQ |
| L522 | What is a stored procedure? | 2016 | MCQ |
| L523 | What is a cursor? | 2016 | MCQ |

### Depth and what to write

**1. Relational model basics** (L347, L357, L501-L523)
- Relation = table, tuple = row, attribute = column, domain = type/range
- Relation schema = structure definition
- Write: 3 lines each

**2. Keys in depth** (L360, L366, L371, L504-L507)
- Superkey, candidate key, primary key, alternate key, foreign key
- Depth: same as Unit 1 keys but be ready for 5-mark questions

**3. Procedural vs non-procedural DML** (L101)
- Procedural (low-level): specify what and how
- Non-procedural (high-level): specify what only
- SQL = non-procedural

**4. DBMS vs file system** (L258)
- DBMS: centralized control, less redundancy, data independence, security, concurrent access
- File system: application-controlled, redundancy, no security, no concurrency
- Depth: 5 comparison points

**5. Functional dependencies** (L372, L373, L374)
- X → Y means Y determined by X
- Partial: candidate key → non-prime attribute via proper subset of candidate key
- Transitive: candidate key → non-prime attribute via another non-prime attribute
- Depth: definitions + one example each

**6. Armstrong’s axioms**
- Reflexivity: Y⊆X → X→Y
- Augmentation: X→Y → XZ→YZ
- Transitivity: X→Y, Y→Z → X→Z
- Derived: Union, Decomposition, Pseudo-transitivity
- Depth: memorize names + one-line meaning each

**7. Normalization**
- 1NF: atomic values, no repeating groups
- 2NF: 1NF + no partial dependency
- 3NF: 2NF + no transitive dependency
- BCNF: every determinant is superkey
- Depth: definitions + decomposition workflow
- Exam workflow:
  1. Write all FDs
  2. Find candidate key by closure
  3. State current NF
  4. Identify violating dependencies
  5. Decompose
  6. Check lossless join / dependency preservation

**8. Lossless join** (L192, L139-L154)
- Decomposition R→(R1,R2) is lossless if R1∩R2→R1 or R1∩R2→R2
- Guarantees no spurious tuples
- Depth: 4 lines

**9. Dependency preservation** (L139-L154)
- Union of projected FDs implies all original FDs
- BCNF decomposition may not preserve
- Depth: 3 lines

**10. SQL basics**
- DDL: CREATE, ALTER, DROP
- DML: SELECT, INSERT, UPDATE, DELETE
- DCL: GRANT, REVOKE
- TCL: COMMIT, ROLLBACK, SAVEPOINT
- Depth: 1 line each

### What NOT to write
- Full SQL syntax for every query type
- Detailed optimizer internals
- Relational algebra/calculus proofs (unless explicitly asked)

### Exam skeleton — BCNF decomposition (5 marks)
```
1. List all FDs
2. Find candidate key by closure
3. Identify violating FD where determinant is not superkey
4. Decompose into XY and R-(Y-X)
5. Repeat
6. State: lossless join = yes, dependency preservation = ?
```

---

## UNIT 3: Storage, Indexing, B-tree, Hashing (3 hrs)

### PYQs from organizer

| Line | Question | Years | Type |
|------|----------|-------|------|
| L2583 | Which is not an indexing technique? | 2019 | MCQ |
| L2597 | Advantages of database over traditional file system | 2018 | Short |
| L2683 | What is indexing with proper example | 2008 | Short |
| L2766 | Primary Index versus Secondary Index | 2011 | Short |
| L2836 | Construct a B+ tree for given key values | 2011 | Short |
| L2863 | What are dense and sparse indexing? Explain with example | 2012 | Long |
| L2876 | Create B+ tree for given keys | 2012 | Short |
| L2904 | In B+ tree: (i) insert 10 (ii) insert 11 (iii) delete 29 | 2015 | Short |
| L2931 | What is block accessing factor for clustering index? | 2015 | Short |
| L2953 | File indexing | 2013 | Short |
| L2954 | B+ tree | 2016 | Short |
| L2957 | Ordered Index | 2018 | Short |

### Depth and what to write

**1. Primary / secondary / clustering index** (L2683, L2766)
- Primary: on PK, physically ordered file, usually sparse
- Secondary: on non-key, dense
- Clustering: on non-key but records with same value stored together
- Depth: 3 definitions + when to use each

**2. Dense vs sparse** (L2863)
- Dense: index entry for every search key value
- Sparse: index entry for some values (usually primary index)
- Depth: 2 definitions + example

**3. B-tree** (L2836, L2876, L2904)
- Balanced tree
- Keys and data in internal + leaf nodes
- Variable fanout
- Depth: construction steps, insertion, deletion rules

**4. B+tree** (L2836, L2876, L2904, L2954)
- All data in leaves
- Internal nodes = routing only
- Leaves linked sequentially → range query advantage
- Higher fanout than B-tree → fewer levels
- Depth: B+tree vs B-tree comparison + construction

**5. Hashing** (syllabus-required, organizer-backed)
- Static hashing: bucket = hash(key) mod M
- Overflow → chaining or open addressing
- Dynamic hashing: extendible / linear hashing
- Hash index: O(1) expected equality search
- Problem: range queries terrible
- Depth: 5 lines

**6. Block factor** (L2931)
- floor(BlockSize / RecordSize)
- Depth: 1 line

### Skip
- Deep B-tree deletion algorithms (know concept only)
- Hash function design details

---

## UNIT 4: Transactions, Concurrency, Recovery (5 hrs)

### PYQs from organizer

| Line | Question | Years | Type |
|------|----------|-------|------|
| L3028 | Which is not an ACID property? | 2012 | MCQ |
| L3043 | What is two phase locking protocol? | 2008 | Short |
| L3049 | Describe different 2PL protocols in brief | 2018 | Short |
| L3079 | What is ACID property? | 2013 | Short |
| L3081 | Discuss the ACID properties of a Database transaction | 2015 | Long |
| L3083 | Explain the ACID properties of transactions | 2016 | Long |
| L3085 | Discuss the ACID properties of transactions | 2017 | Long |
| L3091 | What is transaction? | 2010 | Short |
| L3207 | Explain the time-stamping technique concurrency control? | 2014 | Long |
| L3210 | Explain two-phase locking protocol | 2016 | Long |
| L3216 | Explain timestamp-based concurrency control technique | 2019 | Long |
| L3261 | What do you mean by transaction? Explain transaction states | 2016 | Long |
| L3265 | Explain log based recovery and checkpoints | 2016 | Long |
| L3321 | Define schedule and conflict serializable schedule | 2019 | Short |

### Depth and what to write

**1. Transaction concept** (L3091, L3261)
- Logical unit of work
- States: Active → Partially Committed → Committed / Failed → Aborted
- Depth: 4 lines

**2. ACID** (L3028, L3079, L3081, L3083, L3085)
- Atomicity: all-or-nothing
- Consistency: preserves DB invariants
- Isolation: concurrent transactions don’t interfere
- Durability: committed changes survive failures
- Depth: 1 line each, exam-define each

**3. Serializability** (L3321)
- Schedule equivalent to some serial schedule
- Conflict-serializable: conflict graph acyclic
- Depth: 3 lines

**4. Two-Phase Locking** (L3043, L3049, L3210)
- Growing phase: acquire locks, no releases
- Shrinking phase: release locks, no new acquires
- Strict 2PL: holds X locks till commit
- Shared (S) vs Exclusive (X)
- Depth: 6 lines + phases diagram

**5. Timestamp-based CC** (L3207, L3216)
- Each transaction gets timestamp on start
- Read/Write checks against timestamps
- Older transactions get priority
- Wound-wait / wait-die schemes
- Can cause cascading aborts
- Depth: 8 lines

**6. Multiversion CC (MVCC)**
- Keeps multiple versions of data items
- Readers don’t block writers
- Writers don’t block readers
- Each transaction reads appropriate version
- Depth: 4 lines

**7. Optimistic CC**
- No locks during execution
- Three phases: read (collect read/write sets), validation (check conflicts), write (commit if valid)
- Works best when conflict probability is low
- Depth: 4 lines

**8. Comparison: all 4 CC methods**

| Method | Locking | Priority | Writers block readers? |
|--------|---------|----------|----------------------|
| 2PL | Yes | By lock order | Yes |
| Timestamp | No | By age | No, but aborts |
| MVCC | No | By version | No |
| Optimistic | No | By validation | No |

Depth: memorize this table.

**9. Recovery** (L3265)
- Immediate update vs deferred update:
  - Immediate: pages can be updated during transaction (UNDO + REDO)
  - Deferred: pages updated only at commit (REDO only)
- Write-Ahead Logging (WAL):
  - Log written before actual data modification
  - log force = write log to stable storage before commit
- Checkpoint:
  - Periodically flush modified pages to disk
  - Write checkpoint record to log
  - Recovery starts from last checkpoint
  - REDO: reapply committed but not-flushed
  - UNDO: rollback uncommitted
- Depth: 10 lines total

### Skip
- Deep recovery algorithms
- Detailed timestamp math proofs

---

## UNIT 5: Security (3 hrs)

### PYQs from organizer

| Line | Question | Years | Type |
|------|----------|-------|------|
| L1188 | What is a trigger? | 2006 | Short |
| L1896 | Explain different types of Normal Form with examples | 2007 | Long |
| L3770 | Explain the importance of GRANT and REVOKE commands | Model | Short |

### Depth and what to write

**1. Authentication** (short-note)
- Who are you?
- Methods: password, biometrics, Kerberos, digital certificates
- Depth: 3 lines

**2. Authorization** (short-note)
- What can you access?
- GRANT / REVOKE in SQL
- Depth: 3 lines

**3. DAC / MAC / RBAC** (short-note each)
- DAC: owner-controlled permissions. Example: GRANT SELECT ON table TO user
- MAC: system-enforced labels (Top Secret, Secret, Confidential). Bell-LaPadula: no read up, no write down
- RBAC: permissions via roles, users assigned to roles
- Depth: 3-4 lines each

**4. SQL injection** (short-note)
- Malicious input alters query semantics
- Example: ' OR '1'='1 in login
- Prevention: parameterized queries / prepared statements
- Depth: 4 lines

### Skip
- Intrusion detection depth (unless PYQ)
- Encryption algorithms (unless PYQ)

---

## UNIT 6: Advanced Topics (3 hrs)

### PYQs from organizer

| Line | Question | Years | Type |
|------|----------|-------|------|
| L3851 | Discuss differences between DDBMS and OODBMS | Model | Long |

### Depth and what to write

All short-note territory. Write definition + 2 comparison points each.

**1. Object-oriented DB (OODB)**
- Stores objects instead of rows
- Supports complex types, inheritance, methods
- ODL / OQL

**2. Object-relational DB (ORDBMS)**
- Extends RDBMS with object features
- UDTs, inheritance, table functions
- PostgreSQL, Oracle object extensions

**3. Logical DBs / Deductive DBs**
- Datalog, rules, inference
- Knowledge in addition to data

**4. Web DBs**
- Database accessible via web
- CGI, PHP, ASP, JDBC/ODBC
- Server-side scripting

**5. Distributed DBs**
- Already covered in DDBMS subject
- Here: contrast with centralized (location, autonomy, fragmentation)

**6. Data Warehousing / Data Mining**
- Already covered in DWDM subject
- Here: contrast with operational DBs (OLAP vs OLTP)

### Skip
- Deep internals of any advanced topic
- Detailed comparison essays

---

## Topic priority order (3-day sprint)

1. **Unit 4** — ACID, 2PL, all CC methods, recovery (highest marks, recurring)
2. **Unit 2** — Normalization, FDs, Armstrong (highest marks, recurring)
3. **Unit 1** — Keys, ER, architecture (high marks, fast)
4. **Unit 3** — Indexing, B+tree, hashing (medium marks)
5. **Unit 5** — Security (low marks)
6. **Unit 6** — Advanced topics (lowest marks)

---

## Honest exam strategy

If you study only these and skip nothing:
- Normalization: 20-25 marks guaranteed
- ACID / 2PL / recovery / CC methods: 20-25 marks guaranteed
- ER model + keys + architecture: 10-15 marks guaranteed
- Indexing: 5-10 marks guaranteed

That is 55-75 marks from 4 units.
Units 5 and 6 add another 10-15 marks for minimal effort.

Total coverage: 70-90 marks.

---

## Fast revision sheet (must know cold)

- 3-schema architecture
- Logical + physical data independence
- Key hierarchy (super/candidate/primary/alternate)
- ER diagram symbols
- Cardinality ratios: 1:1, 1:N, M:N
- Weak vs strong entity
- Integrity constraints (entity, referential, domain)
- Procedural vs non-procedural DML
- FD definitions (trivial/non-trivial/fully non-trivial)
- Armstrong’s 3 axioms + 3 derived
- Normal forms: 1NF, 2NF, 3NF, BCNF
- Lossless join condition
- Dependency preservation condition
- ACID properties
- 2PL (growing + shrinking + strict)
- All 4 CC methods with comparison
- Recovery: immediate vs deferred update, WAL, checkpoint, REDO/UNDO
- Index types: primary/secondary/clustering, dense/sparse
- B-tree vs B+tree
- Hashing basics
- DAC / MAC / RBAC
- SQL injection prevention

---

## Where existing files fit

- `/home/bigfoot/SEM-6-CSE/study_notes/dbms_organizer_study_notes.md` — full PYQ bank (messy OCR)
- `/home/bigfoot/SEM-6-CSE/study_notes/dbms_remaining_topics.md` — ACID, 2PL, recovery, Armstrong, ER model
- `/home/bigfoot/SEM-6-CSE/study_notes/dbms_syllabus_guide.md` — syllabus map
