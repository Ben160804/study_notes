# Computer Networks — Abbreviation Reference

Extracted from: PCC-CS602 final guide  
Source file: /home/bigfoot/SEM-6-CSE/study_notes/cn_final_guide.md

---

## Unit 1 — Data Communication & Link Layer

| Abbreviation | Full Form | Short Definition |
|--------------|-----------|-------------------|
| NRZ-L | Non-Return-to-Zero Level | Binary encoding: 1 = high, 0 = low; no clock recovery |
| NRZ-I | Non-Return-to-Zero Inverted | Binary encoding: change of signal = 1, no change = 0 |
| FDM | Frequency Division Multiplexing | Analog multiplexing; each signal on separate frequency band; guard bands between channels |
| TDM | Time Division Multiplexing | Digital multiplexing; each signal gets fixed/recurring time slot |
| WDM | Wavelength Division Multiplexing | Multiple light wavelengths over a single fiber; basis of DWDM |
| DSSS | Direct Sequence Spread Spectrum | Spreads each data bit over wide band using chipping code; resists jamming |
| FHSS | Frequency-Hopping Spread Spectrum | Rapidly changes carrier frequency in pseudorandom sequence; 1 MHz hops |
| LAN | Local Area Network | Private network within a building/campus |
| WLAN | Wireless LAN | LAN using radio; IEEE 802.11; CSMA/CA |
| VLAN | Virtual LAN | Logical partition of a physical LAN into broadcast domains; 802.1Q tagging |
| MAC | Media Access Control | Data-link sublayer; handles framing, addressing, access control (MAC address) |
| OSI | Open Systems Interconnection | 7-layer reference model for network communication |
| CSMA/CD | Carrier Sense Multiple Access / Collision Detection | Wired Ethernet MAC protocol; listen before talk, detect collision, binary exponential backoff |
| CSMA/CA | Carrier Sense Multiple Access / Collision Avoidance | WLAN MAC protocol; listen before talk + RTS/CTS + ACK + NAV |
| RTS | Request to Send | Optional WLAN handshake frame reserving channel |
| CTS | Clear to Send | WLAN response to RTS; grants channel access |
| NAV | Network Allocation Vector | WLAN timer telling station when medium will be busy |
| HDLC | High-Level Data Link Control | Bit-oriented, synchronous, full-duplex data-link protocol |
| CRC | Cyclic Redundancy Check | Polynomial-division error detection; remainder appended as FCS |
| SFD | Start Frame Delimiter | 1-byte field in 802.3 frame marking start of frame after preamble |
| FCS | Frame Check Sequence | CRC field appended to frame for error detection |
| EMI | Electromagnetic Interference | Noise disrupting signal; fiber immune, twisted pair susceptible |
| ALOHA | ALOHAnet random access | Pure/Slotted protocols for shared-medium random access |

---

## Unit 2 — Error Control & Transport

| Abbreviation | Full Form | Short Definition |
|--------------|-----------|-------------------|
| ARQ | Automatic Repeat reQuest | Error control by retransmission after timeout or NACK |
| GBN | Go-Back-N ARQ | Sliding window protocol; retransmit from lost frame forward |
| SR | Selective Repeat ARQ | Sliding window; retransmit only unACKed frames individually |
| ACK | Acknowledgement | Control frame confirming correct receipt of data |
| TCP | Transmission Control Protocol | Connection-oriented, reliable, byte-stream transport protocol |
| UDP | User Datagram Protocol | Connectionless, unreliable, low-overhead transport protocol |
| SCTP | Stream Control Transmission Protocol | Message-oriented transport; multi-homing, multi-streaming, 4-way handshake |
| QoS | Quality of Service | Network performance attributes: reliability, delay, jitter, bandwidth |
| ISP | Internet Service Provider | Organization providing Internet access to end users |
| ISN | Initial Sequence Number | Random starting sequence number chosen in TCP 3-way handshake |
| PSH | Push | TCP flag requesting immediate delivery to application |
| RST | Reset | TCP flag for immediate connection abort |
| URG | Urgent | TCP flag marking urgent data in segment |
| FIN | Finish | TCP flag initiating connection teardown |
| SYN | Synchronize | TCP flag initiating connection establishment |
| DORA | DHCP Discover-Offer-Request-Acknowledge | Four-step DHCP lease process |
| KDC | Key Distribution Center |Trusted authority in Kerberos authentication; issues tickets |

---

## Unit 3 — Network Layer

