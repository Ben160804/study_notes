# Computer Networks — Complete Syllabus-Aligned Study Guide

## Syllabus (PCC-CS602, 39L, 5 Units)

| Unit | Hours | Topics | Organizer Coverage | Status |
|------|-------|--------|-------------------|--------|
| **Unit 1** | 9 | Data comm components, topology, OSI model, transmission media, LAN (wired/wireless), VLAN, multiplexing (FDM/TDM/WDM), spread spectrum | Physical Level + Medium Access Sub Layer | ✅ Covered |
| **Unit 2** | 8 | Error detection/correction (block coding, Hamming distance, CRC), Flow/Error Control (Stop-n-Wait, Go-Back-N, Selective Repeat, Sliding Window, Piggybacking), Medium Access: ALOHA, CSMA/CD, CSMA/CA | Data Link Layer + Medium Access Sub Layer | ✅ Covered |
| **Unit 3** | 14 | Switching, Logical addressing IPv4/IPv6, ARP, RARP, BOOTP, DHCP, Delivery, Forwarding, Unicast Routing | Network Layer | ✅ Covered |
| **Unit 4** | 8 | UDP, TCP, **SCTP**, Congestion control, QoS, Leaky Bucket & Token Bucket | Transport Layer | ⚠️ SCTP gap |
| **Unit 5** | 8 | DNS, **DDNS**, TELNET, EMAIL, FTP, WWW, HTTP, SNMP, Bluetooth, Firewalls, Basic Cryptography | Application Layer + Modern Topics | ⚠️ DDNS gap |

**Exam: June 29 | 13 days | ~14 hrs core + 2 hrs gaps = 16 hrs total**

---

## All PYQs Mapped to Syllabus Units

### UNIT 1: Physical Layer & Data Comm (9 hrs)
| Line | Question | Years | Type |
|------|----------|-------|------|
| L1246 | Why bit stuffing is needed in HDLC frame? | 2006, 2010 | Short |
| L1264 | Basic differences between Pure ALOHA and Slotted ALOHA | 2014 | Short |
| L1269 | Flowchart of CSMA/CD protocol | 2009 | Short |
| L1289 | Describe 802.3 header format. Why padding required? | 2012, 2019 ⭐ | Long |
| L1303 | 1 km 10 Mbps CSMA/CD LAN throughput | 2008, 2011, 2012 | Numerical ⭐ |
| L1360 | Differentiate FHSS and DSSS spread spectrum | 2010 | Short |
| L1434 | Discuss CSMA/CA with flowchart | 2012, 2019 | Long |
| L1435 | Why CSMA/CD not in WLAN? | 2012, 2019 | Short |
| L1494 | Compare CSMA/CA with CSMA/CD | 2014, 2016 | Long |
| L1496 | Differentiate CSMA/CD and CSMA/CA | 2018 | Short |
| L1498 | How does CSMA/CD differ from CSMA/CA? | 2018 | Short |

**Must-know:** Bit/Byte stuffing, 802.3 frame format, CSMA/CD vs CSMA/CA, ALOHA efficiency (pure=18%, slotted=37%), FHSS vs DSSS, padding purpose (min frame size for collision detection)

---

### UNIT 2: Data Link Layer — Error/Flow Control + MAC (8 hrs)
| Line | Question | Years | Type |
|------|----------|-------|------|
| L578 | 4-bit sliding window sequence number range | 2008, 2012 | MCQ |
| L623 | Sliding window used for: flow control | 2017 | MCQ |
| L944 | Delayed Acknowledgement | 2015 | Short |
| L1015 | Discuss sliding window with example, HDLC flow control | 2015 | Long |
| L1116 | Compare bit stuffing vs byte stuffing with example | 2017 | Long |
| L1269 | Flowchart of CSMA/CD protocol | 2009 | Short |
| L1588 | CSMA/CD MCQ | 2015 | MCQ |
| L1590 | HDLC MCQ | 2010 | MCQ |

