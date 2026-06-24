# Distributed DBMS — Structured Study Notes from Organizer

## Overview
- Source: `/home/bigfoot/SEM-6-CSE/BOOKS/ORGANIZERS/Distributed DBMS_23.pdf`
- Raw OCR: `/home/bigfoot/SEM-6-CSE/study_notes/ddbms_organizer_raw.txt` (2,237 lines)
- 48 pages, 6 chapters per TOC

---

## Chapter Map
1. Introduction (DDP, DDBMS definition, architecture, transparencies)
2. Distributed Database Design (fragmentation, allocation, semantics)
3. Distributed Query Optimization (semi-join, cost models, heuristics)
4. Transaction Management & Concurrency Control (2PC, locking, deadlock, recovery)
5. Parallel Database Systems (architectures, parallel query)
6. Advanced Topics (mobile, distributed objects, multi-databases)

---

## Key Questions & Line References

### Introduction & DDP
- `L94`: What is Distributed Data Processing (DDP)? [MODEL]
  - Answer at `L97-110`: Centralized vs Decentralized DDP, types
- `L142`: Write advantages and disadvantages of DDBMS. [MODEL]
  - Answer at `L144-162` (advantages: modular growth, reliability, lower comms cost, better response)
- `L225`: What is Distributed Database system? Explain [MODEL]
  - Answer at `L227-250`: collection of multiple interconnected databases, features (location independency, distributed query, distributed transaction, seamless integration, network linking, transaction processing)
- `L201`: What are fragmentation, replication and location transparencies? [MODEL]
  - Answer at `L204-217`
- `L251`: What is transparency? Discuss network transparency and replication transparency. [MODEL]
  - Answer at `L253-293`
- `L344`: Write short notes on: Transparency, Heterogeneous databases [MODEL]

### DDBMS Architecture & Design
- `L38`: Global Schema / Fragmentation Schema / Allocation Schema reside in? [MODEL MCQ]
  - Answer: (b) the system virtually
- `L217`: Describe reference architecture of DDBMS. [MODEL]
  - Answer at `L222-340`: includes ANSI-SPARC 3-level, global schema, fragmentation schema, allocation schema, site independence, top-down vs bottom-up
- `L295`: Draw ANSI/SPARC reference architecture and discuss site-independent schemas. [MODEL]
  - Answer at `L305-308`: External, Conceptual, Internal levels — DBA works at conceptual, 4 global view, independent of hardware
- `L298`: Show replicated copy allocation diagram. [MODEL]
  - Answer at `L321-340` (diagram text)
- `L299`: When is Bottom-up preferable over Top-down? [MODEL]
  - Answer at `L310-351`: Bottom-up when existing databases exist; easier for horizontally fragmented relations; top-down for scratch/homogeneous
- `L302`: Explain remote access via auxiliary program in heterogeneous DDBMS with diagram. [MODEL]
  - Answer at `L321-340`

### Fragmentation
- `L446`: What is data replication? Explain with example. [MODEL]
- `L471`: What is data fragmentation? [MODEL]
  - Answer at derivation text
- `L498`: What is fragmentation predicate? [MODEL]
- `L524`: What is partial union? [MODEL]

### Query Optimization
- `L1095`: What are the different layers/steps of query processing? [MODEL]
- `L1379`: Draw canonical tree and transform to optimized tree. [MODEL]

### Concurrency, Transactions, Recovery
- `L585`: What is the level of transparency of the above transaction and why? [MODEL]
- `L747`: How is deadlock determination performed in distributed system? [MODEL MCQ]
  - Answer: (a) Distributed wait-for graph
- `L750`: What is replica control protocol? [MODEL MCQ]
- `L754`: Which is NOT a phase of optimistic method for distributed concurrency control? [MODEL MCQ]
- `L755`: Which is a ROWA protocol? [MODEL MCQ]
- `L760`: Which operation is conflicting? [MODEL MCQ]
  - Answer: (d) All of these
- `L769`: A semi-join is which of the following? [MODEL MCQ]
- `L821`: What is Timestamp protocol in relation to distributed database system? [MODEL]
- `L893`: Show the correctness of fragmentation... [MODEL]
- `L1024`: Explain deadlock prevention vs deadlock detection. [MODEL]
- `L1584`: Which failure does NOT occur in distributed system? [MODEL MCQ]
- `L1625`: What happens if coordinator fails during commit protocol? [MODEL]
- `L1758`: Explain phases of 2PC. [MODEL]
- `L1931`: What if cohort fails before ack during 2PC? [MODEL]
- `L1953`: What are the uses of catalogs in DDBMS? What are contents of catalog? [MODEL]
- `L2002`: How is network partitioning handled in replicated databases? [MODEL]

---

## Short Notes (from L344, L1424, L2209)
- Transparency
- Heterogeneous databases
- Replication
- Fragmentation
- Semi-join
- Deadlock prevention vs detection
- 2PC phases
- Catalog contents

---

## MCQs Summary
- Top-down design applicable when: building from scratch
- Bottom-up when: aggregating existing databases
- Data dictionary tells DBMS: what files, attributes, contents
- Unit of data transfer to/from disk: pages
- DDBMS feature: network transparency (not OS/DBMS/hardware)
- Homogeneous autonomous: same DBMS, each works independently, central coordinates
- Heterogeneous: different DBMS at each node
- Fragmentation transparency cannot be achieved: FALSE (it can)
- Fragmentation transparency is highest level
- Clustering: keeping common data in one place
- Derived horizontal fragmentation based on another relation's fragmentation
- Vertical fragmentation conditions: disjointness, completeness, reconstruction (NOT rebuild)
- Replication: when fast response and hardware resilience needed
- Allocation problem easier in: redundant/replicated system

---

## Study Priority for 48 pages (target: 6-8 hrs)

1. **Introduction / DDP / Definitions** (L94-L142) — 30 min
2. **Transparencies & Architecture** (L201-L340) — 60 min
3. **Fragmentation & Allocation** (L344-L524) — 45 min
4. **Concurrency / 2PC / Recovery** (L585-L2002) — 90 min
5. **Query Optimization** (L1095-L1379) — 45 min
6. **Parallel & Advanced** (skim only) — 20 min

**Total: ~4.5 hrs core + 1 hr short notes = 5.5 hrs**

 organizes by PYQ frequency: Intro/Transparencies dominate; Query Opt is medium; Parallel is low-yield.

---

## Key Formulas & Concepts to Write Down
- Semi-join: R ⋉ S = π_R(σ_{condition}(R × S)) — then send projection back
- 2PC phases: Prepare → Commit/Abort
- Fragmentation: Horizontal (predicate), Vertical (attributes), Mixed
- Fragmentation conditions: Disjointness, Completeness, Reconstruction
- Transparency hierarchy: Fragmentation > Location > Local Mapping > Naming (high to low)
