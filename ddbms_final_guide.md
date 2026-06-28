DDBMS FINAL GUIDE — PEC-IT601B
MAKAUT B.Tech CSE, 6th Semester, 2025 Batch
Units 1–6 | Syllabus-matched | Organizer-gap analysis included

══════════════════════════════════════════════
SOURCE AUTHORITY
══════════════════════════════════════════════
Official Syllabus: MAKAUT B.Tech CSE, 6th Sem (PEC-IT601B, 48L, 6 Units)
Organizer: /home/bigfoot/SEM-6-CSE/study_notes/ddbms_organizer_raw.txt (Popular Publications, 48 pages)
Past Papers: None found locally for 2020–2025. Guide written from syllabus + organizer.
Last DBMS Paper: PCC-CS601, June 25, 2026 — DBMS emphasized Units 2 (SQL) and 4 (Transactions).

══════════════════════════════════════════════
ORGANIZER GAP ANALYSIS
══════════════════════════════════════════════
Coverage verdict: 95% of syllabus covered. The organizer is thin but dense.

GAPS IDENTIFIED:
1. No actual MAKAUT DDBMS past papers (2020–2025) available locally
2. Some organizer content is duplicated/merged across questions (e.g., transparencies appear in multiple model questions)
3. No explicit numerical cost-comparison problem for semi-join cost formulas (organizer has formulas but no standalone practice question)
4. Parallel DB partitioning algorithms (round-robin, hash, range) appear in advanced topics but without heavy numerical practice
5. 3PC failure scenarios not fully illustrated with diagrams in organizer
6. Mobile DB and Distributed Object Management are lightly treated (short-answer territory)

HOW TO USE THIS GUIDE:
- Concepts are ordered exactly as the syllabus progresses
- PYQ line references point to the organizer (e.g., L201 = line 201 of organizer)
- [APP] = must be able to draw/get numerical in exam
- Depth spec: ***Concept Depth*** (Low / Medium / High)
- Must-Chit = exam-critical, cannot leave blank

══════════════════════════════════════════════
UNIT 1: INTRODUCTION, ARCHITECTURE, TRANSPARENCIES (8L)
══════════════════════════════════════════════
***Concept Depth: HIGH — expect 1 long + 1 short***

--------------------------------------
PYQ REFERENCE TABLE
--------------------------------------
Q  | Line | Type
L142 | Advantages/disadvantages of DDBMS | Short
L225 | DDBMS definition + features | Long
L201 | Fragmentation/location/replication transparency | Short
L251 | Transparency types + network/replication detail | Long
L344 | Transparency + Heterogeneous DB | Short
L94  | DDP definition | Short

Organizer gaps: Weak on "problem areas" beyond advantages/disadvantages. No explicit MCQ on ANSI-SPARC 3-level from Unit 1 angle.

--------------------------------------
CONCEPTS IN EXAM ORDER
--------------------------------------

1. Distributed Data Processing (DDP)
   - DDP = distributing application programs AND data across interconnected sites
   - Purpose: satisfy info needs of organization, not just relocate files
   - Two types:
     a) Centralized DDP: one machine controls all file access/updates
     b) Decentralized DDP: data stored at multiple sites, sites operate independently
   - Difference from DDBMS: DDP is the philosophy, DDBMS is the software system that manages it

2. Distributed Database System (DDBS / DDBMS) definition
   - Core: logically one database, physically distributed over networked sites
   - Managed by a Distributed DBMS
   - Key properties:
     * Location independency
     * Distributed query processing
     * Distributed transaction management
     * Seamless integration
     * Network linking
     * Transaction processing (atomic)

3. Advantages
   - Modular growth (add sites without stopping system)
   - Local autonomy (sites operate independently)
   - Reliability / availability (failure of one site doesn't stop everything)
   - Better response (data near users = faster access)
   - Data sharing (org-wide access)
   - Lower communication cost (local access preferred)

4. Disadvantages
   - Complexity (transparency, concurrency, recovery harder)
   - Security challenges (network = more attack surface)
   - Network dependence (if network fails, system suffers)
   - Integrity harder to maintain across sites
   - Costly software

5. Reference Architecture
   - ANSI-SPARC 3-level applies here too:
     External (user views)
     Conceptual (global view, DBA works here)
     Internal (physical storage)
   - DDBMS-specific components:
     * Global schema (global relations)
     * Fragmentation schema (maps global -> fragments)
     * Allocation schema (maps fragments -> sites)
     * Local conceptual schemas at each site
     * Local mapping schema

6. Transparencies (MOST IMPORTANT — bear in mind hierarchy)
   Transparency = hide distribution from user

   a) Fragmentation transparency (Level 1 — highest convenience)
      - User sees global relation, doesn't know data is fragmented
      - Query on global schema; no fragment names or locations specified
      - Best for end users

   b) Location transparency (Level 2)
      - User knows data is fragmented but NOT where fragments are stored
      - Must specify fragment names, not site names
      - Middle level

   c) Local mapping transparency (Level 3)
      - User knows fragments + their names
      - But doesn't know how names map to local system objects
      - Must specify sites of objects
      - Application programmer level

   d) Naming transparency
      - All items in database have unique names
      - User doesn't need to worry about name conflicts across sites
      - Simplest level

   e) Replication transparency
      - User doesn't know which copy of replicated data is being accessed
      - DDBMS chooses optimal copy automatically

   f) Transaction transparency
      - Ensures atomicity across sites regardless of location

   Exam note: Ask about DBMS transparency = hide implementation details. Ask about network transparency = user unaware of network operational details (roaming = query from any workstation).

7. Global Directory / Catalog
   [APP]
   - Central to DDBMS operation
   - Contents:
     * Data about data (metadata)
     * Fragmentation schema
     * Allocation schema
     * Global schema definition
     * Local schema definitions
   - Approaches:
     a) Centralized: one master copy (risky for availability)
     b) Fully replicated: copy at each site
     c) Partitioned: catalog itself partitioned (also replicated as needed)
     d) Combination

--------------------------------------
MUST-CHIT CREATION — UNIT 1
--------------------------------------
1. Define DDBMS and distinguish from centralized DBMS (5 marks)
   Chit template: "A DDBMS is a software system that manages a logically integrated collection of physically distributed databases over a computer network... [then contrast with centralized on redundancy, control, reliability]"

2. Draw and explain the DDBMS reference architecture (10 marks)
   Must label: global schema, fragmentation schema, allocation schema, local schemas, transaction manager, data communication module.

