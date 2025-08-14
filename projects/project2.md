# 🌐 Small Office Network Configuration Lab

**Objective:** Configure a small office network with proper IP addressing, DHCP, and basic security.

## Topology
- Router → Switch → 6 Client PCs
- VLAN 10 (Staff), VLAN 20 (Guest)

## IP Plan
- VLAN 10: 192.168.10.0/24 (DHCP)
- VLAN 20: 192.168.20.0/24 (DHCP)
- Router LAN IPs: 192.168.10.1, 192.168.20.1

## Sample Config
```bash
vlan 10
 name STAFF
vlan 20
 name GUEST
```
