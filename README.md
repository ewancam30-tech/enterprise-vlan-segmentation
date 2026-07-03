# VLAN Segmentation

## Executive Summary

VLAN Segmentation is the third project in my Enterprise Network Engineering Portfolio and marks the transition from basic network deployment to enterprise switching technologies.

This project demonstrates how Virtual Local Area Networks (VLANs) can be used to logically segment a flat Layer 2 network into separate broadcast domains, improving network performance, scalability, security, and manageability.

The implementation includes VLAN creation, port assignment, 802.1Q trunking between switches, network verification, troubleshooting, and professional documentation following enterprise engineering standards.

---

# Key Takeaways

After completing this project, I demonstrated the ability to:

- Create and configure VLANs
- Assign switch ports to VLANs
- Configure IEEE 802.1Q trunk links
- Verify VLAN operation using Cisco IOS
- Understand broadcast domains
- Troubleshoot VLAN implementation issues
- Document enterprise switch deployments

---

# Engineering Change Request

**Request ID:** ECR-0003

**Priority:** Medium

**Requested By:** IT Infrastructure Manager

### Business Justification

Campbell Technologies has experienced significant organizational growth. All employees currently reside on a single flat network, resulting in excessive broadcast traffic and limited separation between departments.

To improve network performance and security while preparing for future expansion, the network must be segmented into multiple Virtual Local Area Networks (VLANs).

### Requested Solution

Implement VLAN segmentation for Management, Sales, and IT departments while maintaining Layer 2 connectivity within each department.

### Expected Business Benefits

- Reduced broadcast traffic
- Improved network performance
- Logical departmental separation
- Improved security
- Simplified administration
- Foundation for inter-VLAN routing

---

# Project Overview

This project demonstrates the implementation of VLAN segmentation using Cisco Catalyst switches.

The network was divided into multiple logical broadcast domains while maintaining physical connectivity through managed switches.

The project introduces enterprise switching concepts that serve as the foundation for future routing and security implementations.

---

# Project Objectives

- Create VLANs
- Name VLANs
- Configure access ports
- Configure trunk ports
- Verify VLAN database
- Verify trunk operation
- Test VLAN isolation
- Troubleshoot VLAN issues
- Save configurations
- Document implementation

---

# Network Architecture

## Architecture Overview

The network consists of two Cisco Catalyst 2960 switches connected through an IEEE 802.1Q trunk link.

Six workstations are divided among three departments:

- Management
- Sales
- IT

Each department is assigned its own VLAN, creating separate Layer 2 broadcast domains while sharing the same physical switching infrastructure.

The router is included in the topology but intentionally left unconfigured because inter-VLAN routing will be implemented in the next project.

---

## Design Rationale

The network was intentionally segmented to simulate a real enterprise environment.

The following design decisions were implemented:

- VLANs reduce unnecessary broadcast traffic.
- Departments are isolated for improved security.
- Trunk links transport multiple VLANs across switches.
- The design prepares the network for Router-on-a-Stick implementation in Project 4.
- A hierarchical approach allows future scalability.

---

# Equipment

| Device | Quantity |
|----------|---------|
| Cisco 1941 Router | 1 |
| Cisco Catalyst 2960 Switch | 2 |
| PC | 6 |
| Cisco Packet Tracer | 1 |

---

# VLAN Plan

| Department | VLAN | Network |
|------------|------|----------------|
| Management | 10 | 192.168.10.0/24 |
| Sales | 20 | 192.168.20.0/24 |
| IT | 30 | 192.168.30.0/24 |

---

# IP Addressing Plan

| Device | VLAN | IP Address |
|---------|------|-------------|
| PC1 | 10 | 192.168.10.10 |
| PC2 | 10 | 192.168.10.11 |
| PC3 | 20 | 192.168.20.10 |
| PC4 | 20 | 192.168.20.11 |
| PC5 | 30 | 192.168.30.10 |
| PC6 | 30 | 192.168.30.11 |

---

# Technologies Used

- Cisco IOS
- Cisco Packet Tracer
- IEEE 802.1Q
- VLAN
- Layer 2 Switching
- Trunking
- Cisco CLI