**Must-know:**
- **Stop-and-Wait**: 1 frame, ACK before next
- **Go-Back-N**: Sender window N, receiver window 1, on error retransmit all from lost frame
- **Selective Repeat**: Sender window N, receiver window N, only retransmit lost frame
- **Sliding Window**: Buffer between app and network, TCP uses it
- **HDLC**: Flag (01111110), Address, Control, Data, FCS, Flag; bit stuffing after 5 consecutive 1s
- **Piggybacking**: ACK + data in same frame
- **Delayed ACK**: Wait for data to piggyback ACK

---

### UNIT 3: Network Layer — Addressing & Routing (14 hrs) — HIGHEST WEIGHT
| Line | Question | Years | Type |
|------|----------|-------|------|
| L1695 | Address space of IPv4 | 2011, 2012 | MCQ |
| L1746 | Subnet mask 255.255.255.192 | 2016, 2017 | Numerical |
| L1775 | IP/ARP/ICMP/DHCP protocol function | 2018 | MCQ |
| L1799 | Router B update: 2 hops → 5 hops, what in table? | 2019 | MCQ ⭐ |
| L1804 | Explain Link State Routing | **2007, 2013** ⭐⭐ | Long |
| L1864 | Netid/hostid of IP, subnet mask 255.255.255.224 | 2011, 2013 | Numerical ⭐ |
| L1875 | Compare IPv4 and IPv6 | 2011 | Short |
| L1927 | Advantages of ICMP over IP | 2014, 2018 | Short |
| L2023 | Classful vs classless addressing advantages | 2010, 2013 | Long |
| L2168 | Purpose of subnetting | 2006, 2011 | Short |
| L2200 | Static vs dynamic routing, routing table fields | 2008, 2012 | Long |
| L2277 | Explain Link State Routing | 2010 | Long |
| L2311 | Distance vector routing, RIP vs BGP, infinity=16 | 2010, 2013, 2018 | Long |
| L2378 | Adaptive vs fixed routing | 2010 | Short |
| L2387 | Differentiate Link State vs Distance Vector | 2010, 2013, 2018 ⭐⭐⭐ | Long |
| L2561 | DV update: link cost change, new distance vector at N3 | 2014 | Numerical ⭐ |
| L2569 | RIP routing table update from Router C | 2014 | Numerical ⭐ |
| L2602 | Dijkstra shortest path (node 4→6) | 2018 | Numerical ⭐ |
| L2626 | CIDR notation significance | 2015 | Short |
| L2674 | Class B, mask 255.255.240.0, max hosts/subnet | 2016 | Numerical |

**Must-know (high-yield):**
1. **Link State Routing**: LSDB, flooding, Dijkstra, OSPF/IS-IS — Explain questions (2007, 2010, 2013)
2. **Distance Vector**: RIP, update algorithm, count-to-infinity, infinity=16 — update questions (2014)
3. **Subnetting**: CIDR, VLSM, hosts/subnet formulas — Numerical (2011, 2013, 2016, 2017, 2018)
4. **Routing Table**: NetID, Cost, NextHop, Flags, Interface — Static vs Dynamic (2008, 2012)
5. **IPv4 vs IPv6**: 32 vs 128 bit, header simplification, flow label, security — Compare (2011)
6. **ARP/ICMP**: ARP=IP→MAC, RARP=MAC→IP, ICMP=error reporting, TTL, traceroute
7. **Dijkstra**: Must-show iteration table with d[v], p[v], final path

---

### UNIT 4: Transport Layer (8 hrs)
| Line | Question | Years | Type |
|------|----------|-------|------|
| L1788 | Not part of UDP header: Length | 2019 | MCQ |
| L2798 | TCP sequence numbers purpose, padding | 2019 | Short |
| L2802 | TCP sliding window diagram (window 10000, ACK 22001→24001) | 2019 | Diagram |
| L3289 | Compare TCP and UDP | **2011, 2018, 2019** ⭐⭐⭐ | Long |
| L3291 | Compare TCP with UDP | 2017 | Long |