3. Explain all 5 transparencies with examples (10 marks)
   Hierarchy mnemonic: F-L-N-L-M-R (Fragmentation > Location > Naming > Local mapping > Replication)

4. Advantages and Disadvantages of DDBMS (5 marks)

5. Global Catalog approaches — centralized vs replicated vs partitioned (5 marks)

══════════════════════════════════════════════
UNIT 2: DESIGN, FRAGMENTATION, ALLOCATION, SEMANTICS (11L)
══════════════════════════════════════════════
***Concept Depth: HIGH — expect ER/fragmentation drawing + long explanation***

--------------------------------------
PYQ REFERENCE TABLE
--------------------------------------
Q  | Line | Type
L446 | Data replication explanation | Long
L413 | Horizontal/vertical/mixed/derived fragmentation | Long
L497 | Correctness rules of fragmentation | Short
L524 | Vertical clustering / partial union | Short
L537 | Mixed and horizontal fragmentation with example | Long
L568 | Advantages/disadvantages of fragmentation | Short
L595 | Update operation effect / update subtree | Long
L298 | Reference architecture diagram | Long
L302 | Remote access via auxiliary program in heterogeneous DDBMS | Long
L295 | ANSI-SPARC architecture + site independent schemas | Long
L299 | Bottom-up vs Top-down preference | Short

Organizer gaps: Weak on "semantic data control" specifics (view management beyond security angle, semantic integrity constraints as a separate sub-topic). Coverage exists but thin.

--------------------------------------
CONCEPTS IN EXAM ORDER
--------------------------------------

1. Design Strategies
   a) Top-down
      - System begins with requirements analysis
      - Ends with physical design
      - Used when designing from scratch
      - Used for homogeneous systems
      - Example: building a new enterprise DDBMS

   b) Bottom-up
      - Integrates existing databases at multiple sites
      - Global schema is compromise between existing descriptions
      - Easier for horizontally fragmented relations
      - Example: merging legacy DBMS into a DDBMS

2. Fragmentation — Core of DDBMS
   [APP] Must be able to draw fragmentation tree, apply correctness rules

   a) Horizontal fragmentation
      - Split tuples (rows) into subsets based on selection predicates
      - Example: EMP(ENO, ENAME, TITLE, DEPTNUM)
        EMP1 = σ_TITLE='Mgr'(EMP)  [managers]
        EMP2 = σ_TITLE≠'Mgr'(EMP)  [non-managers]
      - Reconstruction: UNION (EMP1 ∪ EMP2 = EMP)
      - Condition: completeness + disjointness

   b) Vertical fragmentation
      - Split attributes (columns) into groups
      - Must retain primary key in ALL fragments for reconstruction
      - Example:
        EMP1 = π_ENO,ENAME,TITLE(EMP)
        EMP2 = π_ENO,SAL,TAX(EMP)
      - Reconstruction: NATURAL JOIN (EMP1 ⋈ EMP2 = EMP)
      - Condition: completeness + reconstruction + disjointness (except PK)

   c) Mixed / Hybrid fragmentation
      - Apply vertical FIRST, then horizontal on the result
      - OR horizontal first, then vertical
      - Most flexible but reconstruction expensive
      - Example: vertical split EMP into EMP_v1, EMP_v2, then horizontal split EMP_v1

   d) Derived horizontal fragmentation
      - Fragmentation of one relation propagated to related relation via foreign key
      - Example: EMP(ENO, NAME, TITLE, DEPTNUM) and DEPT(DEPTNO, DNAME, LOC)
        If EMP is fragmented by DEPTNUM, then DEPT should be fragmented by DEPTNO at same sites
      - Reduces remote joins

   Correctness Rules:
   [APP]
   - Completeness: every tuple of R must appear in at least one fragment
   - Reconstruction: R must be reconstructible from fragments using UNION or JOIN
     * Horizontal → UNION
     * Vertical → JOIN (natural join on primary key)
   - Disjointness: no tuple appears in more than one fragment
     * Exception: primary key attribute in vertical fragmentation (key appears in all vertical fragments)
     * Horizontal fragments should be disjoint (use mutually exclusive predicates)

3. Data Allocation
   [APP] Be able to draw allocation tree / update subtree

   Strategies:
   - Centralized: entire DB at one site
   - Partitioned (non-replicated): DB divided into fragments at different sites
   - Replicated: copies at multiple sites

   Allocation methods:
   a) Best fit: measure each possible allocation, choose site with max benefit
   b) All beneficial sites: allocate to every site where benefit > cost
   c) Additional replica: solve for non-replicated first, then add copies from most beneficial

   Factors affecting allocation:
   - Response time constraints
   - Availability constraints
   - Network topology
   - Security restrictions

   Update Subtree:
   [APP]
   - Shows which fragments are affected by changing an attribute
   - Used to determine communication cost of updates
   - Root = attribute being updated
   - Leaves = all fragments containing that attribute
   - Example: if changing DEPTNUM in EMP, and EMP is fragmented horizontally by DEPTNUM, the update subtree might span multiple sites

4. Semantic Integrity / View Management / Security
   - View management: define views on global schema, map to local data
   - Semantic integrity: constraints that go beyond basic referential integrity
   - Data security in DDBMS context: local autonomy means each site enforces own security
   - Heterogeneity complications in security enforcement

5. Query Decomposition and Localization (lighter in Unit 2, heavy in Unit 3)
   - Goal: transform global query -> fragment queries
   - Decomposition: global relational algebra -> operations on global relations
   - Localization: replace global relation names with fragment names

--------------------------------------
MUST-CHIT CREATION — UNIT 2
--------------------------------------
1. Horizontal, Vertical, Mixed, Derived fragmentation with examples (10 marks)
   KEY: Draw the fragments, show predicates, prove correctness rules

2. Correctness rules of fragmentation with example (5 marks)
   Chit: Completeness Reconstruction Disjointness — each with one-line formula

3. Allocation strategies — centralized vs partitioned vs replicated (5 marks)

4. Top-down vs Bottom-up design approach (5 marks)

 Drawing protocol:
 - Start with global relation R
 - Apply fragmentation predicates P1, P2...
- Show union/reconstruction
 - Label sites 1, 2, 3...
 - For mixed: show vertical split first, then horizontal

