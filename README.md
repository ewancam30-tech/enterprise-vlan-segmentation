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

The network consists of two Cisco Catalyst 2911 switches connected through an IEEE 802.1Q trunk link.

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
| Cisco Catalyst 2911 Switch | 2 |
| PC | 6 |
| Cisco Packet Tracer | 1 |

---

## VLAN Plan

The VLAN plan separates the network into three departmental broadcast domains. Each department is assigned a unique VLAN ID and IP subnet to improve organization, reduce unnecessary broadcast traffic, and prepare the environment for future inter-VLAN routing.

| Department | VLAN ID | VLAN Name | Network | Purpose |
|---|---:|---|---|---|
| Management | 10 | Management | 192.168.10.0/24 | Administrative and leadership users |
| Sales | 20 | Sales | 192.168.20.0/24 | Sales department users |
| IT | 30 | IT | 192.168.30.0/24 | Technical support and infrastructure users |

### Design Explanation

This VLAN plan was designed to simulate a common enterprise segmentation model where departments are logically separated while sharing the same physical switching infrastructure.

Each VLAN acts as its own broadcast domain. Devices within the same VLAN can communicate with one another, while devices in different VLANs cannot communicate unless Layer 3 routing is configured.

In this project, inter-VLAN routing is intentionally not configured. This allows the VLAN segmentation to be tested and verified before routing is introduced in the next project.

### Expected Communication Behavior

| Source | Destination | Expected Result | Reason |
|---|---|---|---|
| VLAN 10 device | VLAN 10 device | Successful | Same VLAN |
| VLAN 20 device | VLAN 20 device | Successful | Same VLAN |
| VLAN 30 device | VLAN 30 device | Successful | Same VLAN |
| VLAN 10 device | VLAN 20 device | Failed | Different VLANs, no routing configured |
| VLAN 20 device | VLAN 30 device | Failed | Different VLANs, no routing configured |
| VLAN 10 device | VLAN 30 device | Failed | Different VLANs, no routing configured |

The failed pings between different VLANs are expected and confirm that VLAN isolation is working correctly.

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

This project demonstrates the practical Layer 2 networking skills required to design, configure, verify, and troubleshoot VLAN-based enterprise networks using Cisco IOS. Rather than simply configuring switch commands, the implementation emphasizes the engineering principles behind network segmentation, scalability, and security.

Each skill developed during this project builds upon the foundational knowledge established in previous projects while preparing the network for future Layer 3 routing and enterprise infrastructure services.

| Skill | Description |
|--------|-------------|
| Cisco IOS Administration | Configured Cisco Catalyst switches using the Cisco IOS command-line interface to perform enterprise switch administration tasks. |
| VLAN Creation | Created multiple Virtual Local Area Networks (VLANs) to logically separate departments while sharing the same physical switching infrastructure. |
| VLAN Management | Assigned descriptive VLAN names and maintained an organized VLAN database for simplified administration and future scalability. |
| Access Port Configuration | Configured switch access ports and assigned end-user devices to the appropriate departmental VLANs. |
| IEEE 802.1Q Trunking | Configured trunk links between switches to transport traffic for multiple VLANs across a single physical connection. |
| Layer 2 Network Segmentation | Divided a flat network into separate broadcast domains, improving network organization, reducing unnecessary broadcasts, and enhancing security. |
| Broadcast Domain Management | Demonstrated how VLANs contain broadcast traffic within individual departments, improving network efficiency. |
| Network Verification | Verified VLAN creation, port assignments, trunk status, MAC address learning, and connectivity using Cisco IOS verification commands. |
| Network Troubleshooting | Diagnosed and corrected common VLAN implementation issues including incorrect VLAN assignments, trunk misconfigurations, and addressing problems. |
| Enterprise Documentation | Produced structured technical documentation describing the design decisions, implementation process, verification methodology, troubleshooting procedures, and lessons learned. |

## Professional Competencies Developed

Beyond the technical configuration tasks, this project strengthened several professional engineering competencies commonly expected in enterprise networking environments.

