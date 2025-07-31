System and Network Administration Project
Overview
This repository contains a network infrastructure project . The project simulates a multi-site network with a head office and two branch offices, implemented using Cisco Packet Tracer. 
It features WAN connectivity, VLANs, VoIP, DNS, DHCP, NAT, web servers, ACLs, and a Cisco firewall, demonstrating enterprise-level network design and security.
Features

Configured a head office and two branch offices with routers and switches.
Established WAN links using serial interfaces (e.g., 192.168.10.2 on a central router).
Set up two VLANs at one office for network segmentation.
Deployed DNS (e.g., 192.168.10.2) and DHCP for IP management.
Applied NAT for internet access and ACLs for traffic control.
Installed a Cisco firewall and web servers for security and services.

Installation

Prerequisites:
Cisco Packet Tracer (version 7.3 or later).
Compatible OS (Windows, Linux, or macOS).


Setup:
Clone the repository: git clone <repository-url>.
Open the network_project.pkt file in Cisco Packet Tracer.
Review IP configurations in ip_config.xlsx.


Dependencies:
None beyond Cisco Packet Tracer.



Usage

Launch Simulation: Open network_project.pkt in Cisco Packet Tracer.
Test Connectivity:
Ping devices (e.g., ping 192.168.10.1 from a router) to verify links.
Check DHCP assignments and VoIP calls via simulation.


Review Documentation: See TCS Project.docx for IP tables, NAT rules, and ACL settings.



License
For educational use only. Commercial use prohibited without permission.