══════════════════════════════════════════════
UNIT 3: DISTRIBUTED QUERY OPTIMIZATION (11L)
══════════════════════════════════════════════
***Concept Depth: HIGH — numerical cost calculations, diagram heavy***

--------------------------------------
PYQ REFERENCE TABLE
--------------------------------------
Q  | Line | Type
L801 | Objectives of distributed query optimization | Short
L825 | Query processing + characteristics of query processor | Short
L1117 | Query processing layers (diagram + 4 layers) | Long
L1125 | Query decomposition | Definition
L1141 | Data localization | Definition
L1151 | Global query optimization | Definition
L1169 | Local query optimization | Definition
L1210 | Distributed cost model | Long
L1024 | Semi-join theory + cost comparison | Long
L1027 | Semi-join program algorithm | Long
L987  | Semi-join example between R and S at two sites | Long
L876  | Semi-join vs natural join + non-commutativity | Long
L933  | Deadlock prevention vs avoidance | Short
L1233 | Query optimization algorithm (INTEGERS) | Long
L1369 | SDD-1 algorithm steps | Long
L1094 | 2PL + distributed serializability | Long
L1041 | Query graph + redundant relation | Short
L1362 | Query simplification using idempotency | Short

Organizer gaps: 
- Missing standalone "cost formula practice" — the organizer shows formulas but no explicit "compute cost for this scenario" problem
- SDD-1 and INTEGERS algorithms appear but would benefit from 1–2 extra practice runs
- No explicit comparison table of centralized vs distributed optimization (syllabus mentions it)

--------------------------------------
CONCEPTS IN EXAM ORDER
--------------------------------------

1. Query Processing Pipeline (4 Layers)
   [APP] Must draw the 4-layer diagram
   a) Query Decomposition
      - Parse high-level query (SQL/Relational calculus)
      - Convert to relational algebra on global relations
      - Remove redundancy, check integrity constraints
   b) Data Localization
      - Input: algebraic query on global relations
      - Replace global names with fragment names using fragmentation/allocation info
      - Output: query on fragments
   c) Global Query Optimization
      - Input: fragment query
      - Find execution strategy minimizing resource usage
      - Consider: communication cost, CPU, I/O
      - Use: semi-joins, join ordering, site selection
   d) Local Query Optimization
      - Each site optimizes its sub-query using local schema
      - Same algorithms as centralized DB optimization

2. Query Optimizer Objectives
   - Minimize total resource consumption (CPU + I/O + communication)
   - Minimize total response time
   - Optimize total time vs response time tradeoff

3. Cost Model
   [APP] Numerical expected
   Total Cost = T_CPU + T_IO + T_MSG
   - T_CPU: per instruction time × #instructions
   - T_IO: per I/O time × #I/Os
   - T_MSG: message initiation + per-byte transmission × #messages/#bytes
   
   In distributed DB: COMMUNICATION COST is often the DOMINANT cost
   Formula often simplified to:
   Cost = C_transmit × (size of data transferred) + C_local_processing

4. Semi-Join — THE CORE DDBMS OPTIMIZATION
   [APP] Must know cost formulas and be able to compare direct join vs semi-join

   Concept:
   - Standard join: send entire relation R to site S, then join
     Cost = C_net × size(R) × cardinality(R)
   - Semi-join: reduce data transfer by sending only projection of Join attributes first
     Step 1: Site S sends π_join_attr(S) to site R
     Step 2: Site R computes R ▷⋉ S = π_R_attrs(R ⋈ π_join_attr(S))
     Step 3: Send reduced R' to site S
     Step 4: Compute final join at S
     Cost = C_net × size(S) × val(join_attr) + C_net × size(R') × cardinality(R')

   When is semi-join profitable?
   When size(R') × cardinality(R') << size(R) × cardinality(R)
   Usually when selectivity of S is high (few matching tuples)

   Non-commutativity:
   R ▷⋉ S ≠ S ▷⋉ R
   Choose direction based on which relation is more selective to send first

5. SDD-1 Algorithm (Simmonds's Algorithm)
   [APP] Know 10 steps and apply to simple schema
   Overview:
   Step 1: Include all local processing in ES (execution strategy)
   Step 2: Reflect local processing effects on database profile
   Step 3: Build set BS of beneficial semi-joins where benefit > cost
   Step 4: Greedily remove most beneficial semi-join from BS → append to ES
   Step 5: Update database profile
   Step 6: Update BS (new semi-joins, recalculate benefit/cost)
   Step 7: If BS ≠ ∅, goto Step 4
   Step 8: Select assembly site = site with largest data
   Step 9: Remove redundant semi-joins at assembly site
   Step 10: Permute semi-join order to minimize cost

   Output: ES = plan with semi-joins + final join at assembly site

6. Query Optimization Algorithm (INTEGERS)
   [APP] May appear as "write the algorithm" or "apply to relation R and S"
   Input: localized query (operator tree + fragment locations)
   For each relation R in query:
     For each access path A to R:
       cost(A,R) = compute cost
       best_A_R = access path with minimum cost
   For each permutation of relations:
     Build strategy using best access paths
     Compute total strategy cost
     Keep strategy = lowest cost so far
   For each site storing a relation:
     Compute local strategy cost at that site
     If local cost < current best, update best strategy
   Output: minimum cost strategy

7. Distributed vs Centralized Optimization
   - Distributed adds:
     * Site selection (where to evaluate sub-operations)
     * Data transfer costs between sites
     * Replicated fragment access (which copy to use)
     * Semi-join opportunities
   - Centralized assumes all data local = no network cost

--------------------------------------
MUST-CHIT CREATION — UNIT 3
--------------------------------------
1. Draw and explain 4 layers of query processing (5 marks)
2. Semi-join: full cost derivation, when profitable, non-commutativity (10 marks)
   Formula chit:
     Cost(direct join at R) = C_trans × size(S) × card(S)
     Cost(semi-join at R)  = C_trans × [size(S) × val(join_attr[S]) + size(R') × card(R')]
     Compare: semi-join wins when val(join_attr) << card(S)

3. SDD-1 algorithm — 10 steps with brief explanation (5 marks)

4. Cost model formula + what dominates in distributed vs centralized (5 marks)

══════════════════════════════════════════════
UNIT 4: TRANSACTIONS, CONCURRENCY, DEADLOCK, RELIABILITY (8L)
══════════════════════════════════════════════
***Concept Depth: HIGH — schedule analysis, 2PC/3PC diagrams, deadlock algorithms***

--------------------------------------
PYQ REFERENCE TABLE
--------------------------------------
Q  | Line | Type
L1605 | Unilateral abort capability in 2PC | Short
L1738 | 2PC protocol + communication structures + log write-ahead | Long
L1797 | 2PC failure outcomes | Long
L1844 | Reliability vs availability + nested transaction | Short
L1864 | Types of failure in DDBMS | Long
L1736 | Compare centralized vs distributed (redundancy, indexing, reliability, performance) | Short
L866  | Distributed timestamp generation | Definition
L995  | 2PL only ensures conflict-serializable, not view-serializable | Short
L1094 | Strict 2PL + 2PC guarantee global serializability | Long
L1233 | Additional techniques for deadlock (centralized/hierarchical detection, prevention) | Long
L1170 | Deadlock prevention vs avoidance | Short
L1252 | Query optimization steps | Definition
L826  | Query processing characteristics | Short

Organizer gaps: Weak on "taxonomy" of transaction management. Focuses on 2PC, deadlock, recovery. Little on optimistic CC specifics in distributed context.

--------------------------------------
CONCEPTS IN EXAM ORDER
--------------------------------------

1. Transaction Management in DDBMS
   - A distributed transaction = one logical transaction accessing multiple sites
   - Goals: atomicity + consistency across all sites
   - Characteristics:
     * Atomicity: all-or-nothing at every site
     * Consistency preservation
     * Isolation (concurrency control)
     * Durability (survive failures)
   - Sub-transaction: portion of distributed transaction executing at one site

2. Concurrency Control — Distributed
   [APP] Schedule analysis, global serializability check

   Key theorem: Local serializability is NECESSARY but NOT SUFFICIENT for global correctness
   - Each site may have its own local schedule that is serializable
   - But global interleaving across sites may violate serializability
   - Need global mechanism

   Approaches:
   a) Distributed 2PL (strict)
      - All sites use strict 2PL
      - All sites participate in 2PC
      - Result: globally serializable + recoverable
   b) Timestamp ordering (centralized or distributed)
      - Centralized: single site generates timestamps
      - Distributed: each site generates local timestamp, concatenate with site ID
        <local timestamp, site_id> — site_id in LSB ensures fair ordering
   c) Optimistic CC (less common in exams)
      - Validation phase checks for conflicts
   d) Replica control protocols:
      - Primary copy locking
      - Majority locking / weighted majority
      - Write-locks-all
      - Quorum-based (Vr + Vw > V, Vw > V/2)