- Translating business requirements into technical network designs
- Applying structured implementation methodologies
- Verifying configurations before deployment
- Troubleshooting using a systematic approach
- Documenting engineering decisions and implementation steps
- Communicating technical concepts clearly through professional documentation

## Why These Skills Matter

Enterprise networks are designed to support growth, improve security, and simplify administration. VLAN segmentation is one of the most fundamental technologies used to achieve these goals.

By completing this project, I demonstrated the ability to implement logical network segmentation using industry-standard Cisco technologies while following enterprise configuration, verification, and documentation practices.

These skills provide the foundation for future projects involving:

- Inter-VLAN Routing
- Layer 3 Switching
- Spanning Tree Protocol (STP)
- EtherChannel
- Access Control Lists (ACLs)
- Dynamic Routing Protocols
- Enterprise Campus Networks

This project represents the transition from basic network configuration to enterprise switching technologies and establishes the groundwork for the advanced networking concepts introduced throughout the remainder of this portfolio.

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

# Skills Demonstrated

This project demonstrates the practical Layer 2 networking skills required to design, configure, verify, and troubleshoot VLAN-based enterprise networks using Cisco IOS. Rather than simply configuring switch commands, the implementation emphasizes the engineering principles behind network segmentation, scalability, and security.

Each skill developed during this project builds upon the foundational knowledge established in previous projects while preparing the network for future Layer 3 routing and enterprise infrastructure services.

| Skill | Description |
|--------|-------------|
| Cisco IOS Administration | Configured Cisco Catalyst switches using the Cisco IOS command-line interface to perform enterprise switch administration tasks. |
| VLAN Creation | Created multiple Virtual Local Area Networks (VLANs) to logically separate departments while sharing the same physical switching infrastructure. |
| VLAN Management | Assigned descriptive VLAN names and maintained an organized VLAN database for simplified administration and future scalability. |
| Access Port Configuration | Configured switch access ports and assigned end-user devices to the appropriate departmental VLANs. |
| IEEE 802.1Q Trunking | Configured trunk links between switches to transport traffic for multiple VLANs across a single physical connection. |
| Layer 2 Network Segmentation | Divided a flat network into separate broadcast domains, improving network organization, reducing unnecessary broadcasts, and enhancing security. |
| Broadcast Domain Management | Demonstrated how VLANs contain broadcast traffic within individual departments, improving network efficiency. |
| Network Verification | Verified VLAN creation, port assignments, trunk status, MAC address learning, and connectivity using Cisco IOS verification commands. |
| Network Troubleshooting | Diagnosed and corrected common VLAN implementation issues including incorrect VLAN assignments, trunk misconfigurations, and addressing problems. |
| Enterprise Documentation | Produced structured technical documentation describing the design decisions, implementation process, verification methodology, troubleshooting procedures, and lessons learned. |

## Professional Competencies Developed

Beyond the technical configuration tasks, this project strengthened several professional engineering competencies commonly expected in enterprise networking environments.

- Translating business requirements into technical network designs
- Applying structured implementation methodologies
- Verifying configurations before deployment
- Troubleshooting using a systematic approach
- Documenting engineering decisions and implementation steps
- Communicating technical concepts clearly through professional documentation

## Why These Skills Matter

Enterprise networks are designed to support growth, improve security, and simplify administration. VLAN segmentation is one of the most fundamental technologies used to achieve these goals.

By completing this project, I demonstrated the ability to implement logical network segmentation using industry-standard Cisco technologies while following enterprise configuration, verification, and documentation practices.

These skills provide the foundation for future projects involving:

- Inter-VLAN Routing
- Layer 3 Switching
- Spanning Tree Protocol (STP)
- EtherChannel
- Access Control Lists (ACLs)
- Dynamic Routing Protocols
- Enterprise Campus Networks

This project represents the transition from basic network configuration to enterprise switching technologies and establishes the groundwork for the advanced networking concepts introduced throughout the remainder of this portfolio.
---

# Screenshot Documentation

The screenshots below provide visual evidence of the VLAN implementation, verification commands, trunk configuration, connectivity testing, and VLAN isolation results.

- ## Final Network Topology

