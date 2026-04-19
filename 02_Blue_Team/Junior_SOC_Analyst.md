## 🔵 Blue Team (Defensive)

### Lab: SOC Analyst Fundamentals — Triage and Remediation

**Room:** [Junior Security Analyst Intro](https://tryhackme.com/room/jrsecanalystintrouxo)

#### Objective

Establish a baseline for daily Security Operations Center (SOC) activities, focusing on the lifecycle of an alert from initial detection to final resolution.

#### Tools Used

| Tool | Purpose |
| :--- | :--- |
| **Alert Dashboard** | Real-time monitoring of security events. |
| **Log Viewer** | Identifying source/destination IPs and event timestamps. |
| **Firewall Manager** | Implementing IP shunning and traffic rules. |
| **Ticketing System** | Incident documentation and escalation. |

#### Methodology

1.  **Alert Identification:** Monitored the dashboard to identify a high-priority connection from a known malicious IP (`221.181.185.159`).
2.  **Incident Documentation:** Logged the event and initiated the escalation protocol to a Senior Security Analyst.
3.  **Remediation:** Accessed the firewall interface and applied a block rule to the malicious source, successfully securing the flag: `THM{M0NITOR_4ND_D3F3ND}`.

-----

### Lab: Web Attack Forensics — Log Analysis with Splunk

**Room:** [Drone Alone (AoC 2025)](https://tryhackme.com/room/webattackforensics-aoc2025-b4t7c1d5f8)

#### Objective

Trace a Command Injection attack from the web layer down to the operating system using centralized logging and process telemetry.

#### Tools Used

  * **SIEM:** Splunk (Search Processing Language)
  * **Log Sources:** Apache Access/Error logs, Windows Sysmon
  * **Decoders:** Base64 web-based tools

#### Methodology

1.  **Web Request Analysis:** Queried `index=windows_apache_access` to find PowerShell strings; decoded a Base64 payload revealing the attacker's intent.
2.  **Process Lineage:** Analyzed Sysmon events to find `httpd.exe` spawning `cmd.exe`, confirming a successful breakout from the web application.
3.  **Reconnaissance Identification:** Identified the execution of `whoami.exe` as the attacker’s method for privilege assessment.

-----

## 🟣 Purple Team (Integrated/Fundamentals)

### Lab: Environment Architecture — Deploying Kali Purple

**Room:** [Security+ 701 Series](https://www.google.com/search?q=https://learning.oreilly.com/videos/security-701/9781807603670/)

#### Objective

Deploy a NIST-aligned security workstation, bridging the gap between offensive tools and defensive frameworks.

#### Tools Used

  * **Hypervisor:** VMware Workstation Player (Type 2)
  * **Framework:** NIST Cybersecurity Framework (Identify, Protect, Detect, Respond, Recover)
  * **System Tools:** `apt`, `GRUB`, XFCE Desktop

#### Methodology

1.  **Hardware Allocation:** Configured 8GB RAM and 50GB split-disk storage to ensure a stable, portable lab environment.
2.  **NIST Alignment:** During installation, selected the specific Kali Purple toolset to organize the OS menu by the NIST defensive lifecycle.
3.  **FHS Validation:** Performed a "Binary Transparency" test by copying `/bin/ls` to `/bin/list` to verify the Linux "Everything is a File" principle.

-----

### Lab: Network Intelligence — DNS Interrogation Masterclass

**Room:** [NSLOOKUP & DIG](https://www.google.com/search?q=https://learning.oreilly.com/videos/security-701/9781807603670/)

#### Objective

Master the protocols and utilities required for domain reconnaissance and DNS troubleshooting.

#### Tools Used

| Utility | Use Case |
| :--- | :--- |
| **NSLOOKUP** | Quick cross-platform record verification and interactive queries. |
| **DIG** | Advanced Linux-native interrogation with raw message headers. |
| **Protocols** | DNS (UDP/TCP 53) |

#### Methodology

1.  **Record Extraction:** Queried `A`, `MX`, and `TXT` records to map domain infrastructure and security verification strings.
2.  **Path Tracing:** Utilized `dig +trace` to visualize the delegation path from Root servers to Authoritative servers.
3.  **Diagnostic Pivot:** Demonstrated "Server Bypassing" by directing queries to `@8.8.8.8` to confirm local vs. global resolution.

-----
