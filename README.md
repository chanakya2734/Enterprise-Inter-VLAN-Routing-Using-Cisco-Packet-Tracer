# Enterprise-Inter-VLAN-Routing-Using-Cisco-Packet-Tracer

## Project Overview

This project demonstrates the implementation of Inter-VLAN Routing in an enterprise network environment using Cisco Packet Tracer. The project focuses on network segmentation using VLANs, VLAN communication through Router-on-a-Stick, VLAN extension using trunk links, and inter-network communication using a Layer 3 Switch.

The network is designed to provide secure communication between different departments while maintaining proper network segmentation and efficient routing.

---

## Objectives

- Configure and implement VLANs to segment network traffic.
- Configure trunk links between switches.
- Implement Router-on-a-Stick for Inter-VLAN communication.
- Configure Layer 3 Switching for routing between VLANs.
- Verify communication between devices in different VLANs.
- Demonstrate enterprise network segmentation and routing concepts.

---

## Technologies Used

- Cisco Packet Tracer
- Cisco ISR4331 Router
- Cisco 2960 Switches
- Cisco 3560 Multilayer Switch
- VLAN
- Trunking
- Router-on-a-Stick
- Layer 3 Switching
- ICMP
- Inter-VLAN Routing

---

## Network Topology

Topology image is available in:

```
topology/Enterprise_Inter_VLAN_Topology.png
```

---

## Network Architecture

The network consists of:

- Router0 configured for Router-on-a-Stick Inter-VLAN Routing.
- Switch0 configured with VLANs and trunk links.
- Switch1 configured with VLANs and trunk links.
- Multilayer Switch configured for Layer 3 Inter-VLAN Routing.
- PCs assigned to different VLANs.
- Two departments:
  - VLAN 10 – Sales Department
  - VLAN 20 – Accounts Department

---

## VLAN Configuration

| VLAN ID | Department |
|---------|------------|
| VLAN 10 | Sales |
| VLAN 20 | Accounts |

---

## Device Assignment

### VLAN 10 (Sales Department)

| Device | VLAN |
|--------|------|
| PC0 | VLAN 10 |
| PC3 | VLAN 10 |

### VLAN 20 (Accounts Department)

| Device | VLAN |
|--------|------|
| PC1 | VLAN 20 |
| PC2 | VLAN 20 |

---

## Router-on-a-Stick Configuration

Router0 was configured using subinterfaces to enable communication between multiple VLANs.

Router0 configuration:

```bash
interface g0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface g0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
```

---

## Trunk Configuration

Switch trunk ports were configured to carry traffic for multiple VLANs.

Switch configuration:

```bash
interface fa0/1
 switchport mode trunk
 switchport trunk allowed vlan 10,20
```

---

## Layer 3 Switch Configuration

The Multilayer Switch was configured using Switch Virtual Interfaces (SVIs) to enable Inter-VLAN communication.

L3 Switch configuration:

```bash
ip routing

interface vlan 10
 ip address 192.168.10.100 255.255.255.0
 no shutdown

interface vlan 20
 ip address 192.168.20.100 255.255.255.0
 no shutdown
```

---

## Verification

### Router-on-a-Stick Verification

Inter-VLAN communication was verified using ICMP ping tests between VLAN 10 and VLAN 20 devices.

Verification performed using:

```bash
ping 192.168.20.2
ping 192.168.10.2
```

Successful communication was verified.

---

### Trunk Verification

VLAN communication across Switch0 and Switch1 was verified using ping tests.

Verification performed using:

```bash
ping 192.168.1.1
ping 192.168.10.1
```

Successful communication was verified.

---

### Layer 3 Switch Verification

Layer 3 routing functionality was verified using ping tests between connected hosts and VLAN gateways.

Verification performed using:

```bash
ping 192.168.10.100
ping 192.168.1.1
```

Successful communication was verified.

---

## Screenshots

Available in the screenshots folder:

- VLAN_Using_Trunking.png
- VLAN_Using_Router_on_the_Stick.png
- VLAN_L3_Switch.png

---

## Project Structure

```text
Enterprise-Inter-VLAN-Routing-Using-Cisco-Packet-Tracer

├── README.md

├── topology
│   └── Enterprise_Inter_VLAN_Topology.png

├── screenshots
│   ├── Inter_VLAN_Ping_Results.png
│   ├── VLAN_L3_Switch_Verification.png
│   └── VLAN_Router_on_a_stick_Verification.png

├── configurations
│   ├── Router0_Router_on_a_Stick_Configuration.txt
│   ├── Switch0_VLAN_Configuration.txt
│   ├── Switch1_Trunk_Configuration.txt
│   └── Layer3_Switch_Configuration.txt

└── project_file
    └── Enterprise_Inter_VLAN_Routing.pkt
```

---

## Learning Outcomes

- VLAN Configuration
- VLAN Segmentation
- Trunk Configuration
- Router-on-a-Stick Configuration
- Layer 3 Switching
- Inter-VLAN Routing
- Enterprise Network Design
- Cisco Device Configuration
- Network Troubleshooting
- Network Verification
- Cisco Packet Tracer Simulation

---

## Author

**Chanakya Burugu**

Computer Science and Engineering (Networks)

Networking and Infrastructure Enthusiast