<img width="398" height="251" alt="Final VLAN topology" src="https://github.com/user-attachments/assets/057ad578-6caa-4ef5-bf11-a9958126bd6c" />

**Purpose:**  
Displays the completed enterprise VLAN segmentation topology.

**Verification:**  
The topology confirms that two Cisco Catalyst switches are connected by a trunk link and that end devices are assigned to departmental VLANs.

**Skills Demonstrated:**  
Network design, Layer 2 switching, VLAN planning, and topology documentation.

**Business Value:**  
This design allows multiple departments to share the same switching infrastructure while remaining logically separated.

- ## VLAN Database Verification

<img width="291" height="116" alt="SW1 VLAN database" src="https://github.com/user-attachments/assets/5dea5d97-4a12-40ee-96d8-f5c6bf3e1b26" />
<img width="290" height="113" alt="SW2 VLAN database" src="https://github.com/user-attachments/assets/25e28520-396e-4fe7-b6e6-def8ed7233e5" />

**Purpose:**  
Verifies that VLAN 10, VLAN 20, and VLAN 30 were created successfully.

**Commands Used:**  
`show vlan brief`

**Verification:**  
The output confirms VLAN names and access-port assignments.

**Skills Demonstrated:**  
VLAN creation, VLAN naming, port assignment, and switch verification.

**Business Value:**  
Proper VLAN organization supports departmental separation and reduces unnecessary broadcast traffic.

- ## Trunk Configuration Verification

<img width="259" height="88" alt="SW1 trunk verification" src="https://github.com/user-attachments/assets/000f2cf3-52f5-485f-8704-20cfedaff0c5" />
<img width="266" height="85" alt="SW2 trunk verification" src="https://github.com/user-attachments/assets/983252c7-3475-48cb-b2aa-c9cbe60116be" />

**Purpose:**  
Verifies that the inter-switch link is operating as an 802.1Q trunk.

**Commands Used:**  
`show interfaces trunk`

**Verification:**  
The trunk output confirms that VLAN traffic can pass between switches.

**Skills Demonstrated:**  
802.1Q trunking, multi-switch VLAN transport, and trunk verification.

**Business Value:**  
Trunk links allow VLANs to span multiple switches, supporting enterprise scalability.


- Switch 1 running configuration
  <img width="199" height="395" alt="image" src="https://github.com/user-attachments/assets/3f2bc908-afd2-4c67-8fe1-8513349cf870" />
  <img width="153" height="410" alt="image" src="https://github.com/user-attachments/assets/f722ed7a-1199-4af0-b509-0cb940a87103" />
  <img width="207" height="191" alt="image" src="https://github.com/user-attachments/assets/62848e8b-84c7-4b7e-8ff5-d35fa09dffb3" />

- Switch 2 running configuration
  <img width="194" height="389" alt="image" src="https://github.com/user-attachments/assets/652c6237-9598-40eb-9d8c-5422adaf5428" />
  <img width="204" height="298" alt="image" src="https://github.com/user-attachments/assets/49bbce80-1b04-49dd-9a34-4fc82812ac3d" />

**Purpose:**  
Documents the completed configurations for SW1 and SW2.

**Commands Used:**  
`show running-config`

**Verification:**  
The running configurations confirm hostnames, VLAN assignments, trunk configuration, access ports, and saved implementation details.

**Skills Demonstrated:**  
Cisco IOS administration, configuration review, switch deployment, and technical documentation.

**Business Value:**  
Configuration documentation supports troubleshooting, auditing, and future network changes.

- Successful ping within VLAN 10
  <img width="221" height="97" alt="image" src="https://github.com/user-attachments/assets/dd625998-dfb7-46b4-94a9-9c8330eca413" />
  <img width="212" height="91" alt="image" src="https://github.com/user-attachments/assets/6239f134-68bd-4e89-9c06-d95801e65dc9" />

- Successful ping within VLAN 20
  <img width="209" height="93" alt="image" src="https://github.com/user-attachments/assets/0b2f2391-1e38-4387-9b58-23eab2d7b0dc" />
  <img width="211" height="94" alt="image" src="https://github.com/user-attachments/assets/2e34e461-8822-4982-b669-fb5fe8401b52" />


