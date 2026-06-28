# Computer Networks — Unit-Wise Final Revision Guide (PCC-CS602)
Generated: 2026-06-26

---

## [APP] Checklist

**Unit 1**
- [ ] Manchester / Differential Manchester encoding [APP]
- [ ] CRC calculation [APP]
- [ ] ALOHA throughput (pure 18%, slotted 37%) [APP]
- [ ] CSMA/CD collision detection timing [APP]

**Unit 2**
- [ ] Bit stuffing example [APP]
- [ ] Go-Back-N diagram + sliding window [APP]
- [ ] Selective Repeat window diagram [APP]

**Unit 3**
- [ ] Subnetting numericals (CIDR, VLSM, block design) [APP]
- [ ] Classless routing lookup (longest prefix match) [APP]
- [ ] Dijkstra iteration table [APP]
- [ ] Distance vector update iteration (count-to-infinity) [APP]

**Unit 4**
- [ ] TCP header diagram (draw 20 bits) [APP]
- [ ] Leaky Bucket vs Token Bucket timing diagram [APP]
- [ ] TCP vs UDP header field differences [APP]

**Unit 5**
- [ ] RSA encrypt/decrypt numerical example [APP]
- [ ] Firewall block diagram (4 types) [APP]
- [ ] Bluetooth architecture diagram [APP]

---

# Unit 1 (9 hrs)

---

## Data Communication Components

**Depth Notes**
- Core entities: sender, receiver, modem, protocol, transmission medium.
- Modem: modulates digital to analog and demodulates reverse.
- Protocol: set of rules governing data exchange; defines format, timing, sequencing, error handling.
- Medium: guided (twisted pair, coaxial, fiber) and unguided (radio, microwave, satellite).

**PYQs**
- No direct questions in past papers on this alone; tested implicitly in LAN/WLAN and transmission media questions.

---

## Signals, Encoding, and Impairments

**Depth Notes**
- Signal types: analog vs digital; periodic vs non-periodic.
- Encoding: NRZ-L, NRZ-I, Manchester, Differential Manchester (transition at middle for clocking).
- Baud rate vs bit rate: bit rate = baud rate × bits per signal element.
- Impairments: attenuation, distortion, noise (thermal, intermodulation, crosstalk, impulse).
- Performance metrics: throughput (actual vs theoretical), latency (propagation + transmission + queuing), jitter (variation in delay).

**PYQs**
- [2011] (iii) Differential Manchester coding. [WBUT 2011]
- [2014] a) Half the baud rates encoding is used, the bit rate is [WBUT 2014]
- [2011, 2013, 2016] Find the baud rate and bit rate from given encoding and bit duration. [WBUT 2011, 2013, 2016]
- [2017] Signal impairments — naming and classification. [WBUT 2017]

---

## Transmission Media

**Depth Notes**
- Guided: twisted pair (UTP/STP), coaxial cable, optical fiber (single-mode vs multimode).
- Unguided: terrestrial microwave, satellite, radio/IR.
- Coaxial: superior shielding than twisted pair; used in cable internet and old Ethernet.
- Fiber: low loss, high bandwidth, immunity to EMI, no ground loops; fragile and costly.
- Comparative pros/cons: cost, attenuation, bandwidth, susceptibility to EMI, installation difficulty.

**PYQs**
- [2013] Why is coaxial cable superior to twisted pair cable? [WBUT 2013]
- [2015] Twisted Pair Cables — categories and uses. [WBUT 2015]
- [2023] (LA) 7. (a) Discuss the working of Twisted pair cable [7]
- [2023] (LA) 7. (b) What is optical fiber? State the advantages of using optical fiber in computer network. [8]

---

## OSI Reference Model

**Depth Notes**
- 7 layers: Physical, Data Link, Network, Transport, Session, Presentation, Application.
- Layer functions: Physical (bits over medium), Data Link (frames, MAC, error detection), Network (routing, logical addressing), Transport (end-to-end reliability, flow/error control), Session (dialog control, synchronization), Presentation (encryption, compression), Application (user interface).
- TCP/IP vs OSI: TCP/IP has 4 layers (Application, Host-to-Host/Host-to-Network, Internet, Network Access); protocols designed before model; not strictly aligned with OSI layers.
- Importance: layered abstraction, modular design, interoperability.

**PYQs**
- [2023] (SA) 2. Explain the functions of physical layer and Data link layer in brief. [5]
- [2023] (SA) 3. Describe the functions of session layer of the OSI reference model. [5]
- [2025] (LA) 11. (a) ISP address block 190.100.0.0/16 subnetting numerical. [8]

---

## Topology and Switching

**Depth Notes**
- Topologies: Bus, Star, Ring, Mesh (full/partial), Hybrid.
- Mesh with n nodes requires n(n−1)/2 physical links.
- Switching types: Circuit Switching (dedicated path, 3 phases: setup, data transfer, teardown), Packet Switching (statistical multiplexing, store-and-forward), Message Switching.
- Circuit switching: suited for real-time voice; packet switching better for bursty data with no dedicated path.