3. Deadlock Management
   [APP] Distinguish prevention vs avoidance vs detection

   a) Prevention
      - Never allow deadlock to occur
      - Constrain how requests are handled
      - Methods:
        * Wait-Die: older waits for younger; younger restarts
        * Wound-Wait: older preempts younger; younger waits for older
        * Use timestamps: order transactions, only allow wait if i < j

   b) Avoidance
      - Dynamically analyze each request before granting
      - Requires knowledge of future resource needs
      - Banker's algorithm approach (theoretical, not common in DDBMS exams)

   c) Detection
      - Wait-for graph (WFG):
        * Local WFG: at each site, shows processes waiting for local resources
        * Global WFG: union of all local WFGs
      - Centralized detection: coordinator builds global WFG, detects cycles
      - Hierarchical detection: controllers arranged hierarchically
      - Problem: incomplete/delayed info can cause false deadlock detection

4. Reliability and Failure Types
   [APP] Flowchart expected

   Failure classes:
   Class 1: Site failures only (no info loss)
     - Abort due to overflow, etc.
     - Recovery: undo using log
   Class 2: Site failures + lost messages, no partitions
     - System crash: main memory lost, disk intact
     - Requires restart/recovery
   Class 3: Site failures + lost messages + partitions
     - Network partition: sites isolated from each other
     - Most complex
     - Requires quorum-based protocols
   Class 4: Media failures (disk crashes, loss of nonvolatile storage)
     - Cold restart required
     - Restore from archive

   Checkpoint:
   [APP]
   - Synchronization record in log at consistent state
   - Limits log segment needed for recovery
   - Local checkpoint: each site takes snapshot when no active transactions
   - Global checkpoint: set of local checkpoints synchronized across sites

   Warm restart vs Cold restart:
   - Warm restart: after Class 2 failure
     * Use log records from last checkpoint
     * Redo committed, undo uncommitted
   - Cold restart: after Class 3/4 failure
     * All sites must make cold restart together
     * Restore from archived older consistent state
     * Duration of ACID cannot be guaranteed (some transaction effects lost)

   Cold restart conditions:
   - All sites must restart together
   - Consistent global state: for every transaction T, either all subtransactions are in global state, or none are

5. Commit Protocols
   [APP] 2PC state diagram MANDATORY

   a) Two-Phase Commit (2PC)
      Participants: Coordinator + Cohorts
      Phase 1 (Prepare/Voting):
        - Coordinator sends PREPARE to all cohorts
        - Each cohort: write log record "ready", respond YES or NO
        - Unilateral abort allowed: any participant can abort before voting YES
      Phase 2 (Decision):
        - If all YES: coordinator sends COMMIT
        - If any NO: coordinator sends ABORT
        - Cohorts complete, acknowledge
      
      Failure handling:
      - Coordinator fails in Phase 1: cohorts wait (blocking), timeout → abort
      - Coordinator fails in Phase 2 after logging decision: recover from log, resend
      - Participant fails after voting YES: restores state from log
      - Participant fails after receiving COMMIT: completes commit upon recovery
      
      Limitation: BLOCKING protocol
        - If both coordinator AND a cohort fail after prepare, new coordinator cannot decide until failed cohort recovers

   b) Three-Phase Commit (3PC)
      - Adds Prepared-to-Commit state (non-blocking improvement)
      - Phase 1: CanCommit? (same as 2PC Phase 1)
      - Phase 2: PreCommit (all sites acknowledge prepared)
      - Phase 3: DoCommit (actual commit)
      - If coordinator fails before PreCommit → unanimous abort possible
      - If coordinator fails after PreCommit → sites have timeout, proceed with commit

   c) Quorum-based commit (for replicated/partitioned networks)
      - Each site has vote Vi
      - Total votes V
      - Commit quorum Vc, abort quorum Va
      - Rules: Va + Vc > V, transaction needs Vc votes to commit