- Successful ping within VLAN 30
  <img width="209" height="90" alt="image" src="https://github.com/user-attachments/assets/0ecf6dd3-d097-4166-9b60-9ec2ae1aa66f" />
  <img width="206" height="92" alt="image" src="https://github.com/user-attachments/assets/9cae40ae-c9f9-49b5-bdee-95879eb0dc6f" />
## Successful Same-VLAN Connectivity Tests

**Purpose:**  
Confirms that devices within the same VLAN can communicate.

**Commands Used:**  
`ping`

**Verification:**  
Successful replies within VLAN 10, VLAN 20, and VLAN 30 confirm correct access-port assignments and Layer 2 connectivity.

**Skills Demonstrated:**  
Connectivity testing, VLAN validation, and endpoint verification.

**Business Value:**  
Users within the same department can communicate while remaining separated from other departments.

- Failed ping between VLANs
  <img width="216" height="83" alt="image" src="https://github.com/user-attachments/assets/49533fd7-abb7-4ea1-a8a6-44ca8444e850" />
  <img width="217" height="82" alt="image" src="https://github.com/user-attachments/assets/1c43d253-918e-40b4-ae88-234639f6867a" />
  <img width="209" height="79" alt="image" src="https://github.com/user-attachments/assets/0592e370-2c1e-4d9c-9088-b4a81f1ed264" />
## Failed Inter-VLAN Connectivity Tests

**Purpose:**  
Confirms that devices in different VLANs cannot communicate without Layer 3 routing.

**Commands Used:**  
`ping`

**Verification:**  
Failed pings between VLANs are expected because inter-VLAN routing has not been configured yet.

**Skills Demonstrated:**  
VLAN isolation, broadcast-domain separation, and Layer 2 segmentation validation.

**Business Value:**  
Departmental separation improves security and prepares the network for controlled routing in the next project.


-## MAC Address Table Verification

<img width="176" height="83" alt="SW1 MAC address table" src="https://github.com/user-attachments/assets/7112c5dd-b4e7-43fd-8ef3-eda87ba1bd77" />
<img width="170" height="62" alt="SW2 MAC address table" src="https://github.com/user-attachments/assets/3529cf95-4d28-48cd-8b1e-9df9fb6b02c0" />

**Purpose:**  
Verifies that the switches are learning MAC addresses from connected devices.

**Commands Used:**  
`show mac address-table`

**Verification:**  
The MAC address table confirms Layer 2 learning and shows which switch ports are associated with endpoint devices.

**Skills Demonstrated:**  
Layer 2 verification, MAC address learning, and switch troubleshooting.

**Business Value:**  
MAC address verification helps network engineers confirm device connectivity and troubleshoot switching issues.

---

# Troubleshooting Case Studies

Troubleshooting is a fundamental responsibility of every Network Engineer. During enterprise deployments, configuration errors, connectivity issues, and verification failures are expected and must be resolved systematically before the implementation can be considered successful.

The following case studies document common VLAN implementation issues that may occur during deployment, the investigative process used to identify each issue, and the corrective actions taken to restore proper network operation.

These scenarios demonstrate not only technical configuration skills but also structured troubleshooting methodologies commonly used in enterprise networking environments.

---

## Case Study 1 – Incorrect VLAN Assignment

### Problem

A workstation was unable to communicate with another workstation that belonged to the same department.

### Symptoms

- Successful physical link
- Interface operational
- Ping requests failed
- MAC address learned on the switch

### Investigation

The switch configuration was reviewed using:

```text
show vlan brief
```

The output revealed that the workstation's switch port had been assigned to the wrong VLAN.

### Root Cause

The access port was configured for an incorrect VLAN.

### Resolution

The switch port was reassigned to the correct VLAN using:

```text
interface FastEthernet0/x
switchport mode access
switchport access vlan 10
```

### Verification

Connectivity was verified using ICMP ping tests.

### Lesson Learned

Always verify VLAN assignments before investigating higher-layer network issues.

