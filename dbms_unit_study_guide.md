# DBMS ORGANIZER — UNIT-WISE QUESTION BANK

*Source: DBMS_Organizer_2023.pdf (WBUT question bank, OCR extracted)*
*Years covering: 2006–2023 (based on year tags in original)*

---

## UNIT-1: Introduction, Architecture & DBA

### Questions (asked in exams 2006–2023)
1. **Describe three-schema architecture of DBMS.** [2006, 2013]
2. **Explain the roles of a DBA (Database Administrator).** [2006, 2008, 2017, 2018]
3. **What is data independence? Explain logical vs physical data independence.** [2006, 2015]
4. **What is data abstraction? Explain three levels of data abstraction.** [2015]
5. **What is a data dictionary?** [2013]
6. **What separates physical data storage from logical representation?** (MCQ)
7. **What is metadata?** (MCQ)

### Key Concepts to Know
- Three-schema: External (user view), Conceptual (community view), Internal (physical storage)
- Mapping between levels
- Logical data independence: change conceptual without changing external
- Physical data independence: change internal without changing conceptual
- DBA functions: schema definition, storage definition, schema modification, authorization, backup/recovery
- Data dictionary: stores metadata about the database structure

**One-line answers for MCQs:**
- "What separates physical from logical data representation?" → Data independence
- "Metadata" = information about data in the database
- "Tree structures store data in" → Hierarchical model
- "Integrity constraint" = employee salary ≤ 20,000

---

## UNIT-2: ER Model & Relational Model

### Questions
1. **Explain ER model — entity, attribute, relationship, cardinality.** [2009, 2014]
2. **What is a weak entity? How is it different from a strong entity?** [2012]
3. **Explain relational model — tuple, relation, attribute, domain.** [2017]
4. **Explain keys: super key, candidate key, primary key, alternate key, foreign key.** [2006, 2013, 2015, 2017, 2019]
5. **What are integrity constraints — domain, referential, entity integrity?** [2018]
6. **Convert ER diagram to relational schema.** [frequent]
7. **Explain relational algebra operations: SELECT, PROJECT, JOIN, UNION, INTERSECTION, SET DIFFERENCE, CARTESIAN PRODUCT.** [2009, 2011]

### Key Concepts to Know
- Entity vs attribute vs relationship
- Cardinality: 1:1, 1:N, M:N (participation: total vs partial)
- Weak entity: no unique key of its own, identified by owner entity
- Relational model: relation = table, tuple = row, attribute = column, domain = type/range
- Keys hierarchy: super → candidate → primary → alternate → foreign
- Relational algebra operators: SELECT (σ), PROJECT (π), JOIN (⨝), CARTESIAN (×), UNION (∪)

---

## UNIT-3: SQL, Queries & Views

### Questions
1. **Write SQL queries using SELECT, WHERE, GROUP BY, HAVING, ORDER BY.**
2. **What is a subquery? Explain correlated subquery with example.** [2011]
3. **What is a view? Explain with advantages.** [2019]
4. **What is an index? Explain types of indexes.** [2016]
5. **Find Nth highest salary without using LIMIT.** [frequent in class notes]
6. **What is GRANT and REVOKE?** [2016]
7. **What are triggers?** [2012]
8. **Explain joins: inner, outer (left, right, full), cross, self, natural.** [2011, 2019]
9. **What is normalization?** → covered in Unit 4

### SQL Write-Blind Checklist (these come every year)
- Nth highest salary: nested subqueries OR correlated subquery OR TOP-N
- Find duplicate rows in a table
- Self-join for manager-employee hierarchy
- Aggregate: COUNT, SUM, AVG, MAX, MIN with GROUP BY
- HAVING vs WHERE difference

---

## UNIT-4: Normalization

### Questions (HIGHEST FREQUENCY TOPIC)
1. **What is normalization? Explain 1NF, 2NF, 3NF, BCNF, 4NF with examples.** [frequent every year]
2. **What are functional dependencies (FD)?** [core concept, 2015]
3. **What is lossless join decomposition?** [2016, 2020]
4. **What is dependency preservation?** [2018]
5. **Explain Boyce-Codd Normal Form (BCNF).** [2011, 2019]
6. **Decompose a given relation to 3NF / BCNF.** [practical question]
7. **What are anomalies: insertion, deletion, update? How does normalization fix them?**

