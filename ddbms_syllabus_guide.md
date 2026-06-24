# Distributed DBMS — Complete Syllabus-Aligned Study Guide

## Syllabus (PEC-IT601B, 48L, 6 Units)

| Unit | Hours | Topics | Organizer Coverage | Status |
|------|-------|--------|-------------------|--------|
| Unit 1 | 8 | DDP, DDBS definition, advantages/disadvantages, problem areas, architecture, transparencies, global directory | Introduction chapter | ✅ Covered |
| Unit 2 | 11 | Design strategies, fragmentation, data allocation, view management, data security, semantic integrity, query processing basics | Design chapter | ✅ Covered |
| Unit 3 | 11 | Distributed query optimization, centralized vs distributed, ordering fragment queries, optimization algorithms | Query optimization chapter | ✅ Covered |
| Unit 4 | 8 | Transactions, concurrency control, deadlocks, reliability, commit protocols, recovery | Transaction + concurrency chapter | ✅ Covered |
| Unit 5 | 6 | Parallel database architectures, parallel query processing | Parallel DB chapter | ✅ Covered |
| Unit 6 | 4 | Mobile DB, distributed object management, multidatabases | Advanced topics chapter | ✅ Covered |

Primary files:
- /home/bigfoot/SEM-6-CSE/study_notes/ddbms_study_guide.md
- /home/bigfoot/SEM-6-CSE/study_notes/ddbms_organizer_raw.txt

Important reality:
This organizer is thinner and lower quality than DBMS/CN. It uses model-question style, not clean WBUT year tags. So this guide must be concept-first, not frequency-first.

---

## Unit-wise Core Study Map

### UNIT 1: Introduction, Architecture, Transparencies
High-yield concepts already visible in organizer:
- Distributed Data Processing (DDP)
- DDBMS definition
- Advantages / disadvantages
- DDBMS architecture
- Transparency types:
  - Fragmentation transparency
  - Location transparency
  - Replication transparency
  - Naming transparency
  - Local mapping transparency
- Global directory / catalog

What to memorize:
1. DDBMS = logically one database, physically distributed over networked sites
2. Advantages:
   - modular growth
   - local autonomy
   - reliability / availability
   - better response near users
   - data sharing
3. Disadvantages:
   - complexity
   - security challenges
   - concurrency / recovery harder
   - network dependence
4. Transparency = system hides distribution details from user
5. Fragmentation transparency is the highest convenience level for users

---

### UNIT 2: Design, Fragmentation, Allocation, Semantics
Core topics:
- Top-down vs bottom-up design
- Fragmentation:
  - Horizontal
  - Vertical
  - Mixed / hybrid
  - Derived horizontal fragmentation
- Allocation:
  - centralized
  - partitioned
  - replicated
- View management
- Data security
- Semantic data control / integrity
- Query decomposition and localization

What to memorize:
1. Top-down = design from scratch for enterprise-wide DDBMS
2. Bottom-up = integrate existing local databases
3. Horizontal fragmentation = rows split by predicates
4. Vertical fragmentation = columns split by attributes + key retained for reconstruction
5. Mixed fragmentation = both row and column fragmentation
6. Correct fragmentation conditions:
   - completeness
   - reconstruction
   - disjointness (where applicable)
7. Allocation tradeoff:
   - replication improves availability/read speed
   - partitioning reduces redundancy

---

### UNIT 3: Distributed Query Processing / Optimization
Core topics:
- Query processing layers
- Query decomposition
- Localization of global query into fragment queries
- Semi-join
- Cost factors:
  - CPU cost
  - disk I/O
  - communication cost
- Centralized vs distributed optimization
- Fragment ordering / join ordering

What to memorize:
1. In distributed systems, communication cost is often the dominant cost
2. Semi-join reduces data transfer before full join
3. Optimization goal = minimize total response time / resource usage across sites
4. Query decomposition pipeline:
   global query -> relational operations -> fragment localization -> local optimization -> execution plan

Exam-safe semi-join intuition:
Instead of shipping whole relations across the network, send only matching projection keys first, then ship the reduced relation. It’s the logistics version of “ask what you actually need before moving the truck.”

---

### UNIT 4: Transactions, Concurrency, Deadlock, Reliability — MOST IMPORTANT UNIT
Core topics:
- Distributed transaction goals
- Concurrency control:
  - centralized vs distributed
  - locking-based protocols
  - timestamp-based approaches
  - optimistic control
  - replica control
- Deadlock management:
  - prevention
  - detection
  - distributed wait-for graph
- Reliability and failure types
- Commit protocols:
  - 2PC
- Recovery

What to memorize:
1. Distributed transaction = one logical transaction touching multiple sites
2. Main goals = atomicity + consistency across all sites
3. Distributed deadlock is harder because wait information is spread across sites
4. 2PC phases:
   - Phase 1: Prepare / Voting
   - Phase 2: Commit or Abort
5. Coordinator failure can block participants in uncertain state
6. Replica control protocols coordinate updates to replicated data copies

2PC answer skeleton:
- coordinator sends PREPARE
- cohorts vote YES/NO
- if all YES -> COMMIT
- otherwise -> ABORT
- participants acknowledge
- failure during protocol may leave blocking state

---

### UNIT 5: Parallel Databases
Core topics:
- Parallel DB architectures:
  - shared memory
  - shared disk
  - shared nothing
- Parallel query processing
- Intra-query / inter-query parallelism

What to memorize:
1. Shared nothing scales best but is operationally harder
2. Parallel DB goal = speed up large query execution
3. Parallelism types:
   - inter-query = many queries at once
   - intra-query = split one query into parallel parts

This is lower yield than Units 1, 2, and 4.

---

### UNIT 6: Advanced Topics
Topics:
- Mobile databases
- Distributed object management
- Multidatabases

What to memorize:
- one clean definition each
- 2 advantages / use-cases each
- 1 comparison point if possible

This unit is short-note territory.

---

## Best Priority Order for DDBMS
1. Transparencies + architecture
2. Fragmentation + allocation
3. 2PC + concurrency + deadlock + recovery
4. Query optimization + semi-join
5. Parallel DB
6. Advanced topics

---

## Final Revision Sheet

Know these cold:
- DDBMS definition
- Advantages / disadvantages
- Transparency types
- Top-down vs bottom-up
- Horizontal / vertical / mixed fragmentation
- Completeness / reconstruction / disjointness
- Replication vs partitioning
- Semi-join
- Communication cost as major optimization factor
- Distributed deadlock detection
- Two-Phase Commit
- Shared memory / shared disk / shared nothing
- Mobile DB / multidatabase definitions

---

## How to use your existing DDBMS notes
- ddbms_study_guide.md = source question map from organizer
- this file = syllabus order + what to memorize

Best workflow:
1. Read this file first to know what each unit wants.
2. Open ddbms_study_guide.md only for raw line references and question wording.
3. Build a one-page handwritten sheet of transparencies, fragmentation, 2PC, semi-join.

---

## Honest exam strategy
DDBMS is mostly a definitions-and-architecture paper.
That means marks come from clean structure, not brilliance.
If you can define terms sharply and draw basic architecture / fragmentation / 2PC flow, you can score well without doing anything fancy.