---

## Case Study 2 – Trunk Misconfiguration

### Problem

Devices connected to different switches within the same VLAN could not communicate.

### Symptoms

- VLANs existed on both switches.
- Access ports were correctly assigned.
- Same-VLAN communication failed across switches.

### Investigation

The trunk status was verified using:

```text
show interfaces trunk
```

The output indicated that the inter-switch connection had been configured as an access port rather than a trunk.

### Root Cause

The trunk interface had not been configured for IEEE 802.1Q trunking.

### Resolution

The interface was configured as a trunk:

```text
interface FastEthernet0/24
switchport mode trunk
switchport trunk allowed vlan 10,20,30
```

### Verification

The trunk status was verified and same-VLAN communication between switches was successfully restored.

### Lesson Learned

Trunk links are required whenever multiple VLANs must traverse a single physical connection.

---

## Case Study 3 – Missing VLAN

### Problem

One department could not communicate after the implementation was completed.

### Symptoms

- Switch interfaces appeared operational.
- Trunk was functioning.
- One VLAN was missing from the switch database.

### Investigation

The VLAN database was reviewed using:

```text
show vlan brief
```

The missing VLAN was identified immediately.

### Root Cause

The VLAN had not been created on the second switch.

### Resolution

The missing VLAN was created and assigned the appropriate name before reconnecting the access ports.

### Verification

The VLAN database was reviewed again and connectivity testing confirmed successful communication.

### Lesson Learned

Every switch participating in a VLAN environment must contain the same VLAN database unless a centralized management solution is used.

---

## Case Study 4 – Native VLAN Mismatch

### Problem

The switches generated native VLAN mismatch warnings.

### Symptoms

- Trunk operational
- Warning messages displayed
- Potential communication inconsistencies

### Investigation

The trunk configuration on both switches was reviewed.

### Root Cause

The native VLAN configuration differed between switches.

### Resolution

Both trunk interfaces were configured to use the same native VLAN.

### Verification

The warning messages disappeared and the trunk continued operating normally.

### Lesson Learned

Consistent trunk configurations are essential for stable Layer 2 communication.

---

## Case Study 5 – Incorrect IP Addressing

### Problem

A workstation could not communicate with another workstation within the same VLAN.

### Symptoms

- Switch configuration correct
- VLAN assignment correct
- Ping requests failed

### Investigation

The workstation's IP configuration was reviewed.

### Root Cause

The workstation had been assigned an incorrect IP address and subnet mask.

### Resolution

The correct IPv4 addressing information was applied.

### Verification

Connectivity testing confirmed successful communication.

### Lesson Learned

Always verify end-device addressing before assuming a switching problem exists.
---

# Project Roadmap

(Use the roadmap template we standardized with Cisco Device Basics, updating the status so both **Cisco Device Basics** and **Small Office Network Deployment** are marked 🟩 Completed, and **VLAN Segmentation** is marked 🟨 Current Repository.)

---
# Engineer's Reflection

This project represents an important transition from basic Cisco device configuration to enterprise switching technologies.

Although the physical network infrastructure remained unchanged, VLAN implementation demonstrated how logical segmentation can significantly improve network organization, security, scalability, and operational efficiency.

One of the most valuable lessons learned was understanding that VLANs separate broadcast domains rather than creating additional physical networks. Through verification and troubleshooting, I developed a deeper appreciation for the importance of systematic validation and structured problem solving during network deployments.

The implementation also highlighted the relationship between Layer 2 switching and future Layer 3 routing. While devices within the same VLAN communicated successfully, communication between different VLANs remained intentionally unavailable until routing services are introduced.

This project establishes the technical foundation for the next stage of the portfolio, where Router-on-a-Stick and Inter-VLAN Routing will enable controlled communication between departmental networks while preserving the benefits of VLAN segmentation.

# Interview Questions & Model Answers

## 1. Why are VLANs used in enterprise networks?

VLANs logically separate devices into different broadcast domains without requiring additional physical switches. This improves security, reduces broadcast traffic, and simplifies network administration.

---

## 2. What is a broadcast domain?