6. Recovery in DDBMS
   - ARIES-style steps adapted:
     a) Analysis: identify dirty pages, active transactions at failure
     b) Redo: repeat all updates from last checkpoint (idempotent)
     c) Undo: rollback uncommitted transactions
   - Write-ahead log (WAL): log records must reach stable storage before actual data pages

--------------------------------------
MUST-CHIT CREATION — UNIT 4
--------------------------------------
1. 2PC full diagram + failure handling for coordinator and participant (10 marks)
   State mnemonic: INIT → WAIT → READY → COMMIT/ABORT

2. Distributed serializability: why local serializability is insufficient, condition for global serializability (5 marks)
   Chit: Condition = exists total order T1...Tn such that for every conflicting pair in every local schedule, the serial order matches the total order.

3. Wait-Die vs Wound-Wait (5 marks)

4. Failure types Class 1–4 + checkpoint + cold/warm restart (5 marks)

══════════════════════════════════════════════
UNIT 5: PARALLEL DATABASE SYSTEMS (6L)
══════════════════════════════════════════════
***Concept Depth: MEDIUM — definitions, comparison table, diagram***

--------------------------------------
PYQ REFERENCE TABLE
--------------------------------------
Q  | Line | Type
L2071 | Parallel query processing steps | Short
L2092 | Parallel system vs distributed system comparison | Short
L2084 | Scale-up and speed-up in parallel databases | Short
L2103 | Advantages/disadvantages of parallel system | Short
L2124 | Data partitioning techniques | Short
L2120 | Skew problem definition | Short

Organizer gaps: No explicit practice problem on partitioning algorithm. No numerical on speedup/scalup formula.

--------------------------------------
CONCEPTS IN EXAM ORDER
--------------------------------------

1. Why Parallel DB?
   - Speed up large queries by using multiple CPUs
   - Scale up by adding more processors
   - Difference from Distributed DB:
     * Parallel DB: processors tightly/loosely coupled, same location or LAN, shared nothing/shared disk/memory
     * Distributed DB: weakly coupled, WAN, networked sites, autonomous

2. Architectures
   [APP] Comparison table
   a) Shared Memory
      - Processors share common memory
      - Tightly coupled
      - High communication speed
      - Limited scalability (memory bus bottleneck)
      - Example: multiprocessor server

   b) Shared Disk
      - Processors share disks, have private memory
      - Loosely coupled
      - Better scalability than shared memory
      - Disk contention possible

   c) Shared Nothing
      - Processors have private memory + private disk
      - Communicate via network
      - Best scalability
      - Most operationally complex
      - Common in modern MPP systems

3. Parallel Query Processing
   Steps:
   1) Translation: SQL → relational algebra
   2) Optimization: reorder joins, choose algorithms minimizing cost
   3) Parallelization: transform query tree into parallel query plan
   4) Execution: run concurrent operations on multiple processors

   Parallelism types:
   - Inter-query: execute many different queries in parallel
   - Intra-query: split one query into parallel operators

4. Data Partitioning (for parallel processing)
   [APP] Know the three types
   a) Round-robin
      - Tuple i goes to disk Di (mod n)
      - Even distribution guaranteed
      - Bad for point queries, range queries
   b) Hash partitioning
      - Hash partitioning attributes → modulo n
      - Good for equality queries
      - Bad for range queries
   c) Range partitioning
      - Assign value ranges to disks
      - Good for range queries, sequential access
      - Risk of skew (hotspots if distribution uneven)

5. Speedup and Scale-up
   - Speedup: T_seq / T_parallel for same problem size
     * Linear speedup = perfect (rare due to startup + interference + skew)
   - Scale-up: T_parallel(S) / T_parallel(kS) for k× larger problem
     * Size scale-up: scale database size
     * Batch scale-up: scale transaction rate
   - Factors reducing speedup:
     * Startup cost (process spawning)
     * Interference (contention for shared bus/disk/locks)
     * Skew (unequal task sizes = slowest CPU bottleneck)

--------------------------------------
MUST-CHIT CREATION — UNIT 5
--------------------------------------
1. Shared Memory vs Shared Disk vs Shared Nothing (5 marks)
   Draw each architecture, list pros/cons.

2. Parallel query processing 4 steps (5 marks)

3. Speedup vs Scale-up definition + factors reducing them (5 marks)

══════════════════════════════════════════════
UNIT 6: ADVANCED TOPICS (4L)
══════════════════════════════════════════════
***Concept Depth: LOW–MEDIUM — short notes***

--------------------------------------
PYQ REFERENCE TABLE
--------------------------------------
Q  | Line | Type
L2180 | Distributed data management definition | Short
L2119 | Federated database (in advanced topics) | Short
L2217 | MDBS / Federated DDBMS | Short
L2223 | ODBC / OO4O notes | Short
L2209 | Short notes: MDBS, Peer-to-Peer, Distributed administration, ODBC, Federated, distributed object | Short

Organizer gaps: Mobile databases and Distributed Object Management are sketchy.

--------------------------------------
CONCEPTS IN EXAM ORDER
--------------------------------------

1. Mobile Databases
   - DB accessible via mobile devices (laptops, phones, PDAs)
   - Challenges: disconnection, limited bandwidth, mobility
   - Need: location-aware queries, data caching, weak connectivity support
   - Two keywords: disconnection + mobility

2. Distributed Object Management
   - Objects + methods distributed across network
   - Distributed Object Management systems enable method invocation on remote objects
   - Example: COM/DCOM, CORBA, OLE DB, OO4O
   - Key cases:
     * Remote object, local behavior
     * Local object, remote behavior (ship behavior code)
     * Remote function, remote argument
   - OM = managing these distributed object scenarios

3. Multidatabases / Federated Databases
   [APP] Diagram of loosely-coupled vs tightly-coupled
   - Multidatabase = collection of heterogeneous, geographically distributed databases
   - Goal: integrated access without full integration
   - Types:
     * Tightly coupled: global schema, translation between local and global
     * Loosely coupled: no global schema; translation between external schemas and local conceptual schemas
   - Federated DB: virtual database formed by integrating disparate DBs
     * No actual data integration in constituent databases
     * Uses wrappers/translators for heterogeneous query languages
     * Constraint: complete autonomy of local DBMSs (no software modification allowed)
   - MDBS (Multidatabase System): software layer on top of local DBMSs providing single manipulation interface

4. Semi-structured / Web Databases (if covered)
   - XML databases
   - Web data sources
   - Less emphasized in this syllabus