**PYQs**
- [2018] Where does circuit switching take place? [WBUT 2018]
- [2019] Explain switching? What is multiplexing? [WBUT 2019]
- [2023] (SA) 2. Compare and contrast between Circuit Switching and Packet Switching. [5]
- [2023] (SA) 3. Discuss Mesh topology along with a diagram. [5]
- [2023] (VSA) (V) If there are n nodes, how many physical links in MESH?
- [2023] (LA) 7. (c) Packet visits two routers during transmission — determine [5]

---

## LAN, WLAN, and Connecting Devices

**Depth Notes**
- LAN: private network within a building/campus; Ethernet (IEEE 802.3) dominates wired LANs.
- WLAN: IEEE 802.11; uses radio; CSMA/CA instead of CSMA/CD.
- Connecting devices: Repeater (physical layer, regenerates signals), Hub (physical layer, shared medium), Switch (data link layer, uses MAC table, dedicated collision domain per port), Bridge (data link, connects two LAN segments), Router (network layer, inter-network).
- 802.3 header: Preamble (7 bytes), SFD (1 byte), Destination MAC, Source MAC, Length/Type, Data, Pad, CRC (FCS).
- Padding: added when data < 46 bytes to meet minimum frame size (64 bytes).
- Layer-2 Switch = Switch (operates at Data Link layer).

**PYQs**
- [2008, 2011, 2012] A 1 km 10 Mbps CSMA/CD LAN numerical. [WBUT 2008, 2011, 2012]
- [2012] Describe 802.3 header format. Why padding is required? [WBUT 2012, 2019]
- [2019] Describe 802.3 header format. Why padding is required? [WBUT 2012, 2019]
- [2023] (VSA) (III) Layer-2 Switch is also called ___________
- [2023] (LA) 7. (b) Discuss Bluetooth architecture and protocols. [8]

---

## VLAN and Broadcast Domains

**Depth Notes**
- VLAN: Virtual LAN; switch logically partitions a physical LAN into multiple broadcast domains.
- Limits broadcast traffic, improves security and segmentation.
- Trunk ports carry traffic for multiple VLANs using tagging (IEEE 802.1Q).

**PYQs**
- No direct questions in organizer or 2023–2025 papers.

---

## Multiplexing

**Depth Notes**
- FDM: frequency bands separated; guard bands between channels; analog.
- TDM: time slots; synchronous (fixed slot per source) vs statistical (dynamic allocation); digital.
- WDM: multiple light wavelengths over fiber; basis of dense WDM.
- Spread Spectrum: FHSS (frequency hopped), DSSS (direct sequence); wider bandwidth than needed; resistance to jamming and interception.

**PYQs**
- [2010] Total bandwidth required for AM. [WBUT 2010, 2012]
- [2010] Differentiate between FHSS and DSSS spread spectrum. [WBUT 2010]
- [2023] (VSA) (II) Which multiplexing technique sends each signal to a different carrier frequency?
- [2023] (VSA) (VII) In synchronous TDM, for n signal sources of the same data rate, slots per frame?

---

## ALOHA and Random Access Protocols

**Depth Notes**
- Pure ALOHA: transmits whenever data ready; maximum throughput ≈ 18.4% (S₀ = 0.184); vulnerable time = 2 × T_frame.
- Slotted ALOHA: time slots synchronized; max throughput ≈ 36.8% (S₀ = 0.368); vulnerable time = T_frame.
- CSMA: Carrier Sense Multiple Access — listen before talk. Variants:
  - 1-persistent: always transmit if idle.
  - Non-persistent: waits random time if busy.
  - p-persistent: transmits with probability p if idle.
- CSMA/CD: collision detection; used in wired Ethernet (802.3); jam signal + binary exponential backoff.
- CSMA/CA: collision avoidance; used in WLAN; RTS/CTS optional; ACK required; NAV (Network Allocation Vector).

**PYQs**
- [2014] Differences between pure ALOHA & slotted ALOHA. [WBUT 2014]
- [2014] ALOHA with flowchart. [WBUT 2014]
- [2012] Discuss CSMA/CA with flowchart. [WBUT 2012, 2019]
- [2019] Discuss CSMA/CA with flowchart. [WBUT 2012, 2019]
- [2012, 2014, 2016] Compare and contrast CSMA/CA with CSMA/CD. [WBUT 2014, 2016]
- [2018] Differentiate between CSMA/CD and CSMA/CA. [WBUT 2018]
- [2018] How does CSMA/CD differ from CSMA/CA? [WBUT 2018]
- [2012] c) Why is CSMA/CD not implemented in WLAN? [WBUT 2012, 2019]
- [2019] c) Why is CSMA/CD not implemented in WLAN? [WBUT 2012, 2019]
- [2023] (SA) 3. Compare between CSMA/CD and CSMA/CA [5]
- [2023] (LA) 7. (b) Discuss pure ALOHA and slotted ALOHA + vulnerable time. [3+2]
- [2023] (VSA) (VI) Maximum efficiency achievable in Pure ALOHA?

---

## Bit Stuffing, Byte Stuffing, and HDLC

