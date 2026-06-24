======================================================================
DBMS HIGH-FREQUENCY PYQ STUDY GUIDE (Remaining Topics)
======================================================================
Topics: ACID | 2PL | Recovery | B-tree/B+tree | Indexing | Armstrong's | ER Model
PYQ years: 2006-2019 compiled from organizer raw OCR
======================================================================

======================================================================
1. ACID PROPERTIES
======================================================================

Asked: WBUT 2007, 2009, 2013, 2015, 2016, 2017, 2019

A - Atomicity:
  Transaction is either performed in its entirety or not performed at all.
  Guaranteed using: logging, shadowing, distributed commit.

C - Consistency (Preservation):
  Complete execution of a transaction takes the database from one consistent
  state to another. Guaranteed by the application correctly marking transaction
  boundaries.

I - Isolation:
  Execution of a transaction is not interfered with by any other concurrent
  transactions. Updates are not visible to other transactions until completed.
  Guaranteed through locking or timestamp-based concurrency control.

D - Durability (Permanency):
  Changes applied by a committed transaction must persist even if the system
  crashes before all changes are reflected in stable storage.

MCQ: "Which is not an ACID property?" [WBUT 2012]
  Answer: Integrity (the four are Atomicity, Consistency, Isolation, Durability)

----------------------------------------------------------------------
2. TWO-PHASE LOCKING (2PL)
----------------------------------------------------------------------

Asked: WBUT 2008, 2012, 2015, 2017, 2018

Protocol divides transaction execution into TWO consecutive phases:

1. Growing phase (Expanding):
   - Transaction acquires locks
   - No locks are released
   - Number of locks can only increase

2. Shrinking phase:
   - Transaction releases locks
   - No new locks are acquired
   - Once first lock is released, phase-2 starts

Why it guarantees serializability:
  - All transactions follow the same access order determined by lock acquisition
  - The schedule class of all 2PL-compliant transactions is conflict-serializable
  - No cyclic wait can occur

STRICT 2PL (SS2PL):
  - Transaction holds ALL exclusive write locks until COMMIT
  - Prevents cascading rollbacks
  - All real DBMS products use this variant

Lock types:
  - Shared (S): for reading, multiple transactions can hold S lock simultaneously
  - Exclusive (X): for writing, only one transaction can hold X lock
  - To write: must acquire S lock first, then upgrade to X lock

MCQ: "In 2PL, a transaction must:" [WBUT 2006,2007,2008,2019]
  Answer: NOT obtain any new locks once it has started releasing locks

MCQ: "Which phase is NOT part of 2PL?" [WBUT 2012]
  Answer: Stabilization phase

----------------------------------------------------------------------
3. LOG-BASED RECOVERY + CHECKPOINTS
----------------------------------------------------------------------

Asked: WBUT 2010, 2014, 2016, 2017, 2018, 2019

CORE PRINCIPLE: Log of each transaction maintained in stable storage BEFORE
the actual transaction is applied to the database.

LOG CONTENTS:
  - Which transaction is executing
  - Which values were modified and what they changed to
  - State of the transaction (running, committed, aborted)
  - Stored in order of execution = Write-Ahead Logging (WAL)

--------------------------------------------------------------
A) IMMEDIATE UPDATE (UNDO/REDO)
--------------------------------------------------------------
  - Changes written to database DURING transaction execution
  - Original AND new data must be in log BEFORE writing to database disk

  On COMMIT:
    1. Flush all unrecorded updates to log, then to disk
    2. Write new data to database

  On ABORT:
    - UNDO all changes using log entries (REDO the database state)

  On SYSTEM RESTART after failure:
    - REDO committed changes from log
    - Ignore uncommitted transactions

--------------------------------------------------------------
B) DEFERRED UPDATE (NO-UNDO/REDO)
--------------------------------------------------------------
  - NO database changes while transaction is running
  - All changes recorded only in log

  On COMMIT:
    1. Write new data to log and flush to disk
    2. THEN write to database

  On ABORT:
    - Do nothing (database was never changed)

  On SYSTEM RESTART:
    - REDO the log (only committed transactions appear)