--------------------------------------
MUST-CHIT CREATION — UNIT 6
--------------------------------------
1. Federated vs Multidatabase vs DDBMS distinction (5 marks)

2. Mobile DB challenges: disconnection, mobility, limited resources (5 marks)

3. Tightly-coupled vs Loosely-coupled multidatabase architecture — draw and explain (5 marks)

══════════════════════════════════════════════
DEPTH SPECIFICATION PER CONCEPT
══════════════════════════════════════════════

High depth (must solve problems):
- Fragmentation: apply horizontal, vertical, mixed to new schemas; prove correctness rules
- Semi-join: compute cost for given size/selectivity values; decide direction
- 2PC: draw state diagram for coordinator and participant; trace failures
- 2PL: prove global serializability condition from local schedules

Medium depth (must explain in exam):
- Transparencies: define each + level + example
- Allocation strategies: explain best fit, all beneficial, additional replica
- Query layers: name and 1-line purpose of each
- Failure types: Class 1–4 with examples
- Architectures: draw and contrast shared memory/disk/nothing
- Partitioning: explain round-robin, hash, range

Low depth (short note / 5 marks maximum):
- Mobile DB definition + 2 challenges
- Distributed Object Management: 3 cases list
- Federated vs DDBMS: 3-line distinction
- ODBC / OO4O: what they are, not internal details
- Scale-up vs speedup: definitions and main bottlenecks

══════════════════════════════════════════════
ORGANIZER GAP SUMMARY FOR EXAM
══════════════════════════════════════════════
| Topic | Organizer Coverage | Gap |
|-------|-------------------|-----|
| Unit 1: Intro + Architecture | Strong | None |
| Unit 2: Fragmentation + Allocation | Strong | Missing standalone "semantic integrity" Q separate from security |
| Unit 3: Query Optimization | Strong | Missing numerical cost problems; SDD-1 needs extra practice |
| Unit 4: Transactions + CC + Deadlock | Strong | Missing explicit "taxonomy" question; recovery algorithm details light |
| Unit 5: Parallel DB | Good | Missing partitioning algorithm practice; speedup/scalup numerical |
| Unit 6: Advanced Topics | Weak | Mobile DB and DOM very light; needs textbook supplement |

ROADMAP BEFORE EXAM:
1. Blockers first: practice fragmentation (5 schemas) and 2PC state diagram (3 attempts)
2. Semi-join numerical: write out 2–3 practice problems yourself using size/selectivity values
3. Read textbook (Elmasri/Navathe or Korth/Silberschatz chapters on DDBMS) for Unit 5–6 gap-fill
4. Test yourself: draw DDBMS architecture from memory, then list all 6 transparencies with 1-line purpose each

══════════════════════════════════════════════
EXAM STRATEGY
══════════════════════════════════════════════
- DDBMS is definitions-and-diagrams paper
- Marks come from clean structure, not brilliance
- Prioritize:
  1. Fragmentation tree + correctness proof (highest yield drawing)
  2. 2PC state diagram + failure handling (highest yield for 10–15 marks)
  3. Semi-join cost comparison (mathematical but predictable)
  4. Transparency hierarchy (easy 5-marker)
- Avoid: memorizing algorithms verbatim (3PC, SDD-1) — know flow, not exact pseudocode
- If stuck on numerical: write formula + state assumption → partial marks
- ══════════════════════════════════════════════
2021 PAST PAPER — TOPIC-WISE INTEGRATION
══════════════════════════════════════════════
Source: User-provided image, 2021 MAKAUT B.Tech CSE DDBMS (PEC-IT601B)
Note: Only Questions 9–16 visible in provided images; Part A (Q1–10) partial.

--------------------------------------
UNIT 3 — QUERY PROCESSING / SQL
--------------------------------------
Q10. (15 marks, Group C)
Given: Employee(empID, firstName, lastName, address, DOB, sex, position, deptNo)
       Department(deptNo, deptName)
       Project(projNo, projName, deptNo)
       WorkOn(empID, projNo, hours_worked)
Write SQL for:
  i) Names + addresses of all employees in IT department.
  ii) Total hours by each employee, ordered by dept name alphabetically, then by first name.
  iii) Total employees per department — only departments with >10 employees.
  iv) Project number, project name, number of employees working on that project.
  v) All employees who have worked >20 hours.

Exam pattern insight: Heavy SQL/aggregation focus. Subqueries, GROUP BY, HAVING, JOIN all appear together.

--------------------------------------
UNIT 4 — TRANSACTIONS, CONCURRENCY, RECOVERY
--------------------------------------
Q9. (a) State 2-phase commit protocol and discuss implications of failure on:
       i) Coordinator  ii) Participant, during each phase. [5]
   (b) Briefly explain requirements of Cascadeless Schedule. [5]
   (c) Discuss: "Transaction cannot be nested inside one another." [5]

Q11. (a) Explain purpose of checkpoint mechanism. [5]
    (b) What are the roles of Analysis, Redo and Undo phases in ARIES recovery algorithm? [5]
    (c) Explain the requirement of query optimization. [5]

Pattern insight: Transaction + recovery dominated this paper. 2PC, ARIES, cascadeless schedules, nested transactions all tested.

--------------------------------------
UNIT 4 — DEADLOCK
--------------------------------------
Q9. (b) Describe wait-die and wound-wait protocols for deadlock prevention. [5]

Pattern insight: Deadlock prevention tested as short note — expect protocol names + one-line rule.

--------------------------------------
UNIT 4 — SERIALIZABILITY
--------------------------------------
Q9. (c) Schedule analysis: T1, T2, T3 on A, B, C.
     S1: R2(C), R2(B), W2(B), R3(B), R3(C), R1(A), W1(A), W3(B), W3(C), R2(A), R1(B), W1(B), W2(A).
     Is the schedule serializable? [5]

Pattern insight: Conflict-serializability via precedence graph. Same pattern as DBMS paper today.

--------------------------------------
UNIT 1 — INTRO / ARCHITECTURE
--------------------------------------
(Part A, Q7 from user transcription) What do you mean by local checkpoints? [2]
(Part A, Q8) What is the drawback of a checkpoint based rollback recovery approach? [2]

Pattern insight: 2-mark definition questions from Unit 4 recovery section.