A broadcast domain is the group of devices that receive broadcast traffic sent by another device. Each VLAN creates its own broadcast domain.

---

## 3. What is the difference between an access port and a trunk port?

An access port belongs to a single VLAN and typically connects end-user devices. A trunk port carries traffic for multiple VLANs between network devices using IEEE 802.1Q tagging.

---

## 4. Why can't devices in different VLANs communicate?

Each VLAN is a separate Layer 2 broadcast domain. Communication between VLANs requires a Layer 3 device, such as a router or Layer 3 switch.

---

## 5. What protocol is used for VLAN trunking?

IEEE 802.1Q is the industry-standard protocol used to identify VLAN traffic across trunk links.

---

## 6. Which command verifies VLAN membership?

```text
show vlan brief
```

---

## 7. Which command verifies trunk links?

```text
show interfaces trunk
```

---

## 8. Which command verifies MAC address learning?

```text
show mac address-table
```
# Common IOS Commands Used

| Command | Purpose |
|---------|---------|
| `enable` | Enter privileged EXEC mode. |
| `configure terminal` | Enter global configuration mode. |
| `vlan` | Create or modify a VLAN. |
| `name` | Assign a descriptive name to a VLAN. |
| `interface` | Select an interface for configuration. |
| `switchport mode access` | Configure an interface as an access port. |
| `switchport access vlan` | Assign an access port to a VLAN. |
| `switchport mode trunk` | Configure an interface as a trunk port. |
| `switchport trunk allowed vlan` | Specify which VLANs may traverse the trunk. |
| `show vlan brief` | Display VLAN information and port assignments. |
| `show interfaces trunk` | Verify trunk status and allowed VLANs. |
| `show interfaces switchport` | Display switchport operational settings. |
| `show mac address-table` | View dynamically learned MAC addresses. |
| `show running-config` | Display the active device configuration. |
| `show startup-config` | Display the saved configuration stored in NVRAM. |
| `copy running-config startup-config` | Save the current configuration for persistence after reboot. |
# Production Considerations

The implementation in this project focuses on foundational VLAN segmentation. In a production environment, additional security, monitoring, and resiliency features would be incorporated to improve operational stability and protect the network infrastructure.

Recommended enhancements include:

- VLAN Trunking Protocol (VTP) for centralized VLAN management
- Port Security to prevent unauthorized devices from connecting to access ports
- BPDU Guard and Root Guard to protect the Spanning Tree topology
- Storm Control to mitigate broadcast, multicast, and unknown unicast storms
- DHCP Snooping to prevent rogue DHCP servers
- Dynamic ARP Inspection (DAI) to reduce ARP spoofing attacks
- AAA authentication using TACACS+ or RADIUS for centralized administrative access
- SNMP for proactive network monitoring
- Syslog for centralized event logging
- Automated configuration backups and version control
- Network Time Protocol (NTP) for synchronized device timestamps
- Redundant uplinks using EtherChannel for improved availability
# Future Enhancements

This project serves as the foundation for the next phase of the Enterprise Network Engineering Portfolio.

Upcoming projects will expand this implementation by introducing:

- Router-on-a-Stick to enable Inter-VLAN Routing
- Layer 3 switching concepts
- Access Control Lists (ACLs) for traffic filtering between VLANs
- Dynamic Host Configuration Protocol (DHCP) for automated address assignment
- Spanning Tree Protocol (STP) optimization
- EtherChannel for redundant and load-balanced uplinks
- Dynamic routing using OSPF, EIGRP, and RIPv2
- Enterprise route redistribution
- High-availability and enterprise campus network design

Each subsequent project builds directly upon this implementation, demonstrating a structured progression from Layer 2 switching fundamentals to enterprise-scale network engineering.

# Final Outcome

This project demonstrates the implementation of enterprise VLAN segmentation using Cisco Catalyst switches while following industry-standard configuration, verification, troubleshooting, and documentation practices.

Rather than functioning as an isolated Packet Tracer exercise, this repository represents another milestone in a structured Enterprise Network Engineering Portfolio that progressively develops the skills required of a professional Network Engineer.