**Must-know:**
- **TCP vs UDP** (recurring 3 years): Connection-oriented vs connectionless, Reliable vs unreliable, Ordered vs unordered, Heavyweight vs lightweight
- **Sequence Numbers**: Byte stream numbering for reassembly and ACKs, 32-bit field
- **Padding**: Header alignment to 32-bit boundary
- **Congestion Control**: Leaky Bucket (constant rate) vs Token Bucket (burst tolerance) — L3199-L3334
- **SCTP** (syllabus gap): Multi-homing, multi-streaming, message-oriented — 1-2 hrs textbook
- **QoS**: Traffic shaping, scheduling, admission control

---

### UNIT 5: Application Layer (8 hrs)
| Line | Question | Years | Type |
|------|----------|-------|------|
| L1781 | Not silent program in WWW: HTML | 2019 | MCQ |
| L1784 | SOCK_RAW socket uses IP directly | 2019 | MCQ |
| L3195 | Kerberos authentication for digital signature | 2019 | MCQ |
| L3466 | Packet at application layer: message | 2018 | MCQ |
| L3496 | Digital certificates — CA as middleman | — | Short |
| L3701 | Explain RSA algorithm with example | **2014** ⭐ | Long |
| L3764 | Firewall | **2014** | Short |
| L3825 | Firewall types: Packet filter, App gateway, Circuit gateway, Proxy | 2014 | Short |
| L3847 | Digital signature: process, hash + private key, non-repudiation | **2017** | Short |

**Must-know:**
- **RSA**: Key gen (p,q→n, φ, e, d), Encrypt c=m^e mod n, Decrypt m=c^d mod n — Example p=3,q=11,e=7,d=3 (L3747-3756)
- **Digital Signature**: Hash → sign with private key → verify with public key → non-repudiation
- **Firewall**: 4 types (Packet filter, App gateway, Circuit-level, Proxy)
- **Kerberos**: Authentication protocol (MCQ)
- **DDNS** (syllabus gap): Dynamic DNS updates (RFC 2136) — 30 min
- **DNS/TELNET/FTP/HTTP/SNMP**: Basic functions

---

## Unit-wise PYQ Frequency Ranking

| Rank | Topic | PYQ Hits | Recurring Years | Time |
|------|-------|----------|-----------------|------|
| 1 | **Routing (LS + DV)** | 12+ | 2007,2010,2013,2014,2018 | 4 hrs |
| 2 | **Subnetting / CIDR / IPv4-IPv6** | 10+ | 2011,2013,2016,2017,2018 | 3 hrs |
| 3 | **TCP vs UDP** | 5 | 2011,2017,2018,2019 | 1 hr |
| 4 | **CSMA/CD vs CSMA/CA** | 5 | 2009,2012,2014,2016,2018,2019 | 1.5 hrs |
| 5 | **Error/Flow Control (Sliding Window)** | 4 | 2008,2012,2015,2017 | 1.5 hrs |
| 6 | **Security (RSA, Firewall, Digital Sig)** | 4 | 2014,2017,2019 | 1.5 hrs |
| 7 | **Congestion Control (Leaky/Token Bucket)** | 3 | 2007,2012,2018 | 1 hr |
| 8 | **ALOHA / Spread Spectrum** | 2 | 2010,2014 | 0.5 hr |
| 9 | **Application Layer (DNS, etc.)** | 2 | 2018,2019 | 0.5 hr |

---

## Study Plan (13 days to June 29)