--------------------------------------------------------------
CHECKPOINTS
--------------------------------------------------------------
  - Acts as a "bookmark" in the log
  - At checkpoint: all transactions completed so far are written to database,
    log entries up to that point are removed
  - After checkpoint: new log entries continue

  Recovery with checkpoints:
    1. Start from the last checkpoint
    2. REDO all committed transactions after checkpoint
    3. Ignore uncommitted ones

  KEY RULE: Create checkpoint only when all active transactions are complete
  or when database is in consistent state. Never during active transaction work.

--------------------------------------------------------------
FAILURE HANDLING SEQUENCE
--------------------------------------------------------------
  - If disks physically/logically damaged -> restore from dump
  - If disks OK but writes interrupted:
      1. Parse log file
      2. For COMMIT entries: apply REDO (rollforward)
      3. For non-COMMIT entries: do nothing
      4. Flush data to disk
      5. Truncate log to zero

----------------------------------------------------------------------
4. B-TREE vs B+TREE
----------------------------------------------------------------------

Asked: WBUT 2008, 2011, 2016

B-TREE (order m = m-way tree):
  - Non-leaf node: (m-1) keys, m children
  - ALL leaves at SAME level
  - Non-leaf nodes (except root) have >= ceil(m/2) children
  - Root has 2 to m children
  - Leaf node: contains keys, no children
  - m must be ODD

KEY DIFFERENCE:
  B-tree:
    - Keys appear in BOTH leaf AND non-leaf nodes
    - Non-leaf keys act as separators
    - -> Less storage space
    - -> Search may stop at non-leaf level

  B+tree:
    - Keys appear in leaf nodes AND as separators in non-leaf nodes
    (non-leaf keys are duplicates of leaf keys, just for routing)
    - -> ALL data in leaves
    - -> Search always reaches leaf level
    - -> Range queries faster (linked list of leaves)
    - -> More storage space

B+TREE FILE ORGANIZATION (used as file org, not just index):
  1. Leaf nodes store complete RECORDS (not just pointers)
  2. Leaf nodes must be at least half full
  3. Insert/delete same as B+tree index
  4. Space utilization critical — involve more siblings in redistribution:
     - 1 sibling  -> guarantees 50% space use
     - 2 siblings -> guarantees 2/3 space use

BLOCKING FACTOR: floor(B / R)  where B = block size, R = record size
  Number of records that fit in one disk block.

----------------------------------------------------------------------
5. INDEXING TYPES
----------------------------------------------------------------------

Asked: WBUT 2006, 2011, 2013, 2018

--------------------------------------------------------------
PRIMARY INDEX
--------------------------------------------------------------
  - Search key = sequential order of the file (ordered file required)
  - Exactly ONE primary index per file
  - Can be DENSE or SPARSE

SECONDARY INDEX:
  - Search key specifies order DIFFERENT from file's sequence
  - Also called NON-CLUSTERING index
  - Multiple can exist per file

CLUSTERING INDEX:
  - Records physically ordered on a NON-KEY field (clustering field)
  - One per file
  - Speeds up retrieval of records with same field value

--------------------------------------------------------------
DENSE vs SPARSE INDEX
--------------------------------------------------------------
DENSE:
  - Index record for EVERY search-key value
  - More storage, faster lookup
  - Used with: secondary indexes, clustering indexes

SPARSE:
  - Index record for only SOME search-key values
  - Only for clustering/primary indexes (ordered files)
  - Less storage, less maintenance
  - Slower: find largest index key <= K, then scan file sequentially

----------------------------------------------------------------------
6. ARMSTRONG'S AXIOMS
----------------------------------------------------------------------

Asked: WBUT 2008, 2009, 2010, 2012, 2017, 2018

Sound inference rules for functional dependencies:

1. REFLEXIVITY:
   If Y is a subset of X, then X -> Y
   Example: A -> BC implies A -> B

2. AUGMENTATION:
   If X -> Y, then XZ -> YZ for any Z
   Example: If A -> B, then AC -> BC

3. TRANSITIVITY:
   If X -> Y and Y -> Z, then X -> Z
   Example: If A -> B and B -> C, then A -> C

