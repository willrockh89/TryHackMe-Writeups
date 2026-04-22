### Lab: Web Attack Forensics — Log Analysis with Splunk

**Room Metadata**

  * **Platform:** [TryHackMe](https://tryhackme.com/)
  * **Category:** Blue Team / Forensics
  * **Room:** [Drone Alone (AoC 2025)](https://tryhackme.com/room/webattackforensics-aoc2025-b4t7c1d5f8)
  * **Difficulty:** Medium
  * **Status:** `Completed`

#### Objective

Utilize Splunk to investigate a Command Injection attack, analyzing Apache logs and Sysmon events to trace an attacker's path from a web request to OS-level reconnaissance.

#### Tools Used

  * **SIEM:** Splunk (Search Processing Language)
  * **Log Sources:** Apache Access/Error logs, Windows Sysmon
  * **Decoders:** Base64 web-based tools

#### Methodology

1.  **Log Interrogation:** Queried Apache access logs for PowerShell strings and decoded a Base64 payload revealing the attacker's intent.
2.  **Process Tracing:** Analyzed Sysmon events to find `httpd.exe` (Apache) spawning `cmd.exe`, confirming a successful exploit breakout.
3.  **Post-Exploitation Audit:** Identified the execution of `whoami.exe`, confirming the attacker was attempting to determine their privilege level.

#### Reflection

**Real-World Context:** Web forensics requires correlating multiple log sources to build a complete timeline. Monitoring for unusual parent-child process relationships—like a web server spawning a command shell—is a vital skill for detecting "Living off the Land" techniques.

