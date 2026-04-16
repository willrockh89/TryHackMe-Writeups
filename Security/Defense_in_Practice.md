# Lab: Defensive Security in Practice — Defending FakeBank

## Objective
**Goal:** Act as a Junior Security Analyst for a large financial institution to investigate an active **Web Discovery Attack**. The objective is to utilize a Security Information and Event Management (SIEM) dashboard to identify malicious traffic and implement protective measures to secure the infrastructure.

## Tools Used
* **Environment:** [TryHackMe Defensive Security Intro](https://tryhackme.com/room/defensivesecurityintroQR)
* **Security Stack:**
    * **SIEM Dashboard:** Used for real-time event monitoring and alert triage.
    * **Network Monitor:** To analyze traffic flow and source IP reputation.
    * **Firewall/IP Blocker:** To execute remediation actions against identified threats.

## Methodology
1.  **Alert Triage:** Monitored the "Security Analyst Dashboard" for unassigned events. Identified a **Medium Severity** alert titled **"Web Discovery Attack."**
2.  **Attack Analysis:** * **Description:** Automated directory enumeration detected on admin endpoints.
    * **Source IP:** `32.122.195.63`
    * **Context:** This attack indicates an adversary is attempting to find hidden files or directories (like `/admin` or `/config`) to gain unauthorized access.
3.  **Investigation:** Selected the alert to view granular details. Confirmed the traffic patterns were non-human and consistent with automated scanning tools (e.g., Gobuster or Dirbuster).
4.  **Remediation:** * Navigated to the **Network Monitor** or IP Management interface.
    * Input the malicious source IP: `32.122.195.63`.
    * Executed the **Block/Ban** command to terminate the connection and prevent further enumeration.
5.  **Verification:** Confirmed the attack status changed to "Resolved" and secured the final flag.

## Key Findings
* **Flag Captured:** `THM{FAKEBANK-SECURED}`
* **Threat Actor Tactic:** The use of **Directory Enumeration** is a common reconnaissance phase in the Cyber Kill Chain used to map the attack surface of web applications.
* **Defense Strategy:** Rapid identification and IP shunning via a SIEM/Firewall integration is a primary defensive control to mitigate automated brute-force or discovery attempts.

## Reflection
**Real-World Context:** In a high-stakes environment like a bank, defensive security is about **cognitive load management** and **pacing**. An analyst must quickly filter "noise" from actual threats. This lab mirrors the "precision and QA" mindset from my aerospace background—identifying a single faulty "part" (the malicious IP) and isolating it before it causes a systemic failure of the "airframe" (the bank's network).