| Abbreviation | Full Form | Short Definition |
|--------------|-----------|-------------------|
| IP | Internet Protocol | Network-layer protocol; best-effort, connectionless datagram delivery |
| IPv4 | Internet Protocol version 4 | 32-bit addresses; header includes checksum; dominant today |
| IPv6 | Internet Protocol version 6 | 128-bit addresses; no header checksum; extension headers; autoconfiguration |
| ICMP | Internet Control Message Protocol | Error reporting and diagnostics for IP; used by ping and traceroute |
| NDP | Neighbor Discovery Protocol | IPv6 protocol for address autoconfiguration and neighbor resolution; replaces ARP |
| CIDR | Classless Inter-Domain Routing | Slash-notation addressing; eliminates class boundaries; enables route aggregation |
| VLSM | Variable Length Subnet Mask | Subnetting with different mask sizes per subnet for efficient allocation |
| ARP | Address Resolution Protocol | Maps IPv4 address to MAC address; broadcast request, unicast reply |
| RARP | Reverse Address Resolution Protocol | Maps MAC address to IPv4; diskless workstations; largely obsolete |
| BOOTP | Bootstrap Protocol | Diskless workstation boot configuration; static database; predecessor to DHCP |
| DHCP | Dynamic Host Configuration Protocol | Dynamically assigns IP + config to hosts; DORA process |
| MTU | Maximum Transmission Unit | Largest frame/packet size a link-layer technology can carry |
| RIP | Routing Information Protocol | Distance-vector IGP; UDP 520; hop-count metric; max hop = 16 |
| OSPF | Open Shortest Path First | Link-state IGP; Dijkstra SPF; hierarchical areas; no hop-count limit |
| BGP | Border Gateway Protocol | Path-vector inter-AS routing protocol; TCP 179; eBGP vs iBGP |
| AS | Autonomous System | Group of networks under single administrative control; identified by ASN |
| IGP | Interior Gateway Protocol | Routing protocol operating within an AS (RIP, OSPF) |
| EGP | Exterior Gateway Protocol | Routing protocol operating between ASes (BGP) |
| LSA | Link-State Advertisement | OSPF packet flooding topology information to all routers in area |
| SPF | Shortest Path First | Dijkstra algorithm used by link-state routing to compute least-cost paths |

---

## Unit 4 — Transport Layer

| Abbreviation | Full Form | Short Definition |
|--------------|-----------|-------------------|
| TCP | Transmission Control Protocol | Reliable, connection-oriented, byte-stream, 3-way handshake |
| UDP | User Datagram Protocol | Unreliable, connectionless, minimal header, no handshake |
| SCTP | Stream Control Transmission Protocol | Message-oriented; multi-homing, multi-streaming, 4-way cookie handshake |
| QoS | Quality of Service | Network/service performance metrics: delay, jitter, bandwidth, reliability |
| HTTP | Hypertext Transfer Protocol | Stateless request/response application protocol; basis of WWW |
| HTTPS | HTTP Secure | HTTP over TLS/SSL; encrypted web traffic |
| TLS | Transport Layer Security | Cryptographic protocol providing confidentiality/integrity (successor to SSL) |
| SSL | Secure Sockets Layer | Older cryptographic layer; predecessor to TLS |
| DNS | Domain Name System | Hierarchical distributed database mapping domain names to IP addresses |
| DDNS | Dynamic DNS | DNS with automatic record updates when host IP changes |
| FTP | File Transfer Protocol | Application-layer file transfer; separate control (21) and data (20) connections |
| SMTP | Simple Mail Transfer Protocol | Push-based mail transfer; port 25 |
| POP3 | Post Office Protocol v3 | Pull-based mail download; port 110 |
| IMAP | Internet Message Access Protocol | Server-side mail management; port 143 |
| TELNET | TELetypewriter NETwork | Remote login; plaintext; port 23; largely replaced by SSH |
| SNMP | Simple Network Management Protocol | Network monitoring/management; Manager-Agent architecture; port 161 |
| MIB | Management Information Base | Database of managed objects queried by SNMP |
| RFC | Request for Comments | IETF document series defining Internet standards and protocols |
| BER | Bit Error Rate | Ratio of erroneous bits to total transmitted bits |
| BER | Basic Encoding Rules | ASN.1 serialization rules (less common in this syllabus) |
| BER | Block Error Rate | Ratio of errored blocks to total blocks |
| IHL | Internet Header Length | IPv4 header field; header size in 32-bit words |
| TTL | Time To Live | IPv4 hop-limit field; decremented by each router; prevents infinite loops |

---

## Unit 5 — Application Layer & Security

