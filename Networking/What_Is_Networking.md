# Lab: Identifying Devices on a Network

## Objective
Goal: Understand the dual-layer identification system of networked devices—IP Addresses (logical) and MAC Addresses (physical)—and demonstrate how MAC address spoofing can bypass weak network access controls.

## Tools Used
- Networking Concepts: IPv4, IPv6, MAC Addressing
- Techniques: MAC Spoofing
- Environment: TryHackMe Interactive Lab (Hotel Wi-Fi Simulation)

## Methodology
- **Identity Analysis**: Evaluated the difference between a "permeable" identity (IP Address) and a "fixed" identity (MAC Address/Physical Hardware Interface).
- **Public vs. Private Mapping**: Observed how multiple devices on a private network (using unique private IPs) egress to the internet through a single public IP provided by the ISP.
- **Hardware Fingerprinting**: Analyzed the 12-character hexadecimal structure of a MAC address, noting the Organizationally Unique Identifier (OUI) represented by the first six characters.
- **Access Control Bypass**:
  - Observed a simulated router blocking traffic from "Bob" (unauthorized) while allowing "Alice" (authorized).
  - Modified the unauthorized device's MAC address to match the authorized device's address.
  - Successfully bypassed the filter to gain network access.

## Key Findings
- **Flag Captured**: THM{YOU_GOT_ON_TRYHACKME}
- **Addressing Limitations**: IPv4 is limited to 2^32 addresses, necessitating the transition to IPv6 (2^128) to handle global device growth.
- **Security Vulnerability**: MAC-based filtering is inherently insecure because MAC addresses can be easily spoofed, allowing attackers to impersonate legitimate hardware.

## Reflection
Real-World Context: In a blue-team capacity, this lab highlights why MAC filtering should never be the sole line of defense for a network. Just as we use serial numbers for aerospace part accountability, we use MAC addresses for network accountability—but we must recognize that these "numbers" can be manipulated. For a secure environment, stronger authentication methods (like 802.1X) are required to ensure that the device on the wire is truly who they claim to be.