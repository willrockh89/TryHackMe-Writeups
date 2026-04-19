### Lab: SOC Analyst Operations — Triage and Remediation

**Room Metadata**

  * **Platform:** [TryHackMe](https://tryhackme.com/)
  * **Category:** Blue Team / Operations
  * **Room:** [Junior Security Analyst Intro](https://tryhackme.com/room/jrsecanalystintrouxo)
  * **Difficulty:** Easy
  * **Status:** `Completed`

#### Objective

Immerse in the daily operations of a Junior Security Analyst within a SOC to triage real-time alerts, investigate malicious traffic, and execute defensive actions through a simulated dashboard.

#### Tools Used

| Tool | Purpose |
| :--- | :--- |
| **Alert Dashboard** | Real-time monitoring and alert triage. |
| **Log Viewer** | Inspecting source/destination IPs and timestamps. |
| **Firewall Manager** | Implementing IP blocking and traffic rules. |
| **Ticketing System** | Incident documentation and escalation. |

#### Methodology

1.  **Alert Triage:** Identified a high-priority alert indicating a malicious connection from IP `221.181.185.159`.
2.  **Incident Documentation:** Logged the findings and escalated the event to a Senior Security Analyst for oversight.
3.  **Remediation:** Accessed the firewall interface and applied a block rule to the malicious source, successfully securing the system.

#### Reflection

**Real-World Context:** This lab highlights the "front-line" reality of a SOC. Every alert is a potential threat to organizational integrity. Speed of response must be balanced with precision; identifying a single malicious "part" (IP) and isolating it before it causes systemic failure mirrors the quality assurance mindset required in technical maintenance.

-----