| Abbreviation | Full Form | Short Definition |
|--------------|-----------|-------------------|
| DNS | Domain Name System | Distributed hierarchical name-to-IP database |
| DDNS | Dynamic DNS | Automatic DNS record update on IP change; RFC 2136 |
| TELNET | TELetypewriter NETwork | Plaintext remote terminal; port 23 |
| SMTP | Simple Mail Transfer Protocol | Push-based email transfer; port 25 |
| POP3 | Post Office Protocol v3 | Pull email download to client; port 110 |
| IMAP | Internet Message Access Protocol | Server-side mailbox management; port 143 |
| FTP | File Transfer Protocol | Two-connection file transfer; control(21)/data(20); active vs passive |
| WWW | World Wide Web | Hypertext information space accessed via HTTP |
| HTTP | Hypertext Transfer Protocol | Stateless web request/response protocol |
| HTTPS | HTTP Secure | HTTP over TLS/SSL |
| SNMP | Simple Network Management Protocol | Network device monitoring; Manager-Agent; port 161 |
| MIB | Management Information Base | Structure of managed objects for SNMP |
| PAN | Personal Area Network | Short-range network for personal devices (e.g., Bluetooth) |
| L2CAP | Logical Link Control and Adaptation Protocol | Bluetooth link-layer protocol; multiplexes upper layers |
| SDP | Service Discovery Protocol | Bluetooth protocol for discovering device services |
| RFCOMM | Radio Frequency COMMunication | Bluetooth protocol emulating serial port over RF |
| BNEP | Bluetooth Network Encapsulation Protocol | Bluetooth protocol for IP packet transport |
| DMZ | Demilitarized Zone | Isolated sub-network hosting public-facing services between Internet and internal LAN |
| VPN | Virtual Private Network | Encrypted tunnel over untrusted network; IPsec or SSL/TLS |
| IPsec | IP Security | Network-layer encryption/authentication suite for VPNs |
| AES | Advanced Encryption Standard | Symmetric block cipher; 128/192/256-bit keys; current standard |
| DES | Data Encryption Standard | Symmetric block cipher; 56-bit key; obsolete, replaced by AES |
| RSA | Rivest-Shamir-Adleman | Asymmetric public-key algorithm; encrypt with public, decrypt with private |
| ECC | Elliptic Curve Cryptography | Asymmetric cryptography using elliptic-curve math; smaller keys for same security |
| PGP | Pretty Good Privacy | Combined symmetric+asymmetric encryption for secure email |
| KDC | Key Distribution Center | Trusted third party in Kerberos; issues session tickets |
| SSH | Secure Shell | Encrypted remote login; replaces TELNET |
| TSIG | Transaction SIGnature | DNS authentication mechanism for secure dynamic updates |
| TLS | Transport Layer Security | Cryptographic security layer; successor to SSL |
| SSL | Secure Sockets Layer | Legacy cryptographic layer; predecessor to TLS |
| IEEE | Institute of Electrical and Electronics Engineers | Standards body; 802.x networking standards |

---

## Cross-Unit Index (Quick Lookup)

| Term | Unit(s) |
|------|---------|
| ACK | 2, 4 |
| ARP | 3 |
| ARQ | 2 |
| AS | 3 |
| ALOHA | 1 |
| AES | 5 |
| BGP | 3 |
| BNEP | 5 |
| BOOTP | 3 |
| CRC | 1, 2 |
| CSMA/CD | 1 |
| CSMA/CA | 1 |
| CIDR | 3 |
| DES | 5 |
| DHCP | 3 |
| DMZ | 5 |
| DNS | 5 |
| DDNS | 5 |
| DORA | 3 |
| DSSS | 1 |
| DV | 3 |
| ECC | 5 |
| EGP | 3 |
| FTP | 5 |
| FHSS | 1 |
| FCS | 1 |
| FDM | 1 |
| GBN | 2 |
| HDLC | 1, 2 |
| HTTP | 5 |
| HTTPS | 5 |
| IGP | 3 |
| ICMP | 3 |
| IEEE | 5 |
| IMAP | 5 |
| IP | 3, 4, 5 |
| IPv4 | 3 |
| IPv6 | 3 |
| ISN | 4 |
| IHL | 4 |
| KDC | 5 |
| LAN | 1 |
| L2CAP | 5 |
| LSA | 3 |
| LS | 3 |
| MAC | 1 |
| MIB | 5 |
| MTU | 3 |
| NDP | 3 |
| NAV | 1 |
| NRZ-L | 1 |
| NRZ-I | 1 |
| OSI | 1 |
| OSPF | 3 |
| PAN | 5 |
| PGP | 5 |
| POP3 | 5 |
| PSH | 4 |
| QOS | 4 |
| RFCOMM | 5 |
| RIP | 3 |
| RARP | 3 |
| RSA | 5 |
| RST | 4 |
| RTS | 1 |
| SCTP | 4 |
| SDP | 5 |
| SFD | 1 |
| SMTP | 4, 5 |
| SNMP | 5 |
| SPF | 3 |
| SR | 2 |
| SSL | 5 |
| SYN | 4 |
| TDM | 1 |
| TELNET | 5 |
| TLS | 5 |
| TSIG | 5 |
| TTL | 4 |
| UDP | 4 |
| URG | 4 |
| VLAN | 1 |
| VPN | 5 |
| VLSM | 3 |
| WDM | 1 |
| WLAN | 1 |
| WWW | 5 |

---

Notes:
- Multiple distinct expansions share the same abbreviation when they appear in the same or different units.
- Terms like HTTP, HTTPS, TLS, SSL, SSH, TSIG, KDC are listed because they appear in the guide either by full name or abbreviation in PYQ/text.
- Some entries like BER have multiple possible expansions; the most syllabus-relevant one is listed.
- ISN appears in TCP connection management context.
- IHL appears in IPv4 header context.