---

# Skills Demonstrated

- VLAN Creation
- VLAN Management
- Access Port Configuration
- Trunk Configuration
- Layer 2 Switching
- Broadcast Domain Segmentation
- Cisco IOS Administration
- Verification
- Troubleshooting
- Enterprise Documentation

---

# What This Project Demonstrates

This project demonstrates the ability to implement enterprise Layer 2 segmentation using Virtual Local Area Networks.

It showcases the ability to:

- Design segmented LANs
- Configure Cisco Catalyst switches
- Deploy IEEE 802.1Q trunks
- Verify switch operation
- Troubleshoot VLAN issues
- Prepare networks for Layer 3 routing

These are core skills expected of Network Engineers responsible for enterprise campus networks.

---

# Implementation Summary

## Switch Initialization

- Configured hostnames
- Configured passwords
- Disabled DNS lookup
- Configured MOTD banner

## VLAN Configuration

- Created VLAN 10
- Created VLAN 20
- Created VLAN 30

## Port Assignment

- Assigned Management ports
- Assigned Sales ports
- Assigned IT ports

## Trunk Configuration

- Configured IEEE 802.1Q trunk
- Allowed VLANs 10,20,30

## Validation

- Verified VLAN database
- Verified trunk operation
- Verified MAC Address learning
- Verified connectivity
- Verified VLAN isolation

---

# Verification Methodology

After configuration, verification commands were executed to confirm:

- VLAN creation
- VLAN membership
- Trunk operation
- Port assignments
- MAC address learning
- End-to-end connectivity
- Broadcast isolation

---

# Verification Commands

show vlan brief

show interfaces trunk

show interfaces switchport

show mac address-table

show running-config

show startup-config

---

# Screenshots

Include screenshots for:

- Final topology
  <img width="398" height="251" alt="image" src="https://github.com/user-attachments/assets/057ad578-6caa-4ef5-bf11-a9958126bd6c" />

- VLAN database
  <img width="291" height="116" alt="image" src="https://github.com/user-attachments/assets/5dea5d97-4a12-40ee-96d8-f5c6bf3e1b26" />
  <img width="290" height="113" alt="image" src="https://github.com/user-attachments/assets/25e28520-396e-4fe7-b6e6-def8ed7233e5" />

- Trunk configuration
  <img width="259" height="88" alt="image" src="https://github.com/user-attachments/assets/000f2cf3-52f5-485f-8704-20cfedaff0c5" />
  <img width="266" height="85" alt="image" src="https://github.com/user-attachments/assets/983252c7-3475-48cb-b2aa-c9cbe60116be" />


- Switch 1 running configuration
  <img width="199" height="395" alt="image" src="https://github.com/user-attachments/assets/3f2bc908-afd2-4c67-8fe1-8513349cf870" />
  <img width="153" height="410" alt="image" src="https://github.com/user-attachments/assets/f722ed7a-1199-4af0-b509-0cb940a87103" />
  <img width="207" height="191" alt="image" src="https://github.com/user-attachments/assets/62848e8b-84c7-4b7e-8ff5-d35fa09dffb3" />

- Switch 2 running configuration
  <img width="194" height="389" alt="image" src="https://github.com/user-attachments/assets/652c6237-9598-40eb-9d8c-5422adaf5428" />
  <img width="204" height="298" alt="image" src="https://github.com/user-attachments/assets/49bbce80-1b04-49dd-9a34-4fc82812ac3d" />

- Successful ping within VLAN 10
  <img width="221" height="97" alt="image" src="https://github.com/user-attachments/assets/dd625998-dfb7-46b4-94a9-9c8330eca413" />
  <img width="212" height="91" alt="image" src="https://github.com/user-attachments/assets/6239f134-68bd-4e89-9c06-d95801e65dc9" />

- Successful ping within VLAN 20
  <img width="209" height="93" alt="image" src="https://github.com/user-attachments/assets/0b2f2391-1e38-4387-9b58-23eab2d7b0dc" />
  <img width="211" height="94" alt="image" src="https://github.com/user-attachments/assets/2e34e461-8822-4982-b669-fb5fe8401b52" />


