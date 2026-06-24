============================================================
SEM-6 CSE EXAM CRAM NOTES
============================================================

EXAM SCHEDULE:
- June 25: DBMS
- June 29: Computer Networks
- July 1: Distributed DBMS
- July 3: Data Warehousing & Data Mining
- July 6 or 8: Research Methodology

ORGANIZERS:
- DBMS: /home/bigfoot/SEM-6-CSE/BOOKS/ORGANIZERS/DBMS_Organizer_2023.pdf
- CN: /home/bigfoot/SEM-6-CSE/BOOKS/ORGANIZERS/Computer Networks_Organizer_2023.pdf
- DDBMS: /home/bigfoot/SEM-6-CSE/BOOKS/ORGANIZERS/Distributed DBMS_23.pdf
- DWDM: /home/bigfoot/Pictures/wallpaper/nerd/DW & DM_Organizer_2023.pdf

============================================================
DAILY STUDY PLAN (10 days, June 13-22)
============================================================

DAYS 1-2: DBMS
DAYS 3-5: Computer Networks
DAYS 6-7: Distributed DBMS
DAYS 8-9: Data Warehousing & Data Mining
DAY 10: Research Methodology
DAYS 11-12: Buffer + PYQ sprint

============================================================
DBMS — HIGH-YIELD TOPICS (NON-NEGOTIABLE)
============================================================

1. NORMALIZATION
   - 1NF: Atomic values, no repeating groups
   - 2NF: No partial dependencies on composite key
   - 3NF: No transitive dependencies (non-key → non-key)
   - BCNF: Every determinant is a super key
   - Lossless join: common attribute must be super key in at least one table
   - Dependency preservation: all FDs must be enforceable on individual tables

2. ACID PROPERTIES
   - Atomicity: all or nothing
   - Consistency: DB integrity preserved
   - Isolation: concurrent transactions don't interfere
   - Durability: committed data survives crashes (WAL)

3. TRANSACTION SCHEDULING
   - Serial schedule vs parallel schedule
   - Conflict equivalence: no conflicting operations in different order
   - Precedence graph: nodes = transactions, edges = conflicting ops
   - Cycle in precedence graph = not conflict-serializable
   - Conflict serializable ⇔ schedule can be transformed via swap

4. LOCKING & CONCURRENCY
   - Two-phase locking: growing + shrinking phases
   - Rigorous 2PL: holds all locks until commit
   - Deadlock: circular wait, prevention via pre-emption or ordering
   - Deadlock detection: wait-for graph

5. INDEXING
   - B+ Tree: only leaf nodes have data pointers, height small
   - B-Tree: data at every node
   - Hashing: O(1) equality, fails for range queries
   - ISAM: static, fast reads, slow inserts
   - Dense vs Sparse index

6. JOINS
   - Nested loop join, sort-merge join, hash join
   - Cost estimation: relation sizes, index availability

7. SQL (WRITE BLINDLY)
   - Nth highest salary (subquery method, no LIMIT)
   - Find duplicates
   - Self-join examples

8. FILE ORGANIZATION
   - Heap file, sorted file, hashed file
   - Clustering vs non-clustering index
   - Index vs no-index tradeoffs

9. QUERY OPTIMIZATION
   - Heuristic + cost-based optimization
   - Logical vs physical query plan

10. ENTITY-RELATIONSHIP MODEL
    - Entity, attribute, relationship
    - Cardinality: 1:1, 1:N, M:N
    - Weak entity, identifying relationship
    - ER to relational conversion

============================================================
COMPUTER NETWORKS — HIGH-YIELD TOPICS (NON-NEGOTIABLE)
============================================================

1. OSI MODEL (7 layers, top-to-bottom)
   - Application, Presentation, Session, Transport, Network, Data Link, Physical
   - TCP/IP maps: Application (L5-7), Transport (L4), Internet (L3), Network Access (L1-2)

