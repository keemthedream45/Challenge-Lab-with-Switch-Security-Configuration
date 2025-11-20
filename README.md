# Challenge-Lab-with-Switch-Security-Configuration
Scenario Overview – “Secure Multi-VLAN Small Business Network”

# Switch Security & VLAN Routing Lab – PT Practice

A small business is expanding its internal network into multiple departments. To improve segmentation and security, the company is moving from a flat Layer 2 network to one that uses VLANs, trunking, switch security controls, and inter-VLAN routing. Router R1 will act as the central default gateway using a router-on-a-stick design, while switches S1 and S2 must be hardened to protect against misconfigurations, unauthorized connections, and Layer 2 attacks.

# Objective

This lab develops hands-on skills in VLAN configuration, switch security, trunking, and multi-LAN routing. The primary focus is securing Layer 2 access ports, implementing VLAN segmentation, enabling safe trunk connections, and verifying successful communication between different departments.

# Skills Learned

- VLAN Implementation

  - Creating VLANs for Admin, Staff, Management, and ParkingLot

  - Assigning ports and verifying VLAN membership with show vlan brief

- Inter-VLAN Routing

  - Configuring router-on-a-stick subinterfaces

  - Assigning gateways for each VLAN and verifying inter-VLAN communication

- Switch Security Hardening

  - Enabling port security (sticky MAC, maximum MAC limit, violation actions)

  - Configuring PortFast and BPDU Guard on edge ports

  - Shutting down unused interfaces and moving them to a ParkingLot VLAN

 - Trunking & Native VLAN

    - Configuring 802.1Q trunks between switches and the router

    - Setting native VLANs and allowed VLAN lists

- Network Verification

  - show port-security

  - show spanning-tree

  - ipconfig on PCs

  - ping across VLANs

# Tools Used

- Cisco Packet Tracer – Build full topology & configure switches/routers

- Cisco IOS CLI – VLANs, trunks, port security, inter-VLAN routing

- Windows PC Simulation – Validate DHCP/IP configuration

- Ping Utility – Test cross-VLAN connectivity

- Show Commands – Validate trunking, VLAN membership, STP, and port security

# Topology

<img width="717" height="695" alt="Screenshot 2025-11-19 225802" src="https://github.com/user-attachments/assets/20d4ee21-ba57-4af7-a864-9fd279530a1e" />

# Steps
Step 1 – Configuring VLANs and Management Access

Created the required VLANs to segment the network:

- VLAN 10 – Admin

- VLAN 20 – Staff

- VLAN 99 – Management

- VLAN 1000 – ParkingLot (for unused ports)

SVIs were configured on each switch for management via VLAN 99, including IP addressing and default gateways pointing to R1.

Step 2 – Securing the Access Layer

All unused ports were placed into the ParkingLot VLAN (1000) and shut down:



Port Security on User-Facing Ports

Two important user-facing ports were secured:

- S1 F0/6

- S2 F0/18

Security applied:

- Maximum 2 MACs

- Sticky MAC learning

- Violation mode: protect or restrict (lab dependent)



Step 3 – Trunking and Inter-Switch Connectivity

Configured trunks on S1 and S2:

- Allowed VLANs: 10, 20, 99

- Native VLAN: 99 (as required by the scenario)


<img width="212" height="621" alt="Screenshot 2025-11-19 231501" src="https://github.com/user-attachments/assets/47806c2a-fe08-4f93-abfb-ab2c0e88e165" />

<img width="628" height="561" alt="Screenshot 2025-11-19 231621" src="https://github.com/user-attachments/assets/c8a02480-009e-4749-9397-a61edf643811" />

  