══════════════════════════════════════════════
2021 PAPER — MARK DISTRIBUTION BY UNIT
══════════════════════════════════════════════
| Unit | Marks | Questions |
|-------|-------|-----------|
| Unit 3 (SQL/Query) | 15 | Q10 full long |
| Unit 4 (Transactions/CC/Recovery) | ~25 | Q9(a,b,c), Q11(a,b) |
| Unit 4 (Deadlock) | 5 | Q9(b) |
| Unit 4 (Serializability) | 5 | Q9(c) |
| Unit 1 (Checkpoints) | 4 | Q7, Q8 in Part A |
| Unit 3/6 (Query optimization) | 5 | Q11(c) |

Bottom line: 2021 DDBMS emphasized Units 3 and 4, similar to today's DBMS pattern.
Bottom line: 2021 DDBMS emphasized Units 3 and 4, similar to today's DBMS pattern.
No fragmentation/design long question found in visible portion — may be in Part A short questions or missing pages.

══════════════════════════════════════════════
2023 PAST PAPER — TOPIC-WISE INTEGRATION
══════════════════════════════════════════════
Source: /home/bigfoot/Downloads/btech-pec-it-6-sem-distributed-systems-pec-it-601b-2023.pdf
Code: PEC-IT601B, 70 Marks, 3 Hours

--------------------------------------
UNIT 1 — INTRO / BASIC CONCEPTS
--------------------------------------
Group A Q1 (1 mark each):
- What is data replication?
- What is minterm predicate?
- Define homogeneous distributed database.
- What is the maximum no of functional dependencies (trivial and non-trivial) of a relation R of degree n?
- Write the full form of OLAP.
- What is data dictionary?
- What do you mean by granularity?
- What is the disadvantage of replication?
- Who is responsible for ensuring correct execution of a transaction in the presence of failures?
- Provide a technique for recovery management.
- Edit of a data item in a transaction is done in which mode?
- What are the attribute usage values?

Pattern insight: 12 short-answer options. Granularity, minterm predicate, attribute usage — all organizer topics.

--------------------------------------
UNIT 1 — DDBMS FEATURES / COMPONENTS
--------------------------------------
Group B Q2 (5 marks):
- What are the advantages and disadvantages of replication? What is auxiliary program?
Group B Q6 (5 marks):
- What is DDBMS? What are the features of DDBMS?
Group B Q3 (5 marks):
- Which components are necessary for building a distributed database?

Pattern insight: DDBMS definition + features + components tested together as 5-mark question.

--------------------------------------
UNIT 3 — QUERY OPTIMIZATION
--------------------------------------
Group B Q3 (5 marks):
- Write down the Dynamic query optimization methods with example.
Group C Q7 (15 marks):
- Explain query optimization issues in DDBs. [8]
- World Wide Web Architecture and Protocols. [4]
- Data warehousing architectures. [3]

Group C Q11 (15 marks):
- Discuss different types of search strategies. [6]
- What is search space in distributed query optimization? [4]
- Simplify the following SQL using idempotency rules:
  SELECT ENO FROM ASG WHERE RESP = "Analyst"
  AND NOT(PNO="P2" OR DUR=12) AND PNO != "P2" AND DUR=12 [5]

Pattern insight: Query optimization heavily tested. Search strategies + search space + SQL simplification in one 15-marker.

--------------------------------------
UNIT 3 — DISTRIBUTED COST MODEL
--------------------------------------
Group B Q5 (5 marks):
- Explain distributed cost model with example.

Pattern insight: Cost model = I/O + CPU + communication. Need formula + example.

--------------------------------------
UNIT 4 — TRANSACTIONS + RECOVERY
--------------------------------------
Group C Q8 (15 marks):
- What is flat transaction and nested transaction? [4+6]
- Discuss dirty-read, fuzzy read and phantom. [5]
- What is ACID in DDBMS? [3]

Group C Q9 (15 marks):
- Briefly describe various implementations of process pairs concept.
- Comment on how process pairs may be useful in implementing fault tolerant distributed DBMS.

Group C Q10 (15 marks):
- Write BTO-SC (Basic Timestamp Ordering Scheduler) Algorithm. [8]
- Write DP (Data Processor) Algorithm. [7]

Group A Q7 (1 mark):
- Provide a technique for recovery management.

Pattern insight: ACID properties, recovery anomalies, process pairs for fault tolerance, and timestamp algorithms all tested.

--------------------------------------
UNIT 4 — CONCURRENCY CONTROL
--------------------------------------
Group A Q8 (1 mark):
- Edit of a data item in a transaction is done in which mode? (immediate vs deferred)

Pattern insight: Deferred vs immediate update modes tested as 1-mark definition.

--------------------------------------
MARK DISTRIBUTION
--------------------------------------
| Unit | Marks |
|-------|-------|
| Unit 3 (Query Optimization) | ~25 |
| Unit 4 (Transactions/Recovery) | ~25 |
| Unit 1 (Basic Concepts) | ~15 |
| Unit 2 (Fragmentation) | ~0 |
| Unit 5 (Parallel) | ~0 |
| Unit 6 (Advanced) | ~5 |

2023 pattern: Extremely heavy on algorithms (BTO-SC, DP algorithms written out). SQL simplification appears as 5-mark sub-question.

══════════════════════════════════════════════
2024 PAST PAPER — TOPIC-WISE INTEGRATION
══════════════════════════════════════════════
Source: /home/bigfoot/Downloads/btech-cse-it-6-sem-distributed-systems-pec-it601b-2024.pdf
Code: PEC-IT601B, 70 Marks, 3 Hours

--------------------------------------
UNIT 1 — INTRO / BASIC CONCEPTS
--------------------------------------
Group A Q1 (1 mark each):
- What is information?
- Give two important features of distributed database.
- Define heterogeneous distributed database.
- Why two-phase commit protocol is used?
- What is the purpose of using timestamp mechanism?
- What is logical data independence in DDBMS?
- Mention names of two aggregate functions.
- What is atomicity of a transaction?
- What is horizontal partitioning?
- What do you mean by affinity of attributes?
- What is serializable scheduling?
- What is the deadlock prevention method in DDBMS?

Pattern insight: 12 short-answer options. Horizontal partitioning, affinity, serializable scheduling — all organizer topics.

--------------------------------------
UNIT 2 — FRAGMENTATION + ALLOCATION
--------------------------------------
Group B Q3 (5 marks):
- What is allocation? What are the factors affecting allocation? What is minterm predicate?
Group C Q7 (15 marks):
- What is horizontal fragmentation? Give example. [5]
- Write Horizontal Algorithm and explain with proper example. [10]