DERIVED RULES:

4. UNION (Additivity):
   If X -> Y and X -> Z, then X -> YZ

5. DECOMPOSITION (Projectivity):
   If X -> YZ, then X -> Y and X -> Z

6. PSEUDO-TRANSITIVITY:
   If X -> Y and WY -> Z, then XW -> Z

======================================================================
7. ER MODEL  <-- NEW
======================================================================

Asked: WBUT 2006, 2009, 2010, 2011, 2012, 2013, 2015, 2017, 2019
Frequency: ~60% of years — MUST KNOW

----------------------------------------------------------------------
A) WEAK vs STRONG ENTITY SET
----------------------------------------------------------------------

Asked: WBUT 2006, 2010, 2016, 2019

STRONG ENTITY SET:
  - Has its own primary key (sufficient attributes)
  - Existence does NOT depend on another entity
  - Represented in ER diagram: SINGLE outlined rectangle

WEAK ENTITY SET:
  - Does NOT have sufficient attributes to form a primary key
  - Existence depends on another (strong) entity
  - Primary key formed from: primary key of strong entity + partial key (discriminator)
  - Represented in ER diagram: DOUBLE outlined rectangle
  - Connected to strong entity by a " Identifying Relationship" (doubled diamond)

EXAMPLE (from WBUT answer):
  - Flight     -> Strong entity
  - Departures -> Weak entity (depends on Flight, only has 'date' attribute;
    same date can be shared by multiple flights)
  - Primary key of Departures = {flight_no, date}

COMPARISON TABLE:
  +------------------------+------------------------+------------------------+
  | Feature                | Strong Entity          | Weak Entity            |
  +------------------------+------------------------+------------------------+
  | Has primary key?       | Yes                    | No (needs owner key)   |
  | Depends on other?      | No                     | Yes                    |
  | ER diagram symbol      | Single rectangle       | Double rectangle       |
  | Key composition        | Own attributes         | Owner key + discriminator|
  +------------------------+------------------------+------------------------+

----------------------------------------------------------------------
B) CARDINALITY RATIO
----------------------------------------------------------------------

Asked: WBUT 2013, 2017

Defines the maximum number of objects that can participate in a relationship.

THREE types:

1:1 (One-to-One):
  One object can relate to only one other object
  Example: One employee has one parking slot

1:N (One-to-Many):
  One object can relate to many objects
  Example: One department has many employees

M:N (Many-to-Many):
  Some number of occurrences of one entity can relate to some number of
  occurrences of another entity
  Example: Students enroll in many courses; each course has many students

NOTE: Cardinality defines "maximum" participation. It does NOT define whether
participation is mandatory or optional — that's determined by MODALITY.

----------------------------------------------------------------------
C) DEGREE OF RELATIONSHIP
----------------------------------------------------------------------

Asked: WBUT 2015

The number of entity sets participating in a relationship.

TYPES:
  Unary   (degree 1)   : Employee manages Employee (self-referencing)
  Binary  (degree 2)   : Employee works_for Department (most common)
  Ternary (degree 3)   : Supplier supplies Part to Project

----------------------------------------------------------------------
D) ATTRIBUTE TYPES
----------------------------------------------------------------------

Asked: WBUT 2017

Single-valued:      One value per entity (age, roll number)
Multi-valued:       Multiple values per entity (phone numbers, colors of a car)
Composite:          Can be subdivided into smaller attributes with independent
                    meaning. Example: street-address = {house_no, street, city,
                    state, zip}
Derived:            Not stored; computed from other attributes. Example: age =
                    current_date - date_of_birth

----------------------------------------------------------------------
E) SPECIALIZATION / GENERALIZATION
----------------------------------------------------------------------

Asked: WBUT 2010, 2011

SPECIALIZATION (Top-down):
  Start with a higher-level entity set, create lower-level subclasses
  Example: Vehicle -> Car, Bus, Motorcycle

GENERALIZATION (Bottom-up):
  Start with lower-level entity sets, create a higher-level entity set
  Example: Car + Bus + Motorcycle -> Vehicle