**Depth Notes**
- Bit stuffing: used in bit-oriented protocols (HDLC); ensures data transparency by preventing flag pattern (01111110) from appearing in payload; stuffs extra 0 after five consecutive 1s.
- Byte stuffing: used in byte-oriented protocols (PPP, BISYNC); escapes special bytes.
- HDLC: High-Level Data Link Control; bit-oriented, synchronous, supports full-duplex; frame structure: flag, address, control, information, FCS, flag.
- Bit stuffing vs byte stuffing: former operates at bit level with 0 insertion; latter operates at byte level with escape sequences.

**PYQs**
- [2017] d) Compare bit stuffing with byte stuffing with an example. [WBUT 2017]
- [2018] 25. HDLC (High-Level Data Link Control) is a [WBUT 2018]
- [2023] (SA) 6. What is meant by bit stuffing and why it is used? [5]
- [2023] (VSA) (VIII) In bit stuffing when is an extra 0 bit stuffed to the data section of the frame?
- [2023] (LA) 7. (a) Explain bit stuffing method with a suitable example. [5]

---

## Error Detection (CRC)

**Depth Notes**
- Purpose: detect changes in transmitted frame.
- Parity: single bit; detects odd number of errors only.
- Checksum: used at network/transport layers; not strong.
- CRC: polynomial division; appends FCS; remainder 0 means no detectable error; used in Ethernet (802.3) and HDLC.

**PYQs**
- [2023] (SA) 5. Explain CRC with a suitable example. [5]


---

# Unit 2 (8 hrs)

---

## Error Detection and Correction

**Depth Notes**
- Parity: single bit; detects odd number of errors; cannot correct.
- Checksum: used at network/transport layers; limited strength; detects errors but not reliably.
- CRC: polynomial division; appends FCS; remainder 0 means no detectable error.
- Hamming code: error-correcting code; d_min determines detection/correction capability.
- Hamming distance: number of differing bit positions between two codewords.
  - d_min ≥ 2 detects single-bit errors
  - d_min ≥ 3 detects single-bit errors and corrects them

**PYQs**
- [2010] The hamming distance d(000, 011) is [WBUT 2010]
- [2010] 1. Why bit stuffing is needed in HDLC frame? [WBUT 2006, 2010]
- [2023] (VSA) (III) What is the Hamming Distance between two equal codewords?

---

## Data Link Flow and Error Control

**Depth Notes**
- Stop-and-Wait: sender sends one frame, waits for ACK; simple but inefficient on long fat pipes.
- Go-Back-N (GBN): sender can send up to N frames before ACK; cumulative ACKs; sender retransmits from lost/erroneous frame forward.
- Selective Repeat: sender retransmits only unACKed frames individually; receiver buffers out-of-order frames; requires larger window (≤ 2^(k-1) where k = seq num bits).
- Piggybacking: receiver attaches its ACK to next outgoing data frame instead of sending standalone ACK; reduces header overhead on duplex links.
- Delayed ACK: receiver intentionally delays ACK hoping to piggyback it on next data; trade-off between responsiveness and efficiency.
- Independent Ack vs Cumulative Ack: Independent acknowledges each frame separately; Cumulative acknowledges all frames up to a sequence number.

**PYQs**
- [2015] iii) Delayed Acknowledgement. [WBUT 2015]
- [2017] 23. Sliding window protocol is used for . [WBUT 2017]
- [2019] required for TCP segment? Explain your answer. [WBUT 2019]
- [2023] (LA) 8. (a) Write short notes on: (i) Protocol using selective repeat (ii) Stop and Wait protocol. [8]
- [2023] (LA) (c) With diagram explain Go-Back-N protocol. [6]
- [2023] (SA) 4. What is piggybacking? Discuss its advantages. [5]
- [2023] (VSA) (V) TCP assigns a sequence number to each segment. The sequence number for each segment is __________.
- [2023] (SA) 4. State one advantage and disadvantage of Independent Acknowledgement and Cumulative Acknowledgement. [5]
- [2023] (VSA) (VIII) The technique of temporarily delaying outgoing acknowledgements so that they can be hooked onto the next outgoing frame: name.

---

## HDLC and Framing

**Depth Notes**
- HDLC: High-Level Data Link Control; bit-oriented, synchronous, supports full-duplex.
- Frame structure: Flag (01111110), Address, Control, Information (payload), FCS, Flag.
- Bit stuffing: inserts extra 0 after five consecutive 1s in payload to prevent false flag detection by receiver.
- Byte stuffing: used in byte-oriented protocols (PPP); escapes special bytes with escape sequences.
- Does HDLC perform flow control? At data link layer, HDLC provides error control (via FCS/retransmission) and framing; some configurations support flow control through receive-ready/not-ready frames.
- 802.3 header: Preamble, SFD, Dest MAC, Src MAC, Length/Type, Data, Pad, CRC; padding added if data < 46 bytes to meet minimum 64-byte frame size.

**PYQs**
- [2006, 2010] 1. Why bit stuffing is needed in HDLC frame? [WBUT 2006, 2010]
- [2015] does HDLC perform flow control? [WBUT 2015]
- [2023] (SA) 6. What is meant by bit stuffing and why it is used? [5]
- [2023] (VSA) (VIII) In bit stuffing when is an extra 0 bit stuffed to the data section of the frame?
- [2023] (LA) 7. (a) Explain bit stuffing method with a suitable example. [5]
- [2017] (covered under Unit 1 organizer) d) Compare bit stuffing with byte stuffing with an example. [WBUT 2017]
- [2018] 25. HDLC (High-Level Data Link Control) is a [WBUT 2018]

