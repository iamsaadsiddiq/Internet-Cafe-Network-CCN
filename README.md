# Internet Café Network Simulation

A comprehensive and scalable multi-subnet network simulation of a modern Internet Café, designed using Cisco Packet Tracer. This project was developed for the Computer Communication and Networking (CCN) course under the academic supervision of **Ma’am Saira Shairi**. It demonstrates core principles of IP networking, static routing, service layer configuration, and WAN emulation.

---

## Project Overview

The goal of this project is to simulate a fully operational Internet Café network architecture, supporting multiple segmented LANs, centralized routing, internet access simulation, and essential services such as DHCP, DNS, and HTTP. Each room within the café—such as Gaming, Movies, VR Zone, Study, and Staff Office—functions as a logically isolated subnet, while remaining fully interconnected through a central routing infrastructure.

This simulation reflects real-world networking design by incorporating IP address management, inter-network routing, server deployment, and client-side operations within a unified Packet Tracer topology.

---

## Network Architecture

The network is structured around a central core router that connects five edge routers, each representing a room within the Internet Café. All routers are connected via point-to-point serial links using `/30` subnetting. Each edge router serves a dedicated LAN segment with DHCP and DNS configurations. A DSL modem provides simulated WAN access to the cloud environment, which hosts public services such as HTTP and DNS on Server2.

### Network Segments

- **Room 1 – Gaming:** 192.168.1.0/24  
- **Room 2 – Movies:** 192.168.2.0/24  
- **Room 3 – VR Zone:** 192.168.3.0/24  
- **Room 4 – Study:** 192.168.4.0/24  
- **Room 5 – General Internet and Surfing:** 192.168.5.0/24  
- **Core WAN Links:** 192.168.100.0/30 series  
- **Simulated Internet (Cloud):** 203.0.113.0/29  

Each subnet includes a dedicated router interface, client PCs, and in some cases, a server to simulate local applications such as gaming or educational services.

---

##  Key Configurations

### 1. Static Routing

All routers use statically configured routes for communication. The central router maintains routes to each LAN segment and serves as the single default gateway for internet-bound traffic.

### 2. DHCP Configuration

Each room router contains a DHCP pool that allocates IP addresses to client PCs within its subnet, along with the correct default gateway and DNS server.

### 3. DNS and HTTP Simulation

- **Server0** hosts DHCP/DNS services for internal testing.
- **Server2** simulates public web and DNS services in the cloud.
- DNS servers resolve domain names such as `www.example.com` to internal or simulated public IPs.

### 4. Internet Access Simulation

- A **DSL Modem** connects the central router to the **Cloud**.
- The **Cloud** includes Server2, hosting simulated internet services accessible from all LANs.

---

##  Testing and Validation

The network was rigorously tested to validate:

- **Device Connectivity:** ICMP ping tests between PCs, routers, and servers confirmed successful communication.
- **IP Assignment:** DHCP distributed correct IP addresses, subnet masks, gateways, and DNS.
- **Internet Simulation:** Clients accessed Server2’s web and DNS services via simulated external routing.
- **Logical Topology:** All interfaces were administratively up, links were active, and IP addressing was consistent.

Validation also confirmed that each PC could reach:

- Its local router and PCs
- All other room routers and PCs
- Local and simulated external servers
- Web pages via HTTP and DNS resolution

---

##  Server Configuration Summary

Each server was configured with:

- Static IP address
- Default gateway of its subnet router
- DNS service (optional)
- HTTP or FTP services for content simulation

### Example:
**Gaming Room Server (192.168.1.2):**
- Hosts game content for Room 1 PCs
- Excluded from DHCP pool
- Responds to HTTP and DNS requests

---

## Scalability and Security Considerations

The design supports future improvements such as:

- VLAN implementation for traffic segmentation
- ACLs for access control between rooms or services
- Dynamic routing protocols (OSPF, EIGRP) for scalability
- Firewall integration for realistic threat modeling

Currently, the network operates with an open security model to emphasize core connectivity and routing behavior.

---


## How to Use

1. Open the `.pkt` file in Cisco Packet Tracer.
2. Power on all devices and ensure all cables are connected.
3. Use PC terminals to verify IP assignment and test connectivity.
4. Open the web browser on any PC and visit `203.0.113.10` or a configured domain (e.g., `www.example.com`).
5. Explore router CLI for further practice or modification.

---

##  Project Contributor

- **Muhammad Saad** – L1F22BSCS0937  

Under the supervision of **Ma’am Saira Shairi**

---

##  License

This project is intended for **academic and educational use only**. Please cite the authors and supervisor if reused or referenced in coursework or research.

---

##  Acknowledgments

We extend our sincere gratitude to **Ma’am Saira Shairi** for her expert guidance and constructive feedback throughout the project. Her support played a pivotal role in shaping the technical direction and depth of the network simulation.

---

##  Tags

`Networking` `Cisco Packet Tracer` `Static Routing` `DHCP` `DNS` `Internet Simulation` `Computer Networks` `LAN` `WAN` `CCNA` `Education`
