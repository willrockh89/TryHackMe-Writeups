# Lab: Nmap - Advanced Port Scanning

---

## Room Metadata

* **Platform:** [TryHackMe](https://tryhackme.com/room/furthernmap)
* **Category:** Blue Team / Reconnaissance
* **Room:** Further Nmap
* **Difficulty:** Medium
* **Status:** Completed

---

## Objective

**Goal:** To perform advanced network discovery and vulnerability research using the Nmap Security Scanner. This lab documents the transition from basic port discovery to complex scanning techniques, including script engine (NSE) implementation and firewall evasion.

---

## Tools Used

| Tool | Function | Application |
| --- | --- | --- |
| **Nmap** | Primary Scanner | Port discovery, service versioning, and NSE execution. |
| **Wireshark** | Packet Analysis | Validation of scan types (SYN vs. Connect) via packet captures. |
| **Lua** | Scripting Language | The underlying language for the Nmap Scripting Engine (NSE). |

---

## Methodology

### Phase 1: Target Discovery & Host Mapping

1. **ICMP Analysis:** Identified that the target host suppresses ICMP echo requests.
2. **Host Discovery:** Employed the `-sn` switch (Ping Sweep) and subsequent `-Pn` (No Ping) to force scanning on a host that appears offline due to firewall rules.

### Phase 2: Tactical Port Scanning

1. **Stealth Scanning:** Utilized SYN scans (`-sS`) to map open ports while maintaining a "half-open" state, reducing the log footprint on the target.
2. **Protocol-Specific Probing:** Conducted UDP scans (`-sU`) targeting the top 20 ports to identify stateless services (DNS/SNMP) that are often overlooked in TCP-only audits.
3. **Standard Verification:** Used TCP Connect scans (`-sT`) to verify service availability and adherence to RFC 9293 standards.

### Phase 3: Advanced Stealth & Evasion

1. **Flag Manipulation:** Executed NULL (`-sN`), FIN (`-sF`), and Xmas (`-sX`) scans to exploit specific TCP stack behaviors and bypass stateless firewalls.
2. **IDS/Firewall Evasion:** Applied packet fragmentation (`-f`) and MTU manipulation (`--mtu 8`) to split probes into smaller segments, confusing signature-based detection systems.
3. **Data Obfuscation:** Appended random data to packet payloads (`--data-length`) to alter the standard Nmap traffic signature.

### Phase 4: Vulnerability Research (NSE)

1. **Script Auditing:** Navigated the `/usr/share/nmap/scripts/` directory to locate service-specific Lua scripts.
2. **Automated Exploitation Discovery:** Ran the `ftp-anon` script to detect misconfigured file transfer services.

---

## Key Findings

* **Target IP:** `10.146.169.246`
* **Service Density:** Identified **5 open ports** within the 1–5000 range.
* **Critical Misconfiguration:** Confirmed **Anonymous FTP Login** is enabled on Port 21, allowing unauthorized read/write access to the root directory.
* **Evasion Success:** Verified that the target responds to non-SYN packets (NULL/FIN/Xmas) with a `RST` only on closed ports, confirming a non-Windows backend.

---

## Reflection

**Real-World Context:** Advanced scanning is the digital equivalent of a "pre-flight inspection." In aerospace maintenance, missing a single hairline fracture in a turbine blade can lead to catastrophic failure; similarly, in cybersecurity, failing to identify a single "filtered" port or an anonymous service exposure can compromise an entire network. This lab emphasizes a "Function over Form" approach—using specific scan types like **SYN** and **UDP** not because they are the default, but because they provide the most accurate diagnostic data under specific firewall constraints. Precision in the reconnaissance phase ensures that subsequent defensive or offensive measures are built on a foundation of technical truth rather than assumptions.

---