---

## Congestion Control

**Depth Notes**
- Leaky Bucket: fixed-rate outflow; excess input is discarded or queued; smoothes bursty traffic.
- Token Bucket: allows burstiness up to bucket depth; tokens accumulate at constant rate; transmission allowed only when token available.
- Comparison: Leaky Bucket enforces rigid output rate; Token Bucket allows controlled bursts plus average rate.
- Closed loop congestion control: dynamic adjustment based on network feedback (e.g., congestion bit in packet, explicit backpressure, slow start, congestion avoidance in TCP).

**PYQs**
- [2007, 2011, 2012] 1. Explain Leaky Bucket algorithm for congestion control. [WBUT 2007, 2011, 2012]
- [2017] 4. Compare Leaky Bucket Algorithm with Token Bucket Algorithm. [WBUT 2017]
- [2017] 3. Discuss the methods of closed loop congestion control. [WBUT 2017]
- [2023] (VSA) (V) Token bucket algorithm is an advanced form of ___________. (Leaky Bucket)
- [2023] (LA) 9. (a) Explain token bucket algorithm. [7]
- [2023] (LA) (c) Explain briefly how the leaky-bucket and token bucket algorithm works. How can these two be related? [4+2]

---

## Transport Layer: TCP vs UDP

**Depth Notes**
- TCP: connection-oriented, reliable, flow-controlled, error-controlled, congestion-controlled, byte-stream, 3-way handshake, sequence numbers, cumulative ACK.
- UDP: connectionless, unreliable, no retransmission/flow control/congestion control, used for streaming, DNS, VoIP, speed-sensitive apps.
- Port numbers: identify application-layer processes on host; range 0–65535 (well-known 0–1023, registered 1024–49151, dynamic 49152–65535).
- Remote login protocol: Telnet (Application layer protocol, port 23).
- Mail transfer protocol: SMTP (port 25).
- Why IP is considered unreliable: no delivery guarantee, no ACK, no retransmission, no sequencing at IP layer; best-effort delivery.
- QoS attributes: delay, jitter, bandwidth, loss/loss probability; categorized as user-centric vs network-centric.

**PYQs**
- [2011, 2018, 2019] b) State the basic differences between TCP and UDP. [WBUT 2011, 2018, 2019]
- [2017] Compare TCP with UDP. [WBUT 2017]
- [2016] 5. Port number is [WBUT 2016]
- [2016] 15. Router solicitation and advertisement message is used by [WBUT 2016]
- [2023] (VSA) (I) Remote login protocol is known as _________
- [2023] (VSA) (VI) Mail transfer protocol is known as ___________
- [2023] (VSA) (VIII) What are the two categories of QoS attributes?
- [2023] (VSA) (XII) Why IP Protocol is considered as unreliable?
- [2023] (VSA) (III) Which transport layer protocol is used for SMTP?
- [2023] (VSA) (XI) Which protocol is used to get the MAC address given any IP address? (ARP)
- [2023] (LA) 9. (a) Explain the functionalities of the Transport layer. [5]

---

## TCP Internals and Connection Management

**Depth Notes**
- TCP header: Source Port, Dest Port, Sequence Number, Ack Number, Data Offset/Reserved/Flags, Window Size, Checksum, Urgent Pointer, Options.
- 3-way handshake: SYN → SYN-ACK → ACK; establishes connection parameters, initial sequence numbers.
- Port importance: multiplexing/demultiplexing multiple application connections on same host.
- TCP sequence number: byte-stream based; sequence number points to first data byte in segment, not segment number itself.

**PYQs**
- [2011, 2018, 2019] b) State the basic differences between TCP and UDP. [WBUT 2011, 2018, 2019]
- [2023] (LA) (b) Draw the TCP header and explain its parts. [8]
- [2023] (LA) 9. (a) With diagram explain three way handshaking in TCP. [6]
- [2023] (LA) (b) What is the importance of port number? Consider a TCP connection between Host A and Host B. [2+1]

---

## Network Layer Services

**Depth Notes**
- ARP: Address Resolution Protocol; maps IP address to MAC address; broadcast request, unicast reply.
- Virtual circuit network: connection-oriented at network layer; path established before data transfer (e.g., Frame Relay, ATM).
- Datagram network: connectionless; each packet routed independently using destination address.
- Router solicitation and advertisement: used by IPv6 (NDP — Neighbor Discovery Protocol) for address autoconfiguration.
- Virtual circuit vs datagram: virtual circuit provides guaranteed delivery order and QoS-like behavior; datagram is flexible but packets may take different paths.
- ISDN: Integrated Services Digital Network; digital over phone lines; BRI (2B+D) and PRI (23B+D).

**PYQs**
- [2011, 2014] f b) Compare virtual circuit network and datagram network. [WBUT 2014]
- [2012] and EGP? [WBUT 2012]
- [2016] 15. Router solicitation and advertisement message is used by [WBUT 2016]
- [2023] (VSA) (XI) Which protocol is used to get the MAC address given any IP address? (ARP)
- [2023] (VSA) (XII) Why IP Protocol is considered as unreliable?

