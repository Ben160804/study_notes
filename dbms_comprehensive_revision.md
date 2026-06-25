# DBMS Final Revision Guide — PCC-CS601
Syllabus-matched. Organizer-checked. Past paper cross-verified.

STANDING ORDERS
- Anything marked [APP] means it has to appear in exam exactly as application/diagram/numerical.
- If a topic is listed here, it is in the syllabus. If it is not listed, it is not in the syllabus.
- Depth is calibrated from organizer line references and verified 2022–2025 papers.

================================================================
UNIT 1 — Database Architecture, Keys, ER Model, Data Models,
         Integrity (9 hrs) (Syllabus Lines: Unit 1)
================================================================

TOPIC 1.1: Three-schema architecture
  Theory:
  - External level (user views / external schemas)
  - Conceptual level (logical structure, whole database)
  - Internal level (physical storage, indexes, files)
  - Mappings between levels
  Organizer refs: L30, L219
  Past paper:
  - 2024: database system structure
  - 2025: subsystems of a typical database system structure
  [APP] Draw and label the three-schema architecture.
  [APP] "How does data abstraction help in managing complexity?"

TOPIC 1.2: Data independence
  Theory:
  - Logical data independence: change conceptual → external unchanged
  - Physical data independence: change internal → conceptual unchanged
  Organizer refs: L235, L517-L519
  Past paper:
  - 2024: data dictionary; DBA role
  [APP] Give one concrete example of logical independence and one of physical independence.

TOPIC 1.3: Keys
  Theory:
  - Superkey, Candidate key, Primary key, Alternate key, Foreign key
  - Candidate = minimal superkey
  Organizer refs: L262, L264, L267, L390, L393, L478, L504-L507
  Past paper:
  - 2025: keys and commonly used keys in DBMS
  - 2023: primary key / foreign key style questions
  [APP] Given a relation with attributes, identify superkeys, candidate keys, primary key, alternate keys, foreign keys.

TOPIC 1.4: Data models
  Theory:
  - Relational model: tables, rows, columns, domains
  - Network model: owner-member, set based
  - Object-oriented model: objects, classes, inheritance, methods
  - ER model: conceptual design model
  Organizer refs: assorted L258, L406, L418, L863
  Past paper:
  - 2024: top-to-bottom relationship / hierarchical schema MCQ
  - 2025: homogeneous vs heterogeneous DBMS

TOPIC 1.5: ER Model
  Theory:
  - Entity, Entity set, Attribute, Relationship, Relationship set
  - Degree of relationship: binary, ternary, n-ary
  - Cardinality ratio: 1:1, 1:N, M:N
  - Weak entity set / Strong entity set
  - Multivalued attribute, Derived attribute, Composite attribute, Simple attribute
  - Specialization / Generalization
  Organizer refs:
    Weak/strong: L330, L448, L450-L459, L489
    Cardinality: L396, L940
    Degree: L414, L416
    Attributes: L460, L474
    Spec/gen: L229, L501, L581
  Past paper:
  - 2025: multivalued attribute; strong entity; generalization/specialization; ER extensions; degree of relationship
  - 2024: rectangles in ER diagram, weak entity, cardinality, E-R construction question
  - 2023: strong entity, weak entity, derived attribute
  [APP] Draw ER diagram for: Library Management, Examination, Student-Course, Online Shopping.
  [APP] Identify degree and cardinality for each relationship in a given diagram.
  [APP] Convert given ER diagram to relational schema (strong entity → table, weak entity → table + owner PK, 1:N → add FK to many side, M:N → junction table).

TOPIC 1.6: Integrity constraints
  Theory:
  - Entity integrity: PK cannot be NULL
  - Referential integrity: FK must reference existing PK or be NULL
  - Domain integrity: valid range/format
  - User-defined integrity: business rules
  Organizer refs: L3541, L642, L300, L725-L732
  Past paper:
  - 2024: referential integrity MCQ
  [APP] Given a relational schema with FKs, state which tuples can/cannot be inserted/deleted.

TOPIC 1.7: DBA
  Theory:
  - Schema definition, storage/access methods, authorization/GRANT/REVOKE,
    integrity constraints, security and backup, routine maintenance
  Organizer refs: L60, L62, L64, L66, L82-L100
  Past paper:
  - 2025: DBA security responsibilities
  - 2024: DBA role in data abstraction question
  - 2023: DBA functions

TOPIC 1.8: Metadata / Data dictionary
  Theory:
  - Metadata = information about data
  - Data dictionary / system catalog stores table names, column names, types, constraints, indexes
  Organizer refs: L9, L341, L345, L515, L616
  Past paper:
  - 2023: metadata; data dictionary
  - 2022: metadata; data dictionary

[CHIT 1.8 — 1/2 page]
- Metadata vs Data dictionary: metadata IS the data ABOUT data; data dictionary is the DBMS component that stores/ manages metadata.
- Data dictionary stores: table names, column names, data types, constraints, indexes, users, privileges.
- System catalog = same thing as data dictionary.

----------------------------------------------------------------
[CHIT 1 — MUST FOR EXAM] ER + Architecture Chit
----------------------------------------------------------------
3-schema architecture (draw once, never forget):
  External → External mappings → Conceptual → Conceptual/Internal mappings → Internal

Data independence:
  Logical = change conceptual schema without changing user views (external)
  Physical = change storage/internal without changing conceptual

Key hierarchy (strict nesting):
  Superkey ⊃ Candidate key ⊃ Primary key
  Alternate key = candidate key not chosen as primary
  Foreign key = PK of another table, can be NULL, must reference existing PK or be NULL

