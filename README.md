
# Cisco Packet Tracer Labs

Personal networking lab collection built in Cisco Packet Tracer while studying for CCNA. Each project increases in scale and complexity — from a single-site VLAN/OSPF design up to a multi-ISP, dual-datacenter topology with hundreds of endpoints.

## Projects

### 1. Multi-Branch WAN with ISP Core
`Ciscco - With ISP.png`

Six independent LAN sites (LAN 1–LAN 6), each running its own router and dual access-layer switches, connected through a 3-router ISP core mesh.

- Each LAN on its own /24 (192.168.1.0/24 – 192.168.6.0/24)
- Point-to-point WAN links on /30 subnets between LAN routers and ISP routers
- ISP core (ISP Router 1/2/3) fully meshed via redundant serial links
- Dynamic routing (RIP) across the WAN
- DHCP handled per site

### 2. Hotel Network (3-Floor Enterprise)
`Hotel.png`

A three-floor hotel network with per-floor routing and departmental VLAN segmentation.

- One router + one switch per floor (F1, F2, F3), interconnected in a partial mesh over /30 serial links
- OSPF for inter-floor routing
- 8 VLANs across departments: IT (10), Admin (20), Sales (30), HR (40), Finance (50), Logistic (60), Store (70), Reception (80) — each its own /24
- Wireless access point per floor
- SSH management and port security applied to access-layer switches

### 3. Dual Data Center / 9-Site Enterprise
`Cisco_Dual_DC.png`

The largest and most complex topology: 7 branch LANs plus a primary and backup data center, all reachable through 3 independent ISPs.

- 7 branch sites (LAN 1–LAN 7), each with 3–4 VLANs (e.g., LAN 1: VLAN 5/10/15/20)
- Every site and both data centers run redundant **Active/Standby routers with HSRP** for first-hop gateway resiliency
- Primary Data Center (192.168.1.0/24, hosting App2–App5) and Backup Data Center (192.168.2.0/24)
- 3 ISPs (ISP1/ISP2/ISP3), each internally meshed, providing transit between all sites and both data centers
- Dense /30 point-to-point addressing across the entire WAN core for redundant paths
- Designed to demonstrate high availability: no single router or WAN link failure should isolate a site from both data centers

### 4. Large-Scale Multi-VLAN Deployment
`60_PCs_with_Labels.png`

A six-site ring topology focused on scale and DHCP-based VLAN assignment rather than WAN complexity.

- 6 LANs arranged in a ring, each connected to a central ISR4331 router
- Each LAN uses 3 access switches and 3 VLANs on a single /24 (e.g., LAN 1: 192.168.1.0 VLAN1, .65 VLAN2, .129 VLAN3 — /26 subnetting per VLAN)
- Per-site DHCP servers issuing addresses per VLAN
- Core routers interconnected via /30 links in a ring for redundancy
- Hundreds of end devices total — used to test scalability of switch/VLAN design and DHCP scope sizing rather than routing protocol behavior

## Skills Demonstrated

- VLAN design and segmentation (802.1Q trunking, router-on-a-stick)
- Interior routing: OSPF, RIP
- First-hop redundancy: HSRP (Active/Standby)
- WAN design with point-to-point /30 links and multi-provider (ISP) transit
- DHCP scope planning per VLAN/site
- Switch security: SSH hardening, port security
- Scaling network designs from single-site to multi-site/multi-datacenter

## Notes

These are self-directed lab exercises, not production designs. IP scheme and topology choices prioritize demonstrating specific concepts (HSRP failover, multi-ISP redundancy, VLAN scale) over real-world efficiency.