- Successful ping within VLAN 30
  <img width="209" height="90" alt="image" src="https://github.com/user-attachments/assets/0ecf6dd3-d097-4166-9b60-9ec2ae1aa66f" />
  <img width="206" height="92" alt="image" src="https://github.com/user-attachments/assets/9cae40ae-c9f9-49b5-bdee-95879eb0dc6f" />


- Failed ping between VLANs
  <img width="216" height="83" alt="image" src="https://github.com/user-attachments/assets/49533fd7-abb7-4ea1-a8a6-44ca8444e850" />
  <img width="217" height="82" alt="image" src="https://github.com/user-attachments/assets/1c43d253-918e-40b4-ae88-234639f6867a" />
  <img width="209" height="79" alt="image" src="https://github.com/user-attachments/assets/0592e370-2c1e-4d9c-9088-b4a81f1ed264" />



- MAC Address Table
<img width="176" height="83" alt="image" src="https://github.com/user-attachments/assets/7112c5dd-b4e7-43fd-8ef3-eda87ba1bd77" />
<img width="170" height="62" alt="image" src="https://github.com/user-attachments/assets/3529cf95-4d28-48cd-8b1e-9df9fb6b02c0" />


Each screenshot should include:

- Purpose
- Commands Used
- Verification
- Skills Demonstrated
- Business Value

---

# Troubleshooting Case Studies

## Incorrect VLAN Assignment

Problem

PC assigned to the wrong VLAN.

Resolution

Assigned the correct access VLAN.

---

## Trunk Misconfiguration

Problem

Trunk configured as an access port.

Resolution

Configured:

switchport mode trunk

---

## Missing VLAN

Problem

VLAN not created on Switch 2.

Resolution

Created VLAN and verified database.

---

## Native VLAN Mismatch

Problem

Switches reported native VLAN mismatch.

Resolution

Configured matching native VLANs.

---

## Incorrect IP Address

Problem

Host configured with incorrect subnet.

Resolution

Assigned correct IPv4 address.

---

# Engineer's Reflection

This project reinforced the importance of logical network segmentation in enterprise environments.

Although all devices remained physically connected, VLAN implementation demonstrated how broadcast domains can be separated without additional hardware.

Understanding VLAN behavior establishes the foundation for future projects involving Router-on-a-Stick, inter-VLAN routing, ACL implementation, and enterprise routing protocols.

---

# Interview Questions

Why are VLANs used?

What is a broadcast domain?

What is an access port?

What is a trunk port?

What protocol does Cisco use for VLAN trunking?

Why can't devices in different VLANs communicate?

How do you verify VLAN membership?

What command verifies trunk links?

---

# Common IOS Commands Used

enable

configure terminal

vlan

name

interface

switchport mode access

switchport access vlan

switchport mode trunk

switchport trunk allowed vlan

show vlan brief

show interfaces trunk

show interfaces switchport

show mac address-table

copy running-config startup-config

---

# Production Considerations

A production deployment would additionally include:

- VTP
- Port Security
- BPDU Guard
- Root Guard
- Storm Control
- DHCP Snooping
- Dynamic ARP Inspection
- Private VLANs
- AAA Authentication
- SNMP Monitoring
- Syslog Logging
- Configuration Backups

---

# Future Enhancements

Future projects will build directly on this implementation by introducing:

- Inter-VLAN Routing
- Router-on-a-Stick
- Layer 3 Switching
- ACL Implementation
- DHCP
- Enterprise Routing Protocols

---

# Project Roadmap

(Use the roadmap template we standardized with Cisco Device Basics, updating the status so both **Cisco Device Basics** and **Small Office Network Deployment** are marked 🟩 Completed, and **VLAN Segmentation** is marked 🟨 Current Repository.)

---

# Final Outcome

This project demonstrates the implementation of enterprise VLAN segmentation using Cisco Catalyst switches while following industry-standard configuration, verification, troubleshooting, and documentation practices.

Rather than functioning as an isolated Packet Tracer exercise, this repository represents another milestone in a structured Enterprise Network Engineering Portfolio that progressively develops the skills required of a professional Network Engineer.