Hierarchy example (WBUT 2010/11 answer):
  Motor vehicle (top level)
    -Commercial vehicle (subclass)
      - Bus (passenger capacity)
      - Van (max load capacity)
    -Non-commercial vehicle (subclass)
      - Car (type: sports/sedan/wagon)
      - Motorcycle
  Shared attributes at top: model, sales-tax-rate, sales-volume
  Shared attributes per subclass: passenger capacity (commercial), luxury
  vehicle tax rate (non-commercial), type (car only)

DISJOINT CONSTRAINT:
  Subclasses cannot overlap. No object may occur in more than one subclass
  Example: Employees and Customers declared disjoint -> cannot be both

----------------------------------------------------------------------
F) ER DIAGRAM INTERPRETATION
----------------------------------------------------------------------

Asked: WBUT 2009, 2011, 2012, 2016

ER diagram can be viewed as a graph. In terms of graph theory:

  - DISCONNECTED graph:
    If no pair of entity sets is connected by a path, the ER diagram is
    disconnected. Each disconnected component is independent.

  - CYCLIC graph:
    If there is a path from an entity set to itself, the graph is cyclic.
    Cycles can indicate recursive relationships (e.g., Employee manages Employee).

======================================================================
8. ADDITIONAL SHORT NOTES
======================================================================

THETA JOIN [WBUT 2009]:
  Extension of natural join that allows a predicate on attributes in R ∪ S.
  r ⋈θ s = σθ(r × s)
  Combines selection + Cartesian product in one operation.

DATA DICTIONARY [WBUT 2013, 2015, 2017, 2019]:
  Centralized repository of information about data.
  Five sections: data elements, data flows, data stores, processes, external entities.
  Contains: data type, data name, aliases, description, characteristics, composition.

TRIGGER (self-triggering = Cascading trigger) [WBUT 2014, 2017]:
  Procedure that automatically executes in response to certain events on a table.

======================================================================
PYQ ANSWER QUICK-REFERENCE (by year)
======================================================================

WBUT 2006:  Weak vs strong entity
WBUT 2007:  ACID properties
WBUT 2008:  2PL / Armstrong's Axioms
WBUT 2009:  "BCNF is stricter than 3NF" example / Theta join / Armstrong's
WBUT 2010:  BCNF decomposition (PLANE_INFO) / B-tree vs B+tree / Armstrong's
WBUT 2011:  Dense vs sparse indexing / Specialization / Lossless join matrix / B+tree construction
WBUT 2012:  ER diagram symbol MCQ / Cardinality (table) / BCNF definition / Crow's-foot
WBUT 2013:  Cardinality ratio / Disjoint constraint / Data dictionary / Closure
WBUT 2014:  Decomposition properties / 2PL vs Timestamp / Locking vs timestamp
WBUT 2015:  ACID / 2PL / Degree of relationship / Derived attribute / Block factor / B+tree (WBUT 2015)
WBUT 2016:  1NF-2NF-3NF MCQ / Weak entity / B+tree / 2PL / Log recovery + checkpoints
WBUT 2017:  Cardinality ratio / Data dictionary / DBA role / Attribute types / Trigger type
WBUT 2018:  2PL protocols / Armstrong's / Primary/secondary index / Ordered index / DBA role
WBUT 2019:  ACID / BCNF definition / Strong vs weak entity set / 2PL vs Timestamp / Data dictionary

======================================================================
STUDY SEQUENCE (remaining 10 days)
======================================================================

DAY 1 (today):   Normalization practice problems
DAY 2 (June 16): ACID + 2PL + Recovery (Unit 5)       [2-3 hours]
DAY 3 (June 17): B+tree + Indexing (Unit 6)            [1.5 hours]
DAY 4 (June 18): ER Model + Armstrong's + Short notes   [1.5 hours]
DAY 5 (June 19): DBMS full PYQ timed run (self-test)
DAY 5+:          Switch to CN extraction + study

======================================================================
EXAM MARK COVERAGE
======================================================================
Total marks these topics cover across all WBUT papers: ~35-40 marks minimum
(57% of a 70-mark paper — and we haven't even touched SQL/relational algebra,
which is another 10-15 marks of low-effort textbook answers)
======================================================================
