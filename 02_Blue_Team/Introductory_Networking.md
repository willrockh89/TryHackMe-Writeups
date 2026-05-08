# Lab: Introductory Networking

---

## Room Metadata

* **Platform:** [TryHackMe](https://tryhackme.com/room/introtonetworking)
* **Category:** Blue Team / Fundamentals
* **Room:** Introductory Networking
* **Difficulty:** Easy
* **Status:** `Completed`

---

## Objective

**Goal:** To establish a high-precision understanding of network communication models (OSI and TCP/IP) and to master the standard command-line utilities used for network diagnostics, troubleshooting, and reconnaissance.

---

## Tools Used

| Tool | Function | Key Protocol/Feature |
| --- | --- | --- |
| **Ping** | Connectivity testing | ICMP |
| **Traceroute** | Path mapping | TTL (Time to Live) / UDP / ICMP |
| **Whois** | Domain reconnaissance | WHOIS protocol (Port 43) |
| **Dig** | DNS interrogation | DNS (A, AAAA, MX, TXT records) |

---

## Methodology

### Phase 1: Theoretical Framework & Models

1. **OSI Model Analysis:** Deconstructed the seven layers of communication, focusing on the distinction between the upper "Application" layers (5–7) and the lower "Data Transport" layers (1–4).
2. **Encapsulation & De-encapsulation:** Evaluated the data lifecycle as it moves through the stack, specifically how headers and trailers (at Layer 2) are applied to data segments.
3. **TCP/IP Suite:** Compared the theoretical OSI model to the practical TCP/IP stack. Analyzed the **TCP Three-Way Handshake** (SYN, SYN/ACK, ACK) as the foundation for connection-oriented reliability.

### Phase 2: Network Diagnostics & Troubleshooting

1. **Connectivity Verification:** Used `ping` to measure RTT (Round Trip Time) and verify remote host availability.
2. **Hop Analysis:** Utilized `traceroute` to identify every router (hop) between the source and the target, providing visibility into internal and external infrastructure pathing.

### Phase 3: Infrastructure Reconnaissance (OSINT)

1. **Domain Ownership:** Leveraged `whois` to identify registration details, including creation dates and physical location data of corporate infrastructure.
2. **DNS Interrogation:** Employed `dig` to perform advanced DNS lookups, identifying record types and Time-to-Live (TTL) values, which are critical for understanding cache persistence.

---

## Key Findings

* **Target IPv4 Address:** `217.160.0.152` (muirlandoracle.co.uk).
* **DNS Persistence:** Identified a standard TTL of **86400** seconds (24 hours) for record expiration.
* **Infrastructure Insights:** Traceroute confirmed the use of TTL manipulation to map network waypoints, a critical technique for identifying points of failure.
* **Registration History:** Successfully traced domain history back to 1997 for legacy social media infrastructure.

---

## Reflection

**Real-World Context:** Networking is the nervous system of modern infrastructure. This lab reinforces the "Function over Form" logic essential in both aerospace propulsion and cybersecurity. Just as an aircraft’s performance is monitored through distinct, layered sensors to ensure airworthiness, network communication relies on the strict adherence to the OSI layers to ensure data integrity. Understanding the **TCP/IP stack** is the equivalent of understanding a propulsion system's technical manual—without knowing how the components (packets) are supposed to interlock, troubleshooting a failure (incident response) becomes impossible. Precision in these fundamentals is what separates a standard technician from a senior analyst.

---
