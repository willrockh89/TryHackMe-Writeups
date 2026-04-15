# Lab: Network Diagnostics with ICMP (Ping)
## Objective\
Goal: Utilize the Internet Control Message Protocol (ICMP) to verify connectivity between a local host and a remote target, and analyze the basic metrics of network latency.

## Tools Used\
Protocol: ICMP\

Utility: ping (Linux/Windows)\
Environment: TryHackMe Virtual Instance

## Methodology\
**Connectivity Check**: Issued the ping command followed by the target IP or domain name to initiate an echo request.\

**Path Analysis**: Observed the sequence of packets to identify potential packet loss.\

**Latency Evaluation**: Analyzed the Round-Trip Time (RTT) provided in the terminal output to gauge network performance.

## Key Findings\

**Tool Functionality**: Confirmed that ping uses ICMP Echo Request and Echo Reply packets.\

**Troubleshooting**: Identified that a lack of response doesn't always mean a host is down; it may indicate a firewall dropping ICMP packets for security hardening.\

**Metrics**: Successfully calculated average RTT to establish a baseline for "normal" network behavior.

## Reflection
Real-World Context: In a production environment, ping is the "first responder" tool. Much like checking for a spark in an aerospace engine, ping verifies the most basic level of "life" in a system. From a security perspective, understanding ICMP is vital for Blue Teamers to recognize how attackers might use "ping sweeps" for network mapping and how to properly configure firewalls to balance diagnostic needs with stealth.