### Normalization Definition Sheet
- **Normalization**: Process of decomposing relations to eliminate redundancy and anomalies
- **Anomalies**: Insert (can't add without other data), Delete (lose extra data), Update (must update multiple rows)
- **1NF**: All attributes atomic, no repeating groups
- **2NF**: 1NF + no partial dependencies (non-key depends on part of composite key)
- **3NF**: 2NF + no transitive dependencies (non-key → non-key)
- **BCNF**: Every determinant is a super key (stricter than 3NF)
- **4NF**: No multivalued dependencies
- **FD decomposition rules**: lossless join + dependency preservation

---

## UNIT-5: Transactions, Concurrency Control & Recovery

### Questions (SECOND HIGHEST FREQUENCY)
1. **Explain ACID properties with examples.** [frequent]
2. **What is serializability? Explain conflict serializable and view serializable.** [2016, 2020]
3. **What is a precedence graph? How do you use it for serializability testing?** [frequent]
4. **Explain Two-Phase Locking (2PL).** [2013, 2021]
5. **What is a deadlock? How can it be prevented?** [2009, 2015]
6. **What is timestamp-based concurrency control?** [2018]
7. **Explain transaction recovery: log-based recovery, checkpoints, ARIES.** [2017, 2022]
8. **What is a schedule? What is conflict equivalence?** [frequent]
9. **Write short note on: strict 2PL, rigorous 2PL, cascading abort.**

### Key One-Liners
- Serial schedule: transactions execute one after another, no interleaving
- Parallel schedule: transactions interleaved
- Conflict: two operations on same data item, at least one is write
- RW, WR, WW = conflicts. RR = no conflict
- Precedence graph: T1 → T2 if T1 has conflicting op before T2's on same data
- Cycle = not serializable
- 2PL: growing phase (acquire locks) + shrinking phase (release locks, no new acquires)
- Strict 2PL: holds all locks until commit
- Deadlock: wait-for graph cycle. Prevention: pre-emption or ordering

---

## UNIT-6: File Organization, Indexing & Storage

### Questions
1. **Explain B+ Tree index. Why is B+ Tree preferred over B-Tree for DBMS?** [frequent]
2. **What is hashing? Explain static vs dynamic hashing.** [2013, 2019]
3. **What is ISAM?** [2015]
4. **Explain file organization: heap, sorted, hashed.** [2017]
5. **What is the difference between dense and sparse index?** [2011, 2018]
6. **What is clustering index?** [2020]
7. **Write short note on: RAID levels, buffer management.**

### Key One-Liners
- B+ Tree: data pointers ONLY at leaf nodes → range queries efficient, smaller height
- B-Tree: data pointers at every node
- Hashing: O(1) equality search, fails for range queries
- Dense index: one index entry per record. Sparse: one per block/page
- Clustering index: data physically ordered by index key (only one per table)
- Heap file: unsorted, no order, insert easy, search slow

---

## UNIT-7: Query Optimization & Advanced Topics

### Questions
1. **What is query optimization? Explain heuristic vs cost-based optimization.** [2016, 2022]
2. **Explain RAID levels (0, 1, 5, 10).** [2019]
3. **Write short note on data warehouse, OLAP, data mining.** [2015, 2020]
4. **What is a trigger? Explain with syntax.** [2018]
5. **What are NoSQL databases? Why are they needed?** [2021]

---

## HIGHEST FREQUENCY TOPICS (by OCR keyword count)

| Topic | Occurrences | Priority |
|-------|-------------|----------|
| Index | 182 | CRITICAL |
| Transaction | 169 | CRITICAL |
| Log | 97 | HIGH |
| SELECT (SQL) | 65 | HIGH |
| BCNF | 64 | HIGH |
| Recovery | 60 | HIGH |

**Study order for maximum marks:**
1. Normalization (Unit 4) — asked every single year
2. ACID + Transactions + Concurrency (Unit 5) — second most frequent
3. Indexing + File Organization (Unit 6) — third
4. SQL (Unit 3) — practical, write-blind
5. ER → Relational (Unit 2) — conceptual + diagram
6. Architecture (Unit 1) — theory, short answers
7. Query Optimization (Unit 7) — lower priority

---

## 5-DAY DBMS CRAM RECOMMENDATION

**DAY 1 (4 hours):** Normalization drill + ACID
- Memorize all normal forms with examples
- Write 5 table decompositions from scratch
- ACID properties with transfer-of-funds example

**DAY 2 (4 hours):** Transactions + Concurrency
- Serializability, precedence graphs, draw 3 example schedules
- 2PL variants, deadlock
- Recovery: log-based, checkpoints

**DAY 3 (4 hours):** Indexing + File Organization
- B+ Tree structure and why it dominates DBMS
- All index types compared
- File organizations

**DAY 4 (3 hours):** SQL + Relational Model
- Write all 3 code snippets blind (linked list reverse, cycle, Nth salary)
- Relational algebra operators
- ER → relational conversion

**DAY 5 (2 hours):** Architecture + remaining topics
- Three-schema, DBA roles
- Query optimization basics
- Quick scan Unit 7