ER notation (rectangle/diamond/oval):
  Rectangle = Entity set
  Diamond = Relationship set
  Oval = Attribute
  Line = Connects attribute to entity/relationship

Weak entity notation:
  Double rectangle = weak entity
  Double diamond = identifying relationship

Degree vs Cardinality:
  Degree = number of entity sets participating in a relationship (binary=2, ternary=3)
  Cardinality = how many of one entity can be associated with another (1:1, 1:N, M:N)

Attribute types (draw example table):
  Simple: cannot divide (Name as single string)
  Composite: can divide (Name into First, Middle, Last)
  Multivalued: multiple values per entity (PhoneNumbers = {home, office, mobile})
  Derived: calculated from other attributes (Age from DOB, or Address from City/PIN)

Specialization vs Generalization:
  Specialization = bottom-up (entity → subclasses) [IS-A]
  Generalization = top-down (subclasses → entity) [IS-A]
  Both produce E-R hierarchy; difference is only design direction.

Integrity constraints (4 types, memorize):
  1. Entity integrity: PK ≠ NULL
  2. Referential integrity: FK = referenced PK OR NULL
  3. Domain integrity: valid range/format
  4. User-defined integrity: business rules (e.g., Salary > 0)

ER → Relational conversion rules (protocol):
  Strong entity → TABLE(PK=its key, all attributes)
  Weak entity → TABLE(PK=partial key + owner's PK as FK)
  1:N relationship → add FK to the "many" side table
  M:N relationship → NEW TABLE(FK1, FK2, [attributes], PK=FK1+FK2)
  Ternary+ → NEW TABLE(all FKs + attributes)
  Specialization → one table for supertype + one each for subtypes OR single table with subtype discriminator

================================================================
UNIT 2 — Relational Model, SQL, Normalization, Query Optim. (13 hrs)
================================================================

TOPIC 2.1: Relational algebra
  Theory:
  - Selection (σ), Projection (π), Union (∪), Set difference (-), Cartesian product (×), Rename (ρ)
  - Joins: theta join, equi-join, natural join
  Organizer refs: L635, L648, L746, L849
  Past paper:
  - 2025: joins in SQL; relational algebra + SQL on Student/Course/Instructor schema
  - 2024: fundamental relational algebra operation = Cartesian product
  - 2023: relational algebra queries; Cartesian product
  [APP] Given RA expressions, compute the result or simplify.
  [APP] Convert RA to SQL and vice versa.

TOPIC 2.2: Relational calculus
  Theory:
  - Tuple relational calculus: {t | P(t)} — non-procedural
  - Domain relational calculus: {<x1, x2, ...> | P(x1, x2, ...)}
  Organizer refs: L931 for tuple; domain scattered
  Past paper:
  - 2023: features of tuple relational calculus
  [APP] Write queries in tuple relational calculus for given requirements.

TOPIC 2.3: SQL
  Theory:
  - DDL: CREATE, ALTER, DROP, TRUNCATE
  - DML: SELECT, INSERT, UPDATE, DELETE
  - DCL: GRANT, REVOKE
  - TCL: COMMIT, ROLLBACK, SAVEPOINT
  - SQL3: UDTs, inheritance, arrays, multisets, references
  - Built-in functions: character functions (SUBSTRING, etc.)
  - JOINs supported by SQL
  Organizer refs: DDL/DML scattered; DELETE/TRUNCATE/DROP in multiple places
  Past paper:
  - 2025: differences between DROP, TRUNCATE, DELETE; JOINs supported by SQL
  - 2024: DML definition; SQL injection MCQ
  - 2023: ALTER column; DELETE/TRUNCATE/DROP; SQL character function; DML/TCL/metadata
  - 2022: ALTER-style SQL
  [APP] Write SQL queries for given requirements (joins, aggregate, subquery, group by).
  [APP] State the output or error for given SQL snippets.

TOPIC 2.4: Functional dependencies + Armstrong's axioms
  Theory:
  - FD: X → Y
  - Trivial / non-trivial / fully non-trivial FD
  - Attribute closure: X+
  - Armstrong axioms: reflexivity, augmentation, transitivity
  - Derived rules: union, decomposition, pseudo-transitivity
  Organizer refs: L1818, L1941, L1973 (Armstrong); L1531, L1603, L1682, L1702 (FD/closure)
  Past paper:
  - 2023: Armstrong's three axioms; functional dependency
  - 2022: functional dependency
  [APP] Compute closure X+ given F and X.
  [APP] Using Armstrong's axioms, prove inferred FDs.
  [APP] Find candidate keys using closure.

TOPIC 2.5: Normalization
  Theory:
  - 1NF: atomic values, no repeating groups
  - 2NF: no partial dependency on candidate key
  - 3NF: no transitive dependency on candidate key
  - BCNF: every determinant is a superkey (stricter than 3NF)
  - 4NF: no multivalued dependency
  - Dependency preservation
  - Lossless join decomposition
  - Update anomalies, insertion anomalies, deletion anomalies
  Organizer refs:
    Normalization/anomalies: L1513-L1560
    BCNF vs 3NF: L1576-L1605, L1691
    Lossless: L1649-L1667, L1706-L1721, L1922, L1962, L2023, L2039
    3NF decomposition: L2182-L2211
    Advantages: L1761
  Past paper:
  - 2024: heuristic optimization + anomalies
  - 2023: lossless and lossy decomposition; 3NF decomposition; 4NF MCQ; update anomalies
  - 2022: lossless and lossy decomposition
  [APP] Given R and F, check which NF it satisfies.
  [APP] Decompose R into 3NF or BCNF step-by-step.
  [APP] Given a decomposition into R1, R2, check lossless join (use common attribute → check if it is a key in either R1 or R2).
  [APP] Check if decomposition preserves dependencies.

TOPIC 2.6: Query processing / optimization
  Theory:
  - Why optimization is needed: same result, many execution paths
  - Heuristic optimization: cascade of selections, commute selection and projection, commute selection and Cartesian product, join ordering
  - Query execution plan
  - Cost-based choice
  Organizer refs: L687, L794, L812-L841
  Past paper:
  - 2024: heuristic based optimization
  - 2025: SQL query solving + joins, grouped counts
  [APP] Given an initial query tree, apply heuristic rules and redraw the optimized tree.

[CHIT 2 — MUST FOR EXAM] Normalization + SQL Chit
----------------------------------------------------------------
SQL command families (memorize one example each):
  DDL: CREATE TABLE, ALTER TABLE, DROP TABLE, TRUNCATE TABLE  (defines schema)
  DML: SELECT, INSERT, UPDATE, DELETE  (manipulates data)
  DCL: GRANT, REVOKE  (controls access)
  TCL: COMMIT, ROLLBACK, SAVEPOINT  (transaction boundaries)

Differences that come EVERY exam:
  DELETE vs TRUNCATE vs DROP:
    DELETE: removes rows, can have WHERE, logged row-by-row, can ROLLBACK, keeps structure
    TRUNCATE: removes ALL rows, no WHERE, faster, logged as page deallocation, DDL (cannot ROLLBACK in some DBs), keeps structure
    DROP: removes entire table structure + data, cannot recover
  KEY: DELETE = slow, selective, can undo. TRUNCATE = fast, all rows, hard undo. DROP = nuke.

Armstrong's axioms (write them verbatim):
  Reflexivity: Y ⊆ X ⇒ X → Y
  Augmentation: X → Y ⇒ XZ → YZ
  Transitivity: X → Y, Y → Z ⇒ X → Z
  Derived (not axioms but must know):
    Union: X → Y, X → Z ⇒ X → YZ
    Decomposition: X → YZ ⇒ X → Y and X → Z
    Pseudo-transitivity: X → Y, WY → Z ⇒ WX → Z

Normal forms (progression):
  1NF: atomic values only, no repeating groups
  2NF: 1NF + no partial dependency on candidate key (no non-prime attr depends on PART of CK)
  3NF: 2NF + no transitive dependency (no non-prime attr depends on another non-prime attr)
  BCNF: every determinant is a superkey (stricter than 3NF)
  4NF: no multivalued dependency (BCNF + no MVD)

Candidate key via closure (step-by-step protocol):
  Step 1: List all FDs.
  Step 2: For each attribute (or combo), find its closure using FDs.
  Step 3: If closure contains all attributes of R, it is a superkey.
  Step 4: Check minimality — remove one attr at a time; if closure still contains all attrs, it is not minimal; keep reducing until minimal = candidate key.
  Step 5: Alternate keys = other candidate keys. Primary key = chosen one.

BCNF decomposition protocol (bulletproof):
  Step 1: Check if every FD X → Y has X as a superkey.
  Step 2: If yes → already in BCNF.
  Step 3: If no → pick the violating FD X → Y. Decompose R into R1(X ∪ Y) and R2(X ∪ remaining attrs).
  Step 4: Recurse on each new relation.
  Step 5: Each step guarantees lossless join (because X is common and X → R1 holds).

3NF decomposition (if asked):
  Step 1: Find a canonical cover (minimal set of FDs).
  Step 2: For each FD X → Y, create relation (X ∪ Y).
  Step 3: If no relation contains a candidate key, create one extra relation with a candidate key.
  Step 4: Result is always in 3NF, preserves dependencies, but may not be in BCNF.

Lossless join test (quick):
  Decomposition R → (R1, R2) is lossless iff R1 ∩ R2 → R1 OR R1 ∩ R2 → R2.
  In practice: after decomposition, check if common attributes form a key in either R1 or R2.

Relational algebra operations:
  σ (selection): horizontal filter
  π (projection): vertical filter
  ρ (rename): rename relation
  ∪ (union): rows from either (no duplicates, compatible types)
  − (set difference): rows in first not in second
  × (Cartesian product): every row of A paired with every row of B
  ⋈ (join): Cartesian product + selection
    Theta join: general condition (θ = >, <, =, ≠)
    Equi join: θ is only equality (=)
    Natural join: equi join on same-named columns, removes duplicate

Tuple relational calculus:
  { t | P(t) } — t is a tuple variable, P is predicate
  Non-procedural: describes WHAT to retrieve, not HOW
  Safe expression: guaranteed finite result

Heuristic optimization (remember the transformations):
  1. Cascade of selections: σc1(σc2(E)) = σc1∧c2(E)
  2. Commute selection and projection: πL(σc(E)) = σc(πL(σc(E))) — project first then select (if c uses only L attrs)
  3. Commute selection and Cartesian product: before join if possible
  4. Commute projection and Cartesian product
  5. Join ordering: do most restrictive selections first
================================================================

TOPIC 3.1: File organization basics
  Theory:
  - Sequential file organization
  - Indexed sequential file organization
  - Direct / hashed file organization
  Organizer refs: covered in broader indexing blocks
  Past paper: organizer and paper references around indexing

TOPIC 3.2: Index types
  Theory:
  - Primary index: on primary key, physically ordered file
  - Secondary index: on non-key field, may be dense or sparse
  - Clustering index: on non-key field, records with same key stored together
  Organizer refs: L2657-L2681, L2777-L2781, L2958-L2959
  Past paper:
  - 2025: index where index table and database table have same records → dense index
  - 2024: indexing MCQs
  - 2023: B-tree / B+tree short notes
  [APP] Given a relation of N records, block size B, record size R, compute I/O cost for:
       - full table scan
       - dense index scan
       - sparse index scan

TOPIC 3.3: Dense vs sparse index
  Theory:
  - Dense: entry for every key
  - Sparse: entry for some keys only (e.g., primary index)
  Organizer refs: L2863-L2873, L2784-L2785
  Past paper: organizer references

TOPIC 3.4: Blocking factor
  Theory:
  - bfr = floor(B / R)
  - Number of records per block
  Organizer refs: L2682-L2693, L2928-L2946
  Past paper:
  - 2024: granularity MCQ
  - 2022: blocking factor in B-tree question
  [APP] Numericals: compute bfr, then compute number of blocks for a file, then I/O cost.

TOPIC 3.5: B-tree and B+tree
  Theory:
  - B-tree: balanced multiway tree, data in internal + leaf nodes
  - B+tree: data only in leaf nodes, internal nodes are routing only
  - B+tree leaf links → excellent for range queries
  - B+tree has higher fanout than B-tree
  - Order m: every node except root has at least ceil(m/2) children and at most m children
  Organizer refs: L2682-L2709, L2836-L2841, L2860-L2907, L2951-L2959
  Past paper:
  - 2025: sparse index, data structure questions, indexing topic cluster
  - 2024: B-tree insertion question
  - 2023: B-tree vs B+tree; insert in B-tree of order 4
  - 2022: blocking factor; B-tree vs B+tree
  [APP] Insert given keys into a B-tree of given order, show intermediate steps clearly.
  [APP] Insert given keys into a B+tree of given order, show intermediate steps.

TOPIC 3.6: Hashing
  Theory:
  - Static hashing: hash(key) mod M → bucket, fixed number of buckets
  - Bucket overflow / collision
  - Dynamic hashing: extendible hashing, linear hashing
  - Good for equality search, bad for range queries
  Organizer refs: L2822-L2835 (bucket overflow)
  Past paper:
  - 2023: different hashing techniques
  - 2022: hashing
  [APP] Given a hash function and M buckets, compute bucket addresses for keys.
  [APP] Explain bucket overflow handling.

[CHIT 3 — MUST FOR EXAM] Indexing + B-tree + Hashing Chit
----------------------------------------------------------------
Index types (quick diff):
  Primary index: on primary key; physically ordered file; can be sparse (entry for some keys)
  Secondary index: on non-key field; usually dense (entry for every key)
  Clustering index: on non-key field; records with same key value are stored together in same block

Dense vs Sparse:
  Dense index: one entry for every search key value in the data file
    → always exact match, but larger index file
  Sparse index: one entry for some search key values (e.g., every block's first record)
    → smaller index, but requires extra I/O to locate exact record
  Rule: primary index on ordered file = sparse by default
        secondary index on non-key field = dense by default

Blocking factor (bfr):
  bfr = floor(B / R)
  B = block size in bytes, R = record size in bytes
  Number of blocks needed = ceil(N / bfr), N = total records

I/O cost formulas (must know):
  Full table scan: ceil(N / bfr) block accesses
  Dense index scan: (number of index levels) + (number of data records) ≈ depth + N
  Sparse index scan: (number of index levels) + (number of index entries) ≈ depth + ceil(N / bfr)

B-tree rules (order m):
  Every node except root has at least ceil(m/2) children and at most m children
  Root has at least 2 children (unless tree is empty)
  All leaves are at same level
  Internal node structure: [P0 K1 P1 K2 P2 ... Kn Pn] where n children = n-1 keys
  Insertion: if node overflows, split at median, promote median to parent
  Deletion: if node underflows, borrow from sibling or merge

B+tree rules (order m):
  Internal node: [P0 K1 P1 K2 P2 ... Kn Pn] — keys are routing values only
  Leaf node: [ <K1, ptr1> <K2, ptr2> ... <Kn, ptrn> sibling_ptr ]
  All data is in leaves; internal nodes are routing only
  Leaves are linked together in a linked list
  Why preferred: higher fanout, stable search cost, excellent for range queries (follow leaf links)
  Insertion: if leaf overflows, split leaf and copy median up to parent internal node

B-tree vs B+tree (exam table):
  | B-tree | B+tree |
  | Data in internal nodes? | Yes | No (routing only) |
  | Data location | Internal + leaf | Leaf only |
  | Range query | Must traverse internal | Follow leaf links (faster) |
  | Search | May stop at internal | Always reaches leaf |
  | Fanout | Lower (keys take space in internals) | Higher (keys copy only, not data) |
  | Preferred for | Fewer records | Many records, range scans |

Hashing:
  Static hashing: bucket = hash(K) mod M
    - M fixed → bucket overflow if too many keys hash to same bucket
    - Overflow handled by chaining (linked list in bucket) or open addressing
    - Bad for range queries (no order)
    - Good for equality search: O(1) expected
  Dynamic hashing:
    - Extendible hashing: use prefix of hash; directory doubles when needed; bucket split without reorganizing whole file
    - Linear hashing: split one bucket at a time in round-robin fashion; no directory needed

================================================================
UNIT 4 — Transactions, Concurrency Control, Recovery (5 hrs)
================================================================

TOPIC 4.1: Transaction basics and ACID
  Theory:
  - Transaction = logical unit of work, all-or-nothing
  - Atomicity, Consistency, Isolation, Durability
  - Dirty read, Lost update, Non-repeatable read, Phantom read
  Organizer refs: L3077-L3085, L3335 onward, L4587
  Past paper:
  - 2025: ACID, dirty read
  - 2024: ACID
  - 2023: ACID, isolation, checkpoint
  - 2022: ACID
  [APP] Identify the anomaly in a given schedule (dirty read / lost update / non-repeatable read / phantom).

TOPIC 4.2: Serializability
  Theory:
  - Serial schedule: transactions execute one after another
  - Serializable schedule: equivalent to some serial schedule
  - Conflict-serializable: precedence graph acyclic
  - View-serializable: equivalent by read/write view
  - Conflict-serializable is stricter and easier to test
  Organizer refs: around L3435-L3450
  Past paper:
  - 2025: 2PL and schedule-related concept questions
  [APP] Given a schedule of operations on data items:
       (a) Check if it is conflict-serializable by drawing precedence graph.
       (b) Check if it is view-serializable (if asked).
       (c) List the equivalent serial order if acyclic.

TOPIC 4.3: Locking and 2PL
  Theory:
  - Shared lock (S): read, multiple allowed
  - Exclusive lock (X): write, exclusive
  - Two-phase locking (2PL):
      Growing phase: acquire locks, no releases
      Shrinking phase: release locks, no new acquires
  - Strict 2PL: hold exclusive locks until commit
  Organizer refs: L3003-L3008, L3043-L3075, L3638-L3650
  Past paper:
  - 2025: 2PL phases
  - 2024: locking vs timestamp protocol
  - 2023: timestamp vs locking, 2PL-based questions
  - 2022: ACID
  [APP] Given a lock schedule, identify growing phase and shrinking phase.
  [APP] Explain why strict 2PL is preferred in practice.

TOPIC 4.4: Timestamp, MVCC, Optimistic CC
  Theory:
  - Timestamp protocol: each transaction gets timestamp on start; read/write checks against timestamps; older gets priority
  - MVCC: multiple versions kept; readers don't block writers; writers don't block readers
  - Optimistic CC: read phase, validation phase, write phase
  - Wound-wait / wait-die
  Organizer refs: L3210-L3257, L3435-L3437, L3214-L3257, L3464-L3474
  Past paper:
  - 2024: locking vs timestamp
  - 2023: timestamp vs locking
  [APP] Compare 2PL, Timestamp, MVCC, Optimistic in a table.

TOPIC 4.5: Recovery
  Theory:
  - Log-based recovery
  - Immediate update: pages updated during transaction → UNDO + REDO needed
  - Deferred update: pages updated only at commit → REDO only
  - Write-Ahead Logging (WAL): log written before data modification
  - Checkpoint: periodically flush modified pages to disk, write checkpoint record; recovery starts from last checkpoint
  - ARIES: Analysis, Redo, Undo phases
  Organizer refs: L3090-L3172, L3265-L3281, L3508-L3529, L3627-L3637
  Past paper:
  - 2025: checkpoint definition
  - 2024: recovery / trigger / types of failures short notes
  - 2023: checkpoint
  - 2022: ACID
  [APP] Given a log sequence with <Tn, start>, <Tn, X, old, new>, <Tn, commit>:
       (a) Show which transactions need REDO, which need UNDO after crash.
       (b) Show effect of checkpoint on the above.

TOPIC 4.6: Concurrency anomalies and deadlock
  Theory:
  - Dirty read, Lost update, Non-repeatable read, Phantom read, Write skew
  - Deadlock: prevention, detection, recovery
  - Wait-die / wound-wait
  Organizer refs: L3015-L3021, L3286-L3300, L3401-L3419, L3664-L3726
  Past paper:
  - 2025: dirty read
  - 2024: different anomalies with examples; deadlock avoidance
  - 2023: different concurrency problems; deadlock avoidance/protocols
  [APP] Identify which anomaly is shown in a given execution schedule.
  [APP] Draw wait-for graph and detect deadlock.

================================================================
UNIT 5 — Security (3 hrs)
================================================================

TOPIC 5.1: Authentication vs authorization
  Theory:
  - Authentication: who are you? (passwords, biometrics, Kerberos, certificates)
  - Authorization: what can you access?
  - Access control enforces permissions
  Organizer refs: L3747-L3758
  Past paper:
  - 2025: RBAC; MAC; security mechanisms
  - 2024: SQL injection; DML/DDL/security MCQs

TOPIC 5.2: GRANT / REVOKE and views
  Theory:
  - GRANT gives privilege
  - REVOKE removes privilege
  - Views hide sensitive columns/rows
  Organizer refs: L124-L125, L3769-L3778
  Past paper:
  - 2024: view-based security via long questions
  [APP] Write GRANT and REVOKE statements for given privileges.
  [APP] Create a view that restricts access to specific columns/rows.

TOPIC 5.3: DAC, MAC, RBAC
  Theory:
  - DAC: owner-controlled; GRANT/REVOKE
  - MAC: label-controlled; Bell-LaPadula (no read up, no write down)
  - RBAC: role-controlled; permissions to roles, users to roles
  Organizer refs: scattered; MAC/RBAC explicitly asked in modern papers
  Past paper:
  - 2025: RBAC, MAC
  - 2024: DAC/MAC

TOPIC 5.4: SQL injection and intrusion detection
  Theory:
  - SQL injection: malicious input changes query meaning
  - Prevention: prepared statements, input validation
  - Intrusion detection: detect suspicious access patterns
  Past paper:
  - 2024: SQL injection MCQs
  [APP] Given a vulnerable query, show the injection payload.
  [APP] Convert vulnerable query to prepared statement form.

================================================================
UNIT 6 — Advanced Topics (3 hrs)
================================================================

TOPIC 6.1: OODBMS
  Theory:
  - Stores objects instead of rows
  - Object identity, encapsulation, inheritance, methods
  - ODL / OQL
  - Good for OOP applications, complex data
  Organizer refs: L3979-L4029
  Past paper:
  - 2025: homogeneous vs heterogeneous DBMS
  - 2023: DDBMS vs OODBMS

TOPIC 6.2: ORDBMS
  Theory:
  - Relational DB + object features
  - Complex objects, classes, inheritance, dynamic binding, extensible types
  Organizer refs: L3983-L3999
  Past paper: short notes / comparison questions

TOPIC 6.3: Logical databases
  Theory:
  - Deductive database: facts + rules + inference
  - Datalog-style reasoning
  Past paper: syllabus-required, less direct pressure

TOPIC 6.4: Web databases
  Theory:
  - Database used through web apps
  - JDBC / ODBC / CGI / PHP / ASP
  - Server-side scripting
  Organizer refs: L4125-L4143 (ODBC support / DSN / web access)
  Past paper:
  - 2023: web DB questions
  - 2022: web-based DBMS

TOPIC 6.5: DDBMS
  Theory:
  - Data spread across multiple sites, managed as one logical DB
  - Fragmentation: horizontal, vertical, mixed
  - Transparency types:
      Fragmentation transparency
      Location transparency
      Replication transparency
      Local mapping transparency
  - Centralized vs Distributed advantages
  Organizer refs:
    Definition: L3810-L3819
    Centralized vs distributed: L3821-L3850
    DDBMS vs OODBMS: L3851-L3881
    Transparency / fragmentation / allocation: L4088-L4116
  Past paper:
  - 2025: fragmentation in distributed database
  - 2023: vertical vs horizontal fragmentation; short notes on DDBMS
  - 2022: vertical vs horizontal fragmentation; DDBMS
  [APP] Given a scenario, draw horizontal/vertical/mixed fragmentation.
  [APP] Identify which transparency is being described.

TOPIC 6.6: Data warehouse and data mining
  Theory:
  - Warehouse: subject-oriented, integrated, time-variant, non-volatile
  - Mining: discover patterns from data
  - Contrast with OLTP
  Organizer refs: L4144-L4156
  Past paper:
  - 2025: replication / distributed data handling
  - 2023: data warehouse in advanced section

[CHIT 6 — MUST FOR EXAM] Distributed + Advanced Chit
----------------------------------------------------------------
DDBMS transparency types (memorize all 4, exam loves MCQs):
  1. Fragmentation transparency: user sees a single logical table, not fragments
  2. Location transparency: user does not need to know where data physically resides
  3. Replication transparency: user does not know how many copies exist
  4. Local mapping transparency: user does not need to know which local DBMS is used

Horizontal vs Vertical vs Mixed fragmentation:
  Horizontal: distribute rows across sites (e.g., Indian customers in India node, US customers in US node)
    → improves availability and locality of access
  Vertical: distribute columns across sites (e.g., employee personal info on one node, salary on another)
    → improves security; need a JOIN to reconstruct full tuple
  Mixed: both horizontal and vertical (most real-world)

OODBMS vs ORDBMS (easy to confuse, memorize this):
  OODBMS: pure object database; data = objects only; no tables; ODL/OQL; complex objects but no SQL
  ORDBMS: RDBMS + object extensions; supports tables PLUS user-defined types, inheritance, references; SQL with objects
  Exam answer: ORDBMS = relational model extended with object features. OODBMS = object model only, no tables.

DDBMS vs Centralized (comparison):
  Centralized: single DB, single site; easy to manage; single point of failure; slower for remote users
  Distributed: multiple sites; better availability; fault tolerance; data may be fragment/replicated; complex to coordinate

Data warehouse characteristics (mnemonic SINTI):
  S — Subject-oriented (organized around subjects like customer/product, not applications)
  I — Integrated (consistent naming, formats, encoding across sources)
  N — Non-volatile (data is not updated/deleted in real time; only loaded and queried)
  T — Time-variant (data persists with time stamp; historical data kept for trend analysis)
  I — (add) Integrated + separate from operational DB

Data mining:
  Discover patterns/knowledge from large data sets
  Techniques: classification, clustering, association rules, regression, anomaly detection

Web DB:
  Database accessed through web apps
  Components: browser → web server → application server → DBMS
  Connectors: JDBC (Java), ODBC (C/other), PHP, ASP, CGI

Logical DBs (deductive):
  Facts + rules + inference
  Datalog: declarative logic language (Prolog-like)
  Example: parent(X,Y), parent(Y,Z) → grandparent(X,Z)

================================================================
UNIT 5 — Security (3 hrs)

Unit 1:
  [x] ER diagram construction (at least 3 scenarios practiced)
  [x] ER → relational schema conversion (weak entity, M:N relationship)
  [x] Cardinality ratio identification

Unit 2:
  [x] RA expression evaluation
  [x] Tuple relational calculus query writing
  [x] Attribute closure computation
  [x] Candidate key finding using closure
  [x] Armstrong's axioms proof
  [x] Normal form check (given R and F)
  [x] 3NF / BCNF decomposition step-by-step
  [x] Lossless join test (common attribute key check)
  [x] Dependency preservation check
  [x] Query tree heuristic optimization

Unit 3:
  [x] Blocking factor calculation: bfr = floor(B / R)
  [x] I/O cost: full scan, dense index, sparse index
  [x] B-tree insertion (given order, given keys)
  [x] B+tree insertion (given order, given keys)
  [x] Hash function address computation
  [x] Bucket overflow handling

Unit 4:
  [x] Precedence graph construction from schedule
  [x] View-serializability check (if asked)
  [x] 2PL phase identification from lock schedule
  [x] Anomaly identification from schedule (dirty read, etc.)
  [x] Log-based recovery: REDO/UNDO set after crash
  [x] Checkpoint recovery problem
  [x] Wait-for graph deadlock detection

Unit 5:
  [x] GRANT/REVOKE syntax writing
  [x] View creation for security
  [x] SQL injection payload construction
  [x] Prepared statement conversion

Unit 6:
  [x] Fragmentation diagram drawing (horizontal / vertical)
  [x] Transparency type identification

[CHIT 4 — MUST FOR EXAM] Transaction + Concurrency + Recovery Chit
----------------------------------------------------------------
ACID (one-word cheat):
  A — Atomicity (all-or-nothing)
  C — Consistency (preserves integrity constraints)
  I — Isolation (concurrent txns don't interfere)
  D — Durability (committed changes survive crash)

Anomalies (4 main ones, draw schedule for each):
  Dirty read: T1 reads uncommitted data written by T2; if T2 rolls back, T1 has bad data
  Lost update: T1 and T2 both update same data; last write wins; first update lost
  Non-repeatable read: T1 reads same row twice; T2 updates/deletes row in between; T1 gets different values
  Phantom read: T1 reads set of rows matching condition; T2 inserts/deletes rows matching condition; T1's second read sees new/ghost rows

2PL protocol (bulletproof):
  Growing phase: transaction acquires locks as needed; NO releases
  Shrinking phase: transaction releases locks; NO new acquisitions
  Result: guarantees conflict-serializability
  Strict 2PL: holds ALL exclusive locks until COMMIT → automatically prevents dirty reads and makes recovery easier

Precedence graph protocol (step-by-step):
  Step 1: List all conflicting operations in the schedule (same data item, at least one is write)
  Step 2: For each conflict: if T1's op comes before T2's op on same item, draw edge T1 → T2
  Step 3: Draw graph with nodes = transactions, edges = precedence
  Step 4: If graph has NO cycle → conflict-serializable; else NOT
  Step 5: If acyclic, topological sort gives equivalent serial order

Timestamp protocol:
  Each T gets a timestamp TS on start (TS(T1) < TS(T2) means T1 is older)
  Read/Write checks: if write is too late (Thomas Write Rule), abort
  Older transactions get priority; younger ones may be rolled back and restarted with new TS
  Wound-wait: older transaction wounds (aborts) younger if conflict → younger waits
  Wait-die: younger transaction waits; older never waits

Recovery log protocol (given a log, answer REDO/UNDO):
  After crash: all transactions with <commit> in log BEFORE crash → must REDO
  All transactions with <start> but NO <commit> in log before crash → must UNDO
  Checkpoint effect: only transactions active AT checkpoint time need full scan; committed after last checkpoint may still need REDO if not on disk

WAL rule: before any data page is written to disk, the corresponding log record MUST be on stable storage

Deferred vs Immediate update:
  Deferred: database update happens only at commit; log has enough info to REDO; no UNDO needed
  Immediate: updates happen during execution; both UNDO (old values) and REDO (new values) needed in log

CPROTOCOL for recovery problem:
  Step 1: Identify active transactions at crash time
  Step 2: Mark which had committed (needs REDO), which had not (needs UNDO)
  Step 3: If checkpoint given, note the restart point
  Step 4: REDO all committed transactions from last checkpoint (idempotent)
  Step 5: UNDO all uncommitted transactions (use old values in log)

[CHIT 5 — MUST FOR EXAM] Security Chit
----------------------------------------------------------------
Authentication vs Authorization:
  Authentication = identity verification (who are you?) → password, biometric, Kerberos, certificate
  Authorization = permission check (what can you do?) → after authentication

DAC vs MAC vs RBAC (exam table):
  | DAC | MAC | RBAC |
  |----|-----|------|
  | Owner sets permissions | System labels enforce | Roles have permissions |
  | Flexible, hard to audit centrally | Secure, rigid, military | Scalable, enterprise |
  | GRANT/REVOKE | Bell-LaPadula | Users → Roles → Perms |
  | Example: file owner shares file with coworker | Example: Top Secret cannot read Unclassified | Example: 'Clerk' role has SELECT only |

Bell-LaPadula (MAC rules):
  No read up: subject cannot read object at higher security level
  No write down: subject cannot write to object at lower security level

GRANT / REVOKE syntax (memorize):
  GRANT SELECT, INSERT ON TABLE Student TO User1 WITH GRANT OPTION;
  REVOKE INSERT ON TABLE Student FROM User1;

View-based security:
  CREATE VIEW StudentPublic AS SELECT Id, Name FROM Student;  -- hides Grade/Salary
  GRANT SELECT ON StudentPublic TO User1;
  User1 can query view but cannot see hidden columns directly

SQL injection quick rules:
  Pattern: input contains ' OR '1'='1, DROP TABLE, ; --
  Prevention: ALWAYS use prepared statements / parameterized queries
  Never concatenate user input directly into SQL strings

  Vulnerable: `"SELECT * FROM users WHERE name = '" + input + "'"`
  Safe: `cursor.execute("SELECT * FROM users WHERE name = ?", (input,))`

================================================================
NUMERICAL / APPLICATION CHECKLIST

Unit 2:
  [x] RA expression evaluation
  [x] Tuple relational calculus query writing
  [x] Attribute closure computation
  [x] Candidate key finding using closure
  [x] Armstrong's axioms proof
  [x] Normal form check (given R and F)
  [x] 3NF / BCNF decomposition step-by-step
  [x] Lossless join test (common attribute key check)
  [x] Dependency preservation check
  [x] Query tree heuristic optimization

Unit 3:
  [x] Blocking factor calculation: bfr = floor(B / R)
  [x] I/O cost: full scan, dense index, sparse index
  [x] B-tree insertion (given order, given keys)
  [x] B+tree insertion (given order, given keys)
  [x] Hash function address computation
  [x] Bucket overflow handling

Unit 4:
  [x] Precedence graph construction from schedule
  [x] View-serializability check (if asked)
  [x] 2PL phase identification from lock schedule
  [x] Anomaly identification from schedule (dirty read, etc.)
  [x] Log-based recovery: REDO/UNDO set after crash
  [x] Checkpoint recovery problem
  [x] Wait-for graph deadlock detection

Unit 5:
  [x] GRANT/REVOKE syntax writing
  [x] View creation for security
  [x] SQL injection payload construction
  [x] Prepared statement conversion

Unit 6:
  [x] Fragmentation diagram drawing (horizontal / vertical)
  [x] Transparency type identification

================================================================
SYLLABUS COMPLETION CHECKLIST
================================================================

Unit 1:
  [x] Three-schema architecture
  [x] Data abstraction / independence
  [x] DBA
  [x] Keys (super, candidate, primary, alternate, foreign)
  [x] Data models (relational, network, OO, ER)
  [x] ER model (entity, attribute, relationship, degree, cardinality, weak entity, specialization/generalization)
  [x] Integrity constraints (entity, referential, domain, user-defined)
  [x] Metadata / data dictionary

Unit 2:
  [x] Relational algebra (selection, projection, union, difference, Cartesian product, rename, joins)
  [x] Tuple relational calculus
  [x] Domain relational calculus
  [x] SQL3 (UDTs, inheritance, arrays, multisets, references)
  [x] DDL / DML / DCL / TCL
  [x] DBMS products (MySQL, Oracle, DB2, SQL Server)
  [x] Functional dependencies (trivial, non-trivial, fully non-trivial)
  [x] Armstrong's axioms (reflexivity, augmentation, transitivity + derived)
  [x] Attribute closure
  [x] Candidate key finding
  [x] Normalization (1NF, 2NF, 3NF, BCNF, 4NF)
  [x] Lossless join
  [x] Dependency preservation
  [x] Query optimization / heuristic optimization

Unit 3:
  [x] File organizations (sequential, indexed sequential, direct/hashed)
  [x] Index types (primary, secondary, clustering)
  [x] Dense vs sparse index
  [x] Blocking factor
  [x] B-tree
  [x] B+tree
  [x] B-tree vs B+tree
  [x] Hashing (static, dynamic, extendible, linear)
  [x] Bucket overflow

Unit 4:
  [x] Transaction basics
  [x] ACID properties
  [x] Serializability (serial, serializable, conflict-serializable, view-serializable)
  [x] Precedence graph
  [x] Locking (S, X)
  [x] Two-phase locking (2PL, strict 2PL)
  [x] Timestamp-based concurrency control
  [x] MVCC
  [x] Optimistic concurrency control
  [x] Recovery (log-based, immediate/deferred, WAL, checkpoint, ARIES)
  [x] Concurrency anomalies (dirty read, lost update, non-repeatable read, phantom)
  [x] Deadlock (prevention, detection, recovery, wait-die, wound-wait)

Unit 5:
  [x] Authentication
  [x] Authorization
  [x] DAC (GRANT / REVOKE)
  [x] MAC (Bell-LaPadula, no read up, no write down)
  [x] RBAC
  [x] Views for security
  [x] SQL injection
  [x] Intrusion detection

Unit 6:
  [x] OODBMS (object identity, encapsulation, inheritance, methods, ODL/OQL)
  [x] ORDBMS (complex types, extensibility, inheritance)
  [x] Logical DBs / Deductive DBs (Datalog, rules, inference)
  [x] Web DBs (JDBC/ODBC, CGI, PHP, ASP, server-side scripting)
  [x] DDBMS (fragmentation, allocation, replication, all transparency types)
  [x] Data warehouse (4 characteristics, vs OLTP)
  [x] Data mining (pattern discovery)

================================================================
HIGH-YIELD APPLICATION TOPICS (do NOT skip practice)
================================================================
  - ER diagram construction + relational schema conversion (every paper)
  - Candidate key finding via attribute closure (every paper)
  - BCNF/3NF decomposition + lossless join check (every paper)
  - Precedence graph + conflict-serializability check (every paper)
  - B-tree / B+tree insertion steps (every paper)
  - Recovery: REDO/UNDO / checkpoint problem (every paper)
  - GRANT/REVOKE syntax + view-based security (every 2-3 papers)
  - I/O cost with blocking factor (1-2 papers guaranteed)
  - Query tree heuristic optimization (intermittent but high weight)
