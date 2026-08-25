Cisco-Packet-Tracer-Lab-02-Small-Office-Network-Lab

A comprehensive Cisco Packet Tracer lab demonstrating **Inter-VLAN Routing (Router-on-a-Stick)** and **Trunking Configuration** across multiple switches.

---

## 📌 Network Topology Overview

This network lab configures two logical subnets (VLANs) distributed across two switches, routed using a single physical router via sub-interfaces.

* **VLAN 10 (Sales):** `192.168.10.0/24`
* **VLAN 20 (HR):** `192.168.20.0/24`

---

## 🔌 Hardware & Interface Mapping

| Device | Interface | Connected To | Assigned IP / Role | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **PC0** | Fa0 | SW1 Fa0/1 | 192.168.10.2 (VLAN 10) | 255.255.255.0 | 192.168.10.1 |
| **PC1** | Fa0 | SW1 Fa0/2 | 192.168.20.2 (VLAN 20) | 255.255.255.0 | 192.168.20.1 |
| **PC2** | Fa0 | SW2 Fa0/1 | 192.168.10.3 (VLAN 10) | 255.255.255.0 | 192.168.10.1 |
| **PC3** | Fa0 | SW2 Fa0/2 | 192.168.20.3 (VLAN 20) | 255.255.255.0 | 192.168.20.1 |
| **SW1** | Fa0/10 | SW2 Fa0/10 | Trunk Link | N/A | N/A |
| **SW1** | Fa0/24 | Router Gi0/0 | Trunk Link | N/A | N/A |

✅ Verification & Testing
​Communication between devices across different VLANs was verified using ICMP Ping tests:
​Intra-VLAN Test (PC0 to PC2): ping 192.168.10.3 -> Successful
​Inter-VLAN Test (PC0 to PC1): ping 192.168.20.2 -> Successful
​Inter-VLAN Test (PC0 to PC3): ping 192.168.20.3 -> Successful
​Note: Initial ICMP packet loss (Request timed out) is expected during ARP table resolution. Subsequent requests achieve a 100% success rate.

​🛠️ Requirements

​Cisco Packet Tracer v8.0+