---

---

# Unit 3 (14 hrs)

---

## Switching

**Depth Notes**
- Circuit Switching: dedicated path; three phases: connection setup, data transfer, teardown; inefficient for bursty traffic.
- Packet Switching: statistical multiplexing; store-and-forward; two sub-types:
  - Datagram: each packet routed independently; no dedicated path.
  - Virtual Circuit: connection-oriented at network layer; path established before transfer.
- Message Switching: entire message stored at each intermediate node before forwarding; obsolete.

**PYQs**
- No direct standalone questions in organizer or 2023–2025 papers.
- Virtual circuit vs datagram covered under Routing/Network Layer Services.

---

## IPv4/IPv6 Headers and Addressing

**Depth Notes**
- IPv4 header: Version, IHL, Type of Service, Total Length, Identification, Flags, Fragment Offset, TTL, Protocol, Header Checksum, Source IP, Dest IP, Options.
- IPv6 header: Version, Traffic Class, Flow Label, Payload Length, Next Header, Hop Limit, Source/Dest (128-bit each); no header checksum; extension headers instead of options.
- IPv4 address: 32-bit; classes A/B/C/D/E; subnet mask.
- IPv6 address: 128-bit; types: unicast, multicast, anycast; notation: 8 groups of 4 hex digits.
- ICMP: Internet Control Message Protocol; error reporting and diagnostics; used by ping and traceroute; ICMPv6 integrates NDP (Neighbor Discovery Protocol).

**PYQs**
- [2006] b) State the advantages of IPv6 over IPv4 [WBUT 2006, 2013, 2016]
- [2011] 4. Compare IPv4 and IPv6. [WBUT 2011]
- [2011] o) IPv6 [WBUT 2011]
- [2013] b) State the advantages of IPv6 over IPv4 [WBUT 2006, 2013, 2016]
- [2014] | 6. IPv6 addresses are bytes long. [WBUT 2014]
- [2014] What is the header size in bytes [WBUT 2014]
- [2014] A)nswer; vantages of ICMP over the IPV4. [WBUT 2014, 2018]
- [2016] b) State the advantages of IPv6 over IPv4 [WBUT 2006, 2013, 2016]
- [2018] A)nswer; vantages of ICMP over the IPV4. [WBUT 2014, 2018]
- [2023] (VSA) (IX) What are the number of bits required for IPv4 addresses when expressed in binary?

---

## Subnetting and CIDR

**Depth Notes**
- Subnetting: borrow bits from host portion to create sub-networks; reduces broadcast domain, improves security and address utilization.
- Subnet mask: 32-bit pattern; contiguous 1s in network+subnet portion.
- Block design: allocate subnets based on smallest/largest block requirement; VLSM for flexible sizing.
- CIDR: classless inter-domain routing; slash notation (e.g., /24); supernetting for route aggregation; eliminates class boundaries.
- Subnetting numericals: given IP + mask → determine network address, broadcast address, first/last host, number of hosts, number of subnets.

**PYQs**
- [2006] 1. a) What is the purpose of subnetting? [WBUT 2006, 2011]
- [2011] 1. a) What is the purpose of subnetting? [WBUT 2006, 2011]
- [2011] 1. The address space of i [WBUT 2011, 2012]
- [2011] a) 192.168.10.39 b) 192.168.10.47 [WBUT 2011]
- [2011] 38 ) 19.34.21.8 stid of the following IP addresses. [WBUT 2011, 2013]
- [2012] 1. The address space of i [WBUT 2011, 2012]
- [2013] 38 ) 19.34.21.8 stid of the following IP addresses. [WBUT 2011, 2013]
- [2014] 8.1P address in the B class is given by [WBUT 2014]
- [2015] pesign the subblocks and give the slash notation for each subblock. [WBUT 2015]
- [2016] is the maximum number of hosts per subnet? [WBUT 2016]
- [2023] (SA) 5. What is the first address of a block of classless addresses if one of the addresses is 12.2.2.76/27 [5]
- [2023] (LA) (b) Classless Inter-domain Routing (CIDR) receives a packet with address 131.23.151.76. The router's [5]

---

## ARP, RARP, BOOTP, and DHCP

**Depth Notes**
- ARP: Address Resolution Protocol; maps IPv4 address to MAC address; broadcast request, unicast reply; maintains ARP cache/table.
- RARP: Reverse ARP; maps MAC address to IP; used by diskless workstations; largely obsolete.
- BOOTP: Bootstrap Protocol; diskless workstation booting; relay agents; static configuration database; older than DHCP.
- DHCP: Dynamic Host Configuration Protocol; DORA process:
  - Discover: client broadcasts DHCPDISCOVER
  - Offer: server replies with DHCPOFFER
  - Request: client requests offered address
  - Acknowledge: server confirms with DHCPACK
- DHCP provides: IP address, subnet mask, default gateway, DNS server, lease time.

**PYQs**
- [2018] 20 2) IP b) ARP sement mescs)algew;: used by [WBUT 2018]
- [2023] (LA) (b) Explain the DHCP state transition diagram. [6]

---

## Delivery, Forwarding, and Router Lookup

