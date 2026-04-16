# Lab: Web Attack Forensics — Drone Alone

## Objective
**Goal:** Utilize **Splunk** to investigate a Command Injection attack against a web server. The objective is to analyze Apache access/error logs and Sysmon process events to trace the attacker's path from initial web request to OS-level reconnaissance.

## Tools Used
* **SIEM:** [Splunk](https://www.splunk.com/)
* **Log Sources:** * `windows_apache_access`: Web traffic logs.
    * `windows_apache_error`: Server-side error logs.
    * `windows_sysmon`: Detailed process creation and command-line logs.
* **Decoder:** [Base64Decode.org](https://www.base64decode.org/)
* **Environment:** [TryHackMe Advent of Cyber 2025 - Day 15](https://tryhackme.com/room/webattackforensics-aoc2025-b4t7c1d5f8)

## Methodology

### 1. Detecting Suspicious Web Commands
Initiated a search in the Apache access logs for high-risk strings associated with command execution.
* **Splunk Query:** `index=windows_apache_access (cmd.exe OR powershell OR "powershell.exe" OR "Invoke-Expression")`
* **Findings:** Identified requests to a CGI script (`hello.bat`) containing encoded PowerShell payloads. 
* **Decoding:** Extracted the string `VABoAGkAcwAgAGkAcwAgAG4AbwB3ACAATQBpAG4AZQAhACAATQBVAEEASABBAEEASABBAEEA` and decoded it to reveal the attacker's message: *"This is now Mine! MUHAHAHAHA"*.

### 2. Analyzing Server-Side Errors
Inspected error logs to confirm if the malicious requests were processed by the backend.
* **Splunk Query:** `index=windows_apache_error ("cmd.exe" OR "powershell" OR "Internal Server Error")`
* **Observation:** Found "500 Internal Server Error" messages corresponding to the injection attempts, indicating the server attempted to execute the input but failed or produced unexpected output.

### 3. Tracing Process Creation
Investigated process lineage to see if the web server (`httpd.exe`) spawned unauthorized child processes.
* **Splunk Query:** `index=windows_sysmon ParentImage="*httpd.exe"`
* **Discovery:** Confirmed that `httpd.exe` (Apache) successfully spawned `cmd.exe` and `powershell.exe`. This is a definitive indicator of a successful **Command Injection** exploit.

### 4. Confirming Attacker Reconnaissance
Searched for common post-exploitation commands used to identify user privileges.
* **Splunk Query:** `index=windows_sysmon *cmd.exe* *whoami*`
* **Findings:** Captured logs of the `whoami.exe` executable being run, confirming the attacker was attempting to determine their current permission level on the compromised host.

## Key Findings
* **Reconnaissance Executable:** `whoami.exe`
* **Injection Payload:** `PowerShell.exe`
* **Vulnerability:** The `hello.bat` CGI script was susceptible to command injection, allowing remote attackers to breakout of the web context into the Windows OS.
* **Evasion Technique:** The attacker utilized **Base64 encoding** to obfuscate their PowerShell commands and bypass simple string-based detection.

## Reflection
**Real-World Context:** Web attack forensics requires correlating multiple log sources to build a complete timeline. An alert in the web logs (Access) becomes an incident when confirmed by system-level telemetry (Sysmon). From a Blue Team perspective, monitoring for unusual parent-child process relationships (like a Web Server spawning a Command Shell) is one of the most effective ways to detect "Living off the Land" techniques and web shell activity.