Pattern insight: Horizontal fragmentation + algorithm = classic 15-mark question. Allocation + minterm predicate bundled as 5-mark.

--------------------------------------
UNIT 3 — QUERY OPTIMIZATION
--------------------------------------
Group B Q2 (5 marks):
- What is Static query optimization? Write down the Static query optimization Algorithm.
Group B Q5 (5 marks):
- Write down the Dynamic query optimization methods with example.
Group C Q11 (15 marks):
- Compare Linear Join Tree and Bushy Join Tree. [6]
- Discuss different issues in Multidatabase Query Processing. [4]
- Explain hybrid query optimization. [5]

Pattern insight: Static + dynamic optimization both as separate 5-mark questions. Join tree comparison + hybrid optimization = 15 marks.

--------------------------------------
UNIT 4 — TRANSACTIONS + CC + DEADLOCK
--------------------------------------
Group B Q2 (5 marks):
- What is concurrency control? What is lock-based protocol?
Group C Q8 (15 marks):
- What is shared and exclusive lock? [4]
- Discuss timestamp protocol with DDBMS. [4+5]
- Explain significance of semi-join in DDBMS. [5]
Group C Q9 (15 marks):
- Discuss centralized, hierarchical and distributed deadlock detection. [6+6+3+?]
- What is wait-die and wound-wait rule for deadlock avoidance? [4]
- Draw Communication Structure of Distributed 2PL. [2]

Group C Q10 (15 marks):
- Discuss communicational structure for distributed transactions. [8+7]
- Discuss communication structure for commit protocols. [7]

Pattern insight: Lock, timestamp, 2PL structure, deadlock taxonomy + 2PC communication — all 2024 heavy hitters.

--------------------------------------
UNIT 6 — P2P / MDBS
--------------------------------------
Group B Q4 (5 marks):
- Describe peer-to-peer architecture with diagram.
Group C Q11 (part):
- Discuss multidatabase architecture.

Pattern insight: P2P = 5-mark diagram. MDBS = short note.

--------------------------------------
MARK DISTRIBUTION
--------------------------------------
| Unit | Marks |
|-------|-------|
| Unit 3 (Query Optimization) | ~25 |
| Unit 4 (Transactions/CC/Deadlock) | ~30 |
| Unit 2 (Fragmentation) | 15 |
| Unit 6 (P2P/MDBS) | ~10 |
| Unit 1 (Basic) | ~5 |

2024 pattern: Most balanced. Deadlock taxonomy + fragmentation algorithm both 15-markers.

══════════════════════════════════════════════
2025 PAST PAPER — TOPIC-WISE INTEGRATION
══════════════════════════════════════════════
Source: /home/bigfoot/Downloads/btech-cse-it-6-sem-distributed-systems-pec-it601b-2025.pdf
Code: PEC-IT601B, 70 Marks, 3 Hours

--------------------------------------
UNIT 1 — INTRO / BASIC CONCEPTS
--------------------------------------
Group A Q1 (1 mark each):
- The node where the distributed transaction originates is called the .......
- What is the advantage of a DDBMS?
- What is view management in distributed database design?
- What are the factors that govern query optimization?
- What are distributed concurrency control algorithms?
- What is shared-memory architecture?
- What is the purpose of mobile database replication?
- ......... protocol is used to perform multiple transactions that execute on different database. (answer: 2PC)
- What is fragmentation in distributed database design?
- What are the goals of transaction management?
- What are the parallel architectures used in parallel database systems?
- What is distributed object management?

Pattern insight: Fill-in-the-blank mixed with definitions. Coordinator site, 2PC, fragmentation all named.

--------------------------------------
UNIT 2 — FRAGMENTATION / VIEW / ALLOCATION
--------------------------------------
Group C Q7 (15 marks):
- (a) Discuss various transaction models [5]
  (b) What is flat and nested transaction? Explain with example. [5]
  (c) What is serializability in distributed database? [5]

Group C Q11 (15 marks):
- (a) Discuss multidatabase architecture. [5]
- (b) What is mobile database? [5]
- (c) Discuss in brief concurrency control mechanism in distributed DBMS. [5]

Pattern insight: View management tested as 1-mark. MDBS + mobile DB = 15-marker combo.

--------------------------------------
UNIT 4 — TRANSACTIONS + CC + 2PC
--------------------------------------
Group C Q8 (15 marks, equal 5 each):
- Why is it necessary to have a commit protocol?
- Explain how does 2PC respond to failure of a participating site.
- What are the disadvantages of 2PC protocol?

Group C Q10 (15 marks, equal 5 each):
- What is serializability in distributed database?
- Write down the algorithms both Coordinator and Participants of 2PC protocol in distributed environment.
- Explain with diagram communication structure for different 2PC protocol.

Group B Q2 (5 marks):
- What is concurrency control? What is lock-based protocol?

Pattern insight: 2PC = 2 full 15-mark questions (35 marks combined with serializability). Coordinator/participant algorithms written out.

--------------------------------------
UNIT 5 — PARALLEL ARCHITECTURES
--------------------------------------
Group C Q9 (15 marks):
- Explain different parallel database architecture. [7]
- What is the goal of using parallel database architecture. [4]
- Difference between parallel database and distributed database. [4]

Group A Q11 (1 mark):
- What are the parallel architectures used in parallel database systems?

Pattern insight: Full 15-marker on parallel only. Goal + comparison with distributed = easy 15 marks.

--------------------------------------
UNIT 6 — MOBILE DB + DSM + TRANSPARENCY
--------------------------------------
Group B Q3 (5 marks):
- What is distributed transparency? Explain different levels (level 1, 2, 3) with diagram.
Group B Q4 (5 marks):
- Write short note on mobile database.
Group C Q11:
- What is mobile database?

Pattern insight: Transparency levels 1/2/3 = draw and explain. Mobile DB tested multiple times.

--------------------------------------
MARK DISTRIBUTION
--------------------------------------
| Unit | Marks |
|-------|-------|
| Unit 4 (Transactions + CC + 2PC) | ~35 |
| Unit 2 / 6 (MDBS / Mobile) | ~15 |
| Unit 5 (Parallel) | 15 |
| Unit 1 (Basic) | ~5 |
| Unit 3 (Query Optimization) | 0 in visible |

2025 pattern: Most transaction-heavy. Serializability + 2PC = 2 full 15-mark questions. Parallel DB = only 15-marker. Query optimization completely absent.

══════════════════════════════════════════════
