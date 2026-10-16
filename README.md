# Enterprise Pakistan Network Infrastructure & Simulation

A comprehensive enterprise-level network infrastructure design, deployment, and security simulation spanning multiple regional hubs across Pakistan (Punjab Head Office, Balochistan Branch, and Sindh Branch), built and verified using Cisco Packet Tracer.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Topology Architecture](#topology-architecture)
- [Core Features & Implementations](#core-features--implementations)
- [Subnet & Interface Summary](#subnet--interface-summary)
- [Security & Access Control](#security--access-control)
- [Verification & Testing](#verification--testing)
- [Author](#author)

---

## Project Overview
This project was developed as part of the System and Network Administration course (Spring 2025) at Bahria University Lahore Campus. It simulates a robust, multi-site enterprise network featuring core networking protocols, enterprise telephony, dynamic addressing, name resolution, network address translation, perimeter firewalls, and granular security policies.

---

## Topology Architecture
The network is divided into three primary geographical zones connected via serial WAN links:
1. **Head Office (Punjab):** Central management hub (`CENTER` router) responsible for core routing, DHCP assignment, telephony control, and administrative oversight.
2. **Branch 1 (Balochistan - `B2`):** Regional branch handling local workstations, IP telephony, local web hosting, and DNS servers.
3. **Branch 2 (Sindh - `S2`):** Regional branch equipped with branch workstations, DHCP relay/services, and localized web servers.

---

## Core Features & Implementations

* **WAN Interconnectivity:** Full-mesh and hub-and-spoke serial links established between regional routers with verified low-latency ICMP packet delivery (`0.000s`).
* **VLAN Segmentation:** Internal office traffic segmented into dedicated VLANs (e.g., **VLAN 10** for *Admin*, **VLAN 20** for *Sales*) with trunking configured on switch ports.
* **VoIP (Voice over IP):** Centralized telephony service configured on the Punjab router (`max-ephones 10`, extension range `101`-`105`) with voice VLANs and DHCP helper addresses (`ip helper-address 192.168.1.1`) deployed across branches.
* **DHCP Services:** Automated IP address, subnet mask, default gateway, and DNS configuration across client PCs and IP phones.
* **DNS & Web Hosting:** Regional DNS servers (`balochistan.com`, `tcs.bal`, etc.) mapping custom domains to dedicated Cisco web servers hosting localized web pages.
* **Network Address Translation (PAT/NAT):** Dynamic Port Address Translation (`ip nat inside source list 1 interface Serial0/0/1 overload`) enabling private internal hosts to communicate across external networks.
* **Access Control Lists (ACLs):** Extended ACLs implemented on routers to regulate and secure inter-branch traffic flow between regional subnets.
* **Cisco ASA Firewall:** Configured security zones (`inside` security level `100`, `outside` security level `0`) to safeguard the enterprise perimeter from external threats.

---

## Subnet & Interface Summary

| Location | Device Name | Interface | IP Address | Subnet Mask |
| :--- | :--- | :--- | :--- | :--- |
| **Head Office (Punjab)** | `CENTER` | `FastEthernet0/0` | `192.168.1.1` | `255.255.255.0` |
| **Head Office (Punjab)** | `CENTER` | `Serial0/2/0` | `192.168.10.2` | `255.255.255.0` |
| **Head Office (Punjab)** | `L1` | `GigabitEthernet0/0` | `192.168.9.1` | `255.255.255.0` |
| **Branch 1 (Balochistan)** | `B2` | `GigabitEthernet0/0` | `192.168.14.1` | `255.255.255.0` |
| **Branch 1 (Balochistan)** | `DNS_BAL` | `NIC` | `192.168.15.2` | `255.255.255.0` |
| **Branch 2 (Sindh)** | `S2` | `GigabitEthernet0/0` | `192.168.18.1` | `255.255.255.0` |
| **Branch 2 (Sindh)** | `DNS_SINDH` | `NIC` | `192.168.19.4` | `255.255.255.0` |

---

## Security & Access Control
* **ACL 130:** Applied on router serial interfaces to control and restrict traffic exchange between specific branch subnets (e.g., Sindh and Balochistan boundaries).
* **Cisco ASA Security Contexts:** Configured interface security levels, dynamic NAT object mapping, and inspection policies.

---

## Verification & Testing
* **Connectivity Tests:** 100% successful ping response rates across inter-office serial links.
* **Web Services:** Verified HTTP resolution via web browsers pointing to regional domains (`http://balochistan.com`).
* **VoIP Call Simulation:** Verified successful call placement between IP phone extensions (`101` to `105`) across different provinces.

---

## Author

**Muhammad Bilal Hamza**  
* Bahria University Lahore Campus (BSIT - 8th Semester)  
* Enrollment: `03-135231-057`  

---
*License: This project is developed for academic evaluation under Bahria University.*