| Day | Unit | Topic | Source Lines | Hours |
|-----|------|-------|--------------|-------|
| 1 | 3 | Subnetting & CIDR (all numerical) | L1746, L1864, L2168, L2674, L2585, L2724 | 3 |
| 2 | 3 | Link State Routing (explain + Dijkstra) | L1804, L2277, L2602 | 3 |
| 3 | 3 | Distance Vector (RIP updates, infinity) | L1799, L2311, L2564, L2569 | 2 |
| 4 | 3 | Static vs Dynamic, Routing Table | L2200 | 1 |
| 5 | 2 | Flow/Error Control (Stop-Wait, GBN, SR, Sliding Window) | L1015, L578, L623 | 2 |
| 6 | 2 | HDLC, Bit/Byte Stuffing | L1246, L1116 | 1 |
| 7 | 1 | CSMA/CD vs CSMA/CA, 802.3 header | L1269, L1289, L1434, L1494 | 2 |
| 8 | 1 | ALOHA (pure/slotted), FHSS/DSSS | L1264, L1360 | 1 |
| 9 | 4 | TCP vs UDP, Sequence numbers, Window | L2798, L2802, L3289 | 2 |
| 10 | 4 | Congestion Control (Leaky/Token Bucket) | L3199 | 1 |
| 11 | 4 | **Gap: SCTP** (textbook 1 hr) | — | 1 |
| 12 | 5 | Security (RSA full example, Firewall, Digital Sig) | L3701, L3764, L3847 | 2 |
| 13 | 5 | DNS/TELNET/FTP/HTTP, **Gap: DDNS** | L3199, L3764 | 1 |
| **Buffer** | | Review MCQs, re-do numerical | — | 2 |

**Total: ~24 hrs over 13 days = ~2 hrs/day**

---

## Quick-Reference Formulas & Facts

**Subnetting:**
- Mask 255.255.255.224 → /27 → 5 host bits → 2⁵-2 = 30 hosts/subnet
- Class B + 255.255.240.0 → /20 → 12 host bits → 4094 hosts
- Subnets = 2^(subnet bits beyond class), Hosts = 2^(host bits) - 2

**Routing:**
- RIP infinity = 16 hops, UDP port 520, classful only
- OSPF = Link State, Dijkstra, areas
- BGP = Path Vector, TCP port 179, Inter-AS
- Link State: LSDB flooding → Dijkstra → routing table
- Distance Vector: Bellman-Ford → neighbors share distance vectors

**TCP vs UDP:**
| | TCP | UDP |
|---|-----|-----|
| Connection | Oriented | Less |
| Reliability | Yes (ACK, retransmit) | No |
| Ordering | Guaranteed | No |
| Weight | Heavy | Light |

**Security:**
- RSA: n=pq, φ=(p-1)(q-1), ed≡1 mod φ, c=m^e mod n, m=c^d mod n
- Example: p=3,q=11 → n=33, φ=20, e=7, d=3, m=2 → c=29, m=2
- Firewall: Packet filter, App gateway, Circuit gateway, Proxy
- Digital Sig: Hash → sign(priv) → verify(pub) = non-repudiation

**Congestion:**
- Leaky Bucket: constant rate output, queue = bucket, overflow = drop
- Token Bucket: tokens added at rate, burst = tokens available

---

## Gaps to Fill (Textbook/Notes)
1. **SCTP** (Unit 4): Multi-homing, multi-streaming, 4-way handshake, message boundaries
2. **DDNS** (Unit 5): RFC 2136, dynamic UPDATE, TTL, TSIG authentication
3. **3-way handshake** detail: SYN, SYN-ACK, ACK with ISN
4. **TCP states**: CLOSED → LISTEN → SYN-SENT → SYN-RCVD → ESTABLISHED → FIN-WAIT-1 → CLOSE-WAIT → LAST-ACK → TIME-WAIT → CLOSED

---

## MCQ Drill List (memories)
- Subnet mask 255.255.255.224 → 30 hosts
- 4-bit sliding window → seq 0-15
- Pure ALOHA efficiency → 18%
- Slotted ALOHA efficiency → 37%
- RIP infinity → 16
- RIP port → 520
- Not a mining task → Indexing
- Firewall type → Packet filter / App gateway / Circuit / Proxy
- RSA key size → 1024/2048 bits
- Padding → 32-bit boundary alignment

---
**END OF CN STUDY GUIDE**

All 5 syllabus units covered. PYQs mapped. Gaps identified. Study plan scheduled. Execute.