# Network Security Design

This project focuses on designing a secure network for a small organisation using Cisco Packet Tracer.

## Objectives
- Understand basic network architecture.
- Practise IP addressing and subnetting.
- Apply network segmentation.
- Identify basic network security measures.

## Tools
- Cisco Packet Tracer

## Project Status
In Progress

## Network Implementation

### Network Devices
- 1 Cisco 2960 Switch
- 3 End Devices (PCs)

### IP Addressing

| Department | IP Address | VLAN |
|---|---|---|
| Administration | 192.168.1.10 | 10 |
| Finance | 192.168.1.11 | 20 |
| IT | 192.168.1.12 | 30 |

### VLAN Configuration
- VLAN 10: ADMIN
- VLAN 20: FINANCE
- VLAN 30: IT

### Connectivity Testing
A ping test from Administration (VLAN 10) to Finance (VLAN 20) returned Request Timed Out.
This demonstrated that devices in separate VLANs could not communicate directly without inter-VLAN routing.

### Tools Used
- Cisco Packet Tracer
- Cisco IOS CLI

## Project Implementation and Results

### 1. Network Design

Designed and configured a small office network with three departments:

- Administration
- Finance
- IT

**Tools used:** Cisco Packet Tracer, Cisco 2960 Switch and Cisco 2911 Router.

### 2. IP Addressing

| Department | VLAN | IP Address | Default Gateway |
|---|---|---|---|
| Administration | 10 | 192.168.10.10 | 192.168.10.1 |
| Finance | 20 | 192.168.20.10 | 192.168.20.1 |
| IT | 30 | 192.168.30.10 | 192.168.30.1 |

Subnet mask: 255.255.255.0

### 3. Network Configuration

- Created three VLANs to separate departmental networks.
- Assigned switch access ports to their respective VLANs.
- Configured a trunk connection between the switch and router.
- Implemented router-on-a-stick using router subinterfaces.
- Configured default gateways for all three departments.

### 4. Security Implementation

Configured an extended Access Control List (ACL) named `FINANCE_PROTECTION`.

Security policy:
- Block Administration from accessing Finance.
- Allow IT to access Finance.
- Permit other IP traffic not covered by the restriction.

The ACL was applied outbound on the Finance router subinterface.

### 5. Testing and Results

| Test | Result |
|---|---|
| Administration to router gateway | Successful |
| Administration to Finance | Blocked |
| Administration to IT | Successful |
| IT to Finance | Successful |

The tests confirmed that inter-VLAN routing was working and the ACL enforced the intended access restrictions.

### 6. Key Learning Outcomes

Through this project, I gained practical experience with:

- VLAN creation and configuration.
- IP addressing and subnetting.
- Router-on-a-stick configuration.
- Inter-VLAN routing.
- Extended Access Control Lists.
- Network connectivity testing and troubleshooting.

### 7. Project Status

Completed.

## Project Screenshots

### Network Topology
![NetworkTo](https://github.com/MarvelousOtis/cybersecurity-portfolio/blob/main/01-Network-Security-Design/Network%20Topology.PNG)

### ACL Configuration
![[ACL Configuration](./acl-configuration.png)](https://github.com/MarvelousOtis/cybersecurity-portfolio/blob/main/01-Network-Security-Design/ACL%20Configuration.PNG)