**Depth Notes**
- **Direct delivery**: source and destination on same network; sender resolves destination MAC via ARP and sends frame directly without involving any router.
- **Indirect delivery**: destination on a different network; sender forwards packet to default gateway (router); router makes the forwarding decision.
- Routing decision = compare destination IP with routing table entries to determine next hop.
- **Forwarding table**: optimized data structure used by router for fast packet lookup (usually derived from routing table, may use trie/ Patricia tree, longest prefix match).
- **Routing table**: built by routing protocols; contains network destination, next hop, metric, interface.
- **Longest prefix match**: when multiple forwarding table entries match the destination IP, select the entry with the longest subnet mask (most specific route).
- Router lookup steps:
  1. Extract destination IP.
  2. Find all forwarding table entries that match (AND with mask = destination network).
  3. Among matches, pick entry with longest prefix (largest mask / most 1s).
  4. Forward out associated interface to next hop.

**PYQs**
- [2023] (LA) (b) Classless Inter-domain Routing (CIDR) receives a packet with address 131.23.151.76. The router's [5]
- VSA concepts tied to longest prefix match and routing table lookup are frequently tested in organizer.

---

## Routing Algorithms and Protocols

**Depth Notes**
- Distance Vector (DV): Bellman-Ford; nodes share routing table with neighbors; periodic full-table updates; slow convergence; count-to-infinity problem.
- Link State (LS): Dijkstra's Shortest Path First; nodes flood LS packets to entire network; each node builds complete topology map; faster convergence, more memory/CPU.
- Routing table: destination network, next hop, metric/hop count, interface.
- RIP: Routing Information Protocol; DV algorithm; UDP port 520; hop count metric; max hop count = 16 (unreachable); update every 30s.
- OSPF: Open Shortest Path First; LS algorithm; uses Dijkstra; hierarchical (areas); no hop count limit; faster convergence; link-state advertisements (LSA).
- BGP: Border Gateway Protocol; inter-domain (between ASes); path vector protocol; uses TCP port 179; eBGP vs iBGP.
- Autonomous System (AS): group of networks under single administrative control; AS number; IGP operates within AS (RIP, OSPF), EGP operates between ASes (BGP).
- Two-node instability: DV-specific count-to-infinity where two nodes bounce metric updates between each other; solutions: split horizon, route poisoning, hold-down timers, triggered updates.

**PYQs**
- [2007] 1. Explain Link State Routing. [WBUT 2007, 2013]
- [2008] typical routing table. [WBUT 2008, 2012]
- [2010] S. Explain link state routing. [WBUT 2010]
- [2011] d) OSPE [WBUT 2011, 2019]
- [2012] typical routing table. [WBUT 2008, 2012]
- [2012] and EGP? [WBUT 2012]
- [2013] 1. Explain Link State Routing. [WBUT 2007, 2013]
- [2014] round of update, what will be the cost to N1 in distance vector of N3? [WBUT 2014]
- [2017] 24. Which the following is an inter-domain routing protocol? [WBUT 2017]
- [2019] d) OSPE [WBUT 2011, 2019]
- [2019] ; services of IP. [WBUT 2019]
- [2019] ' in B's routing table for Net-1? [WBUT 2019]
- [2023] (LA) (b) Explain the concept of RIP. [7]
- [2023] (VSA) (IV) What are autonomous systems in computer networks?
- [2023] (LA) 11. (a) Explain the two node instability problem in Distance vector routing. [5]
- [2023] (LA) (b) Discuss the possible solutions of the two node instability problem in Distance vector routing. [5]
- [2023] (LA) 8. (a) Explain Distance Vector Routing algorithm with an example. [10]
- [2023] (LA) (b) Classless Inter-domain Routing (CIDR) receives a packet with address 131.23.151.76. The router's [5]

---

---

# Unit 4 (8 hrs)

---

## Transport Services and the Need for a Transport Layer

**Depth Notes**
- Transport layer: host-to-host delivery; segments; multiplexing/demultiplexing by port numbers.
- Two transport services: connection-oriented vs connectionless service.
- Why IP is unreliable: no delivery guarantee, no ACK, no retransmission, no sequencing; best-effort delivery inside hosts.
- Segment = transport-layer packet at the sender; reassembled at receiver.
- Congestion = too many sources sending too much data too fast for network to handle; occurs at network layer.

**PYQs**
- [2024, 2025] (SA) 6. What are the two possible transport services? What is meant by segment? What is congestion? [5]
- [2023] (VSA) (XII) Why IP Protocol is considered as unreliable?
- [2023] (VSA) (III) Which transport layer protocol is used for SMTP?
- [2023] (VSA) (VI) Mail transfer protocol is known as ___________
- [2016] 5. Port number is [WBUT 2016]

---

## UDP

**Depth Notes**
- Connectionless, unreliable transport service; no handshake, no connection state.
- Header: Source Port, Dest Port, Length, Checksum.
- Checksummerror detection: receiver computes checksum and checks it against transmitted value; detects flipped bits; cannot guarantee no bit error occurred.
- Used where latency matters more than reliability: streaming, DNS, VoIP.
- Smaller header overhead than TCP.