2. TCP vs UDP
   - TCP: connection-oriented, reliable, ordered, 3-way handshake, flow/congestion control
   - UDP: connectionless, unreliable, unordered, no handshake
   - Use TCP for: web, email, files. Use UDP for: DNS, video, gaming, VoIP

3. SUBNETTING (must calculate blind)
   - subnets = 2^n where n = bits borrowed
   - hosts per subnet = 2^(host-bits) - 2
   - CIDR notation
   - Practice: given IP + mask, find network address, broadcast address, valid host range

4. CSMA/CD
   - Listen before transmit
   - Collision detection → jam signal
   - Binary exponential backoff: range doubles each collision up to 1023
   - After 16 collisions, give up

5. ARP
   - ARP request: broadcast "who has IP X?"
   - ARP reply: target responds with MAC
   - Cached in ARP table

6. SWITCHING
   - Hub vs Switch vs Router
   - Collision domain, broadcast domain
   - VLAN: broadcast domain segmentation

7. ROUTING
   - Distance vector vs link state
   - Dijkstra's algorithm (link state)
   - RIP vs OSPF
   - Autonomous systems: IGP vs EGP

8. TRANSPORT LAYER PROTOCOLS
   - TCP: sequence numbers, ACK, sliding window, flow control
   - UDP: header format (src port, dst port, length, checksum)
   - SCTP: multi-streaming, multi-homing
   - TCP congestion control: slow start, congestion avoidance, fast retransmit

9. DNS & DHCP
   - DNS: recursive vs iterative query
   - DHCP: DORA process (Discover, Offer, Request, Acknowledgement)
   - BOOTP vs DHCP

10. APPLICATION LAYER
    - HTTP: methods, status codes, persistent vs non-persistent
    - SMTP, FTP (active vs passive), Telnet vs SSH
    - POP3 vs IMAP

============================================================
DATA STRUCTURES — CODE WRITE-BLIND
============================================================

1. REVERSE LINKED LIST
def reverse(head):
    prev = None
    curr = head
    while curr:
        next_node = curr.next
        curr.next = prev
        prev = curr
        curr = next_node
    return prev

2. CYCLE DETECTION (Floyd's)
def hasCycle(head):
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            return True
    return False

3. NTH HIGHEST SALARY (no LIMIT)
SELECT MAX(Salary) FROM Employee
WHERE Salary < (SELECT MAX(Salary) FROM Employee
WHERE Salary < (SELECT MAX(Salary) FROM Employee));

============================================================
BEHAVIORAL ANSWER TEMPLATES
============================================================

"Tell me about yourself":
"I'm Ootso, B.Tech CSE 2027 batch. Backend-focused with strong fundamentals in databases and
networking — 400+ LeetCode problems. I built a Linux security pipeline that ingests auth logs
and detects brute-force attacks using an LLM. I'm here because I want to work on production
systems involving real-time data processing and security, and grow into a backend engineering
role where I can own services end-to-end."

"Strengths and weaknesses":
Strength: "Problem-solving — evidenced by 400+ LeetCode and a multi-component pipeline project."
Weakness: "I can go too deep on technical details and lose track of time. Now I set explicit
time-boxed goals before any deep work session."

"Why should we hire you":
"Because I already think like an engineer. I don't just write code — I design systems with failure
modes in mind. My project shows I can build end-to-end pipelines, handle edge cases, and make
deliberate technology choices. I'm consistent, I ship, and I learn fast."

============================================================
ORGANIZER EXTRACTION STATUS
============================================================
DBMS Organizer: OCR in progress (scanned PDF, 160 pages)
Extracted text: /home/bigfoot/SEM-6-CSE/study_notes/dbms_organizer_raw.txt
Summaries: will be written to /home/bigfoot/SEM-6-CSE/study_notes/dbms_unit_summaries.md
(extraction started — check back in ~30 minutes)

============================================================
