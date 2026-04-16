# Lab: A Day in the Life of a Security Analyst

## Objective
**Goal:** Immerse in the daily operations of a Junior Security Analyst within a Security Operations Center (SOC). This lab focuses on triaging real-time alerts, investigating malicious traffic, and executing defensive actions through a simulated dashboard.

## Tools Used
* **Environment:** [TryHackMe Junior Security Analyst Intro](https://tryhackme.com/room/jrsecanalystintrouxo)
* **Systems:**
    * **Alert Dashboard:** For monitoring incoming security events.
    * **Log Analysis:** To inspect source/destination IP addresses and timestamps.
    * **Firewall Management:** To implement IP blocking/shunning.
    * **Ticketing System:** For documenting and escalating incidents.

## Methodology
1.  **Alert Triage:** Monitored the dashboard for high-priority alerts. Identified a critical event indicating a potential malicious connection.
2.  **Log Investigation:** Inspected the alert details to identify the **Malicious IP Address** (e.g., `221.181.185.159`) and the target system within the network.
3.  **Threat Intelligence Check:** (Simulated) Verified the reputation of the source IP to confirm it was associated with known malicious activity.
4.  **Incident Escalation:** Documented the findings and escalated the alert to a **Senior Security Analyst** for deeper investigation and oversight.
5.  **Remediation & Hardening:** Accessed the firewall management interface and applied a rule to block the malicious IP, effectively neutralizing the threat.

## Key Findings
* **Malicious IP Identified:** `221.181.185.159`
* **Escalation Path:** Successfully escalated to a "Senior Security Analyst."
* **System Response:** Upon blocking the IP, the firewall confirmed the action with a flag or completion message (e.g., `THM{M0NITOR_4ND_D3F3ND}`).
* **Operational Flow:** Verified that the "Frontline" defense relies on a systematic cycle of detection, investigation, escalation, and remediation.

## Reflection
**Real-World Context:** This lab highlights the "mountain of tickets" reality that SOC analysts face during an 8-hour shift. In a professional cybersecurity role—much like in aerospace quality assurance—the speed of response must be balanced with the precision of the investigation. Every alert is a potential threat to the organization's integrity. Understanding the escalation chain and knowing how to interact with defensive infrastructure like firewalls are fundamental skills for any Blue Team professional.