**PYQs**
- [2024, 2025] (SA) 6. Last subparts: checksum matching and certainty. [5]
- [2023] (VSA) (XII) Why IP Protocol is considered as unreliable?
- [2019] UDP checksum MCQ/notes. [WBUT 2019]

---

## TCP

**Depth Notes**
- Connection-oriented, reliable transport service; byte-stream oriented.
- Header: Source Port, Dest Port, Sequence Number, Ack Number, Data Offset/Reserved/Flags, Window Size, Checksum, Urgent Pointer, Options. Minimum 20 bytes; padded to 32-bit boundary.
- Sequence number: byte-stream based; numbers first data byte in segment, not segment number.
- Sliding window: receiver advertises window size; controls flow and throughput; window may advance dynamically.
- Importance of port number: identifies application process; enables multiplexing/demultiplexing on same host.
- 3-Way handshake: SYN → SYN-ACK → ACK; sets parameters and ISN.
- Connection states: CLOSED → LISTEN → SYN-SENT → SYN-RCVD → ESTABLISHED → FIN-WAIT-1 → FIN-WAIT-2/TIME-WAIT → CLOSED.

**PYQs**
- [2023] (LA) (b) Draw the TCP header and explain its parts. [8]
- [2023] (LA) 9. (a) With diagram explain three way handshaking in TCP. [6]
- [2023] (LA) (b) What is the importance of port number? Consider a TCP connection between Host A and Host B. [2+1]
- [2023] (VSA) (V) TCP assigns a sequence number to each segment. The sequence number for each segment is __________.
- [2019] TCP sequence numbers purpose, padding. [WBUT 2019]
- [2019] TCP sliding window diagram. [WBUT 2019]

---

## Congestion Control and QoS

**Depth Notes**
- Open-loop control: prevent congestion before occurrence.
  - Leaky Bucket: fixed-rate output; bursty input smoothed; excess discarded or queued.
  - Token Bucket: tokens accumulate at fixed rate; transmit only when token available; transmits in bursts up to bucket depth.
  - Relation: Token Bucket is an advanced form of Leaky Bucket that allows controlled burstiness plus average rate limit.
- Closed-loop control: react to congestion.
  - Congestion bit, explicit backpressure, slow start, congestion avoidance in TCP.
- QoS attributes: reliability, delay, jitter, bandwidth.

**PYQs**
- [2007, 2011, 2012] Explain Leaky Bucket algorithm for congestion control. [WBUT 2007, 2011, 2012]
- [2017] Compare Leaky Bucket Algorithm with Token Bucket Algorithm. [WBUT 2017]
- [2017] Discuss the methods of closed loop congestion control. [WBUT 2017]
- [2023] (VSA) (V) Token bucket algorithm is an advanced form of ___________. (Leaky Bucket)
- [2023] (LA) 9. (a) Explain token bucket algorithm. [7]
- [2023] (LA) (c) Explain briefly how the leaky-bucket and token bucket algorithm works. How can these two be related? [4+2]
- [2023] (SA) 4. State one advantage and disadvantage of Independent Acknowledgement and Cumulative Acknowledgement each. In Go Back N ARQ if both the sender window size and receiver window size is 1 then what does it indicate? [related flow/state concept]
- [2023] (LA) 8. (c) With diagram explain Go-Back-N protocol. [related congestion/order context]

---

## SCTP

**Depth Notes**
- Stream Control Transmission Protocol; message-oriented unlike TCP byte-stream.
- Multi-homing: multiple IP addresses per endpoint; failover support.
- Multi-streaming: independent streams avoid head-of-line blocking.
- 4-way handshake using cookies; more resistant to SYN floods than TCP.

**PYQs**
- No direct PYQs in 2023–2025 papers.
- Syllabus gap note retained.

---

Unit 4 high-yield threads: TCP header fields + diagram, 3-way handshake diagram, TCP vs UDP comparison, Leaky Bucket vs Token Bucket relationship, transport services + segment/congestion short notes, sliding window + two-node Instability context.

---

# Unit 5 (8 hrs)

---

## DNS and DDNS

**Depth Notes**
- DNS: Domain Name System; hierarchical, distributed database; maps domain names to IP addresses.
- Hierarchy: root servers, TLD servers, authoritative servers; resolvers.
- Resource Records: A, AAAA, MX, CNAME, PTR, NS.
- DDNS: Dynamic DNS; automatic updates when IP changes; RFC 2136; TSIG authentication; DHCP+DDNS integration.

**PYQs**
- [2011] each other in the context of DNS? Explain with example. [WBUT 2011]
- [2023] (VSA) (I) What is DNS in computer network?
- [2023] (VSA) (IX) Three main division of the domain name space are _________.
- [2024, 2025] (VSA) (I) What is DNS in computer network?
- [2024, 2025] (VSA) (IX) Three main division of the domain name space are _________.

---

## Application Protocols

**Depth Notes**
- TELNET: remote login; Application layer; port 23; text-based; now largely replaced by SSH.
- EMAIL: SMTP (port 25, push), POP3 (port 110, pull/download), IMAP (port 143, server-side mail management).
- FTP: file transfer; uses two connections — control (port 21) and data (port 20); modes: active vs passive; can be used to browse website via anonymous login + directory traversal.
- WWW/HTTP: WWW = information space; HTTP = stateless request/response; HTTPS = TLS-secured.
- SNMP: Simple Network Management Protocol; Manager/Agent architecture; MIB (Management Information Base); port 161.

