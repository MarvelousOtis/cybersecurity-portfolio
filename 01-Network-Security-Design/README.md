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
