Network Connectivity Testing for Netcore Solutions
A practical networking project demonstrating IP configuration, DHCP setup, ACL implementation, and connectivity testing across multiple departments using Cisco Packet Tracer. This README summarizes the full workflow, results, and configurations performed.

Table of Contents
Project Overview

Network Topology

Tools and Technologies

Configuration Steps

Results and Findings

Author

Project Overview
This project focuses on building and testing a functional network for Netcore Solutions, consisting of Admin, Sales, and HR departments. The goal was to configure DHCP, assign IP addresses, verify inter‑department connectivity, and enforce communication restrictions using Access Control Lists (ACLs).

Network Topology
The network consists of:

1 Cisco 2911 Router

3 Cisco 2960 Switches (Admin, Sales, HR)

6 PCs (2 per department)

1 Server configured for DHCP and DNS

Key IP allocations (from the document):

Admin Network: 192.168.10.0/24

Sales Network: 192.168.20.0/24

HR Network: 192.168.30.0/24

DHCP Server: 192.168.10.2

DNS Server: 192.168.10.3

DHCP successfully assigned:

Admin PC2 → 192.168.10.11

Sales PC2 → 192.168.20.11

HR PC2 → 192.168.30.11

Tools and Technologies
Cisco Packet Tracer

Cisco 2911 Router

Cisco 2960 Switches

DHCP Server

DNS Server

Access Control Lists (ACLs)

Ping testing (ping)

IP helper configuration

Configuration Steps
Built the full network topology with router, switches, PCs, and server.

Configured the DHCP server to automatically assign IP addresses.

Connected Sales and HR networks to DHCP using ip helper-address.

Verified IP assignment on Admin, Sales, and HR PCs.

Performed connectivity tests using ping between departments.

Created an extended ACL named HR-ACL to restrict HR → Admin communication:

deny ip 192.168.30.0 0.0.0.255 192.168.10.0 0.0.0.255

permit ip 192.168.30.0 0.0.0.255 192.168.20.0 0.0.0.255

permit ip any any

Applied the ACL inbound on interface GigabitEthernet0/2 using:

ip access-group HR-ACL in

Re-tested connectivity to confirm ACL behavior.

Results and Findings
Successful communication from Sales → Admin (verified via ping).

Failed communication from HR → Admin due to ACL restrictions.

DHCP successfully assigned IP addresses across all departments.

ACL worked as intended, allowing HR → Sales communication while blocking HR → Admin.

The network topology operated correctly with all devices connected and functional.

Author
Abeeb Salaudeen  
Contact: salaudeenabeeb21@gmail.com