**PYQs**
- [2018] | 6. The packet of information at the application layer is called [WBUT 2018]
- [2018] 7. Which of the following is an application layer service? [WBUT 2018]
- [2023] (VSA) (VI) What are the transmission modes in FTP?
- [2023] (LA) 11. (a) Explain how FTP can be used to browse website? [7]
- [2024, 2025] (SA) 2. How does FTP Work? [5]
- [2024, 2025] (VSA) (VI) What are the transmission modes in FTP?

---

## Bluetooth

**Depth Notes**
- Short-range wireless PAN; IEEE 802.15.1.
- Piconet: one master + up to 7 active slaves; scatternet = interconnected piconets.
- Frequency hopping spread spectrum (FHSS) in 2.4 GHz; 1 MHz hops, 1600 hops/sec.
- Protocol stack: RF, Baseband, L2CAP, SDP, RFCOMM, BNEP.

**PYQs**
- [2023] (LA) 7. (b) Discuss Bluetooth architecture and protocols. [8]
- [2023] (LA) 7. (b) Discuss Bluetooth architecture and protocols. [8]

---

## Firewalls and VPN

**Depth Notes**
- Purpose: monitor/control traffic between trusted internal and untrusted external networks.
- Types: Packet filter (stateless/stateful), Application gateway (proxy), Circuit-level gateway, Stateful inspection.
- DMZ: demilitarized zone; isolated subnetwork between internal network and internet; hosts public-facing services.
- VPN: Virtual Private Network; encrypted tunnel over untrusted network; IPsec/SSL/TLS based.

**PYQs**
- [2014] d) Firewall [WBUT 2014]
- [2019] a) Kerberos b) Digital signature [WBUT 2019]
- [2023] (VSA) (XII) The point where the secure internal network and untrusted external network meet and a firewall is installed is known as______ .
- [2024, 2025] (SA) 5. How does firewall protect data? [5]
- [2024, 2025] (VSA) (XII) The point where secure internal network and untrusted external network meet... [DMZ]
- [2024, 2025] (VSA) (IV) Write one advantage of VPN.
- [2024, 2025] (LA) 10. (a) How does a packet filter firewall work? [7]

---

## Basic Cryptography

**Depth Notes**
- Symmetric: single shared key; AES, DES; fast but key distribution problem.
- Asymmetric: public/private key pair; RSA, ECC; slower; enables digital signatures.
- RSA: key generation (p, q → n, φ, e, d); encrypt c = m^e mod n; decrypt m = c^d mod n.
- Digital signature: hash message → encrypt hash with private key → receiver verifies with public key; provides authentication and non-repudiation.
- PGP: Pretty Good Privacy; combines symmetric + asymmetric; used for secure email.
- Kerberos: network authentication protocol; uses tickets and KDC.

**PYQs**
- [2007, 2009, 2011, 2013] non-repudiation be implemented by the dig [WBUT 2007, 2009, 2011, 2013]
- [2014] b) Explain RSA algorithm with an example. [WBUT 2014]
- [2019] a) Kerberos b) Digital signature [WBUT 2019]
- [2023] (VSA) (XI) Why is PGP needed?
- [2024, 2025] (LA) (b) With a block diagram explain symmetric key encryption. [8]
- [2024, 2025] (VSA) (IV) Write one advantage of VPN.

---

Unit 5 high-yield threads: RSA full numerical example, firewall types + DMZ, DNS hierarchy, FTP commands/modes, symmetric vs asymmetric comparison.

---

# Global Gap Fill

**SCTP (Unit 4):** RFC 4960; message-oriented; multi-homing; multi-streaming; 4-way handshake (cookies); no head-of-line blocking.

**DDNS (Unit 5):** RFC 2136 dynamic DNS UPDATE; TSIG authentication; DHCP+DDNS auto-updates.

**TCP 3-Way + States:** SYN→SYN-ACK→ACK; ISN random. States: CLOSED→LISTEN→SYN-SENT→SYN-RCVD→ESTABLISHED→FIN-WAIT-1→FIN-WAIT-2→TIME-WAIT(2MSL)→CLOSED.

---

# Quick Reference

**Subnetting:** Class A /8, B /16, C /24. Hosts = 2^(32-mask)-2.
**Routing:** RIP (UDP 520, inf=16), OSPF (Dijkstra), BGP (TCP 179).
**Congestion:** Leaky Bucket (constant r), Token Bucket (tokens at rate r).
**TCP Flags:** URG, ACK, PSH, RST, SYN, FIN.
**QoS:** Reliability, Delay, Jitter, Bandwidth.

---

# Syllabus Audit Summary

| Unit | Status |
|------|--------|
| Unit 1 | 15/15 topics COVERED |
| Unit 2 | 14/15 topics COVERED (CDMA/CA = typo for CSMA/CA) |
| Unit 3 | 11/11 topics COVERED |
| Unit 4 | 10/10 topics COVERED |
| Unit 5 | 12/12 topics COVERED |

Total: 63 topics | Gaps: 0

---

**END**