# hsrp-high-availability-network
Implementation of a redundant network infrastructure using Cisco HSRP, Inter-VLAN routing, and DHCP services for 15 VLANs in Cisco Packet Tracer.

# High Availability Network Infrastructure with HSRP

## 📌 Project Overview
This repository contains a high-availability network project designed and simulated in **Cisco Packet Tracer**. The project focuses on implementing a redundant gateway solution using **HSRP (Hot Standby Router Protocol)** to ensure network resilience and 100% uptime for 15 distinct VLANs.

The architecture follows a hierarchical model (Core, Distribution, and Access) to simulate a robust corporate environment.

## 🚀 Key Features
* **Gateway Redundancy:** Dual-router setup (Active/Standby) using HSRP.
* **Inter-VLAN Routing:** Router-on-a-stick configuration with 802.1Q encapsulation.
* **Dynamic Addressing:** Fully automated DHCP pools for all 15 VLAN segments.
* **Network Segmentation:** Logical separation of departments/services via VLANs.
* **Failover Validation:** Proven automatic recovery during primary link failure.

## 🛠️ Technologies Used
* **Simulation Tool:** Cisco Packet Tracer
* **Protocols:** HSRP, IEEE 802.1Q (Dot1Q), DHCP, ICMP, VTP/STP.
* **Infrastructure:** Cisco 2911 Routers, 2960 Switches, and End-Devices.

## 📁 Repository Structure
* `/topology`: Contains the `.pkt` (Packet Tracer) source file.
* `/documentation`: Contains screenshots of CLI configurations and verification tests.
* `README.md`: Project documentation and summary.

## 📊 Network Configuration Details
The network is divided into 15 VLANs (10-150). Each VLAN uses the `.254` address as its Virtual IP (VIP) for the default gateway.

| VLAN ID | Subnet | Gateway (VIP) | HSRP Role |
| :--- | :--- | :--- | :--- |
| 10 - 150 | 192.168.X.0/24 | 192.168.X.254 | R1 (Active) / R2 (Standby) |

## 🧪 Verification & Testing
### 1. HSRP Status
Verification of the Active and Standby roles was performed using the `show standby brief` command, ensuring that R1 manages all traffic while R2 remains in a ready state.

### 2. Connectivity Test
Inter-VLAN communication was validated through ICMP ping tests from end-devices to their respective virtual gateways and across different network segments.

### 3. Failover Simulation
A critical test was performed by disabling the primary interface on **R1-CORE-A**. The simulation confirmed that **R2-CORE-B** successfully assumed the Active role in seconds, maintaining connectivity for all users without manual reconfiguration.

## 📸 Screenshots
*(Include your numbered screenshots here or link them from the documentation folder)*

## 📄 Conclusion
This project demonstrates the practical application of high-availability protocols in modern networking. It ensures that the infrastructure can withstand hardware failures without impacting the end-user experience.

---
**Developed by:** [Eduardo]  
**Date:** January 2026
