# Lab 03 - Inter-VLAN Routing + DHCP Relay

## 🎯 Objectives
- Implementasi Router-on-a-Stick untuk komunikasi antar-VLAN
- Sediakan centralized DHCP Server untuk semua VLAN
- Gunakan DHCP Relay (`ip helper-address`) agar tiap VLAN bisa dapat IP otomatis
- Uji komunikasi lintas VLAN

## 🏗️ Topology
- Router 2811
- Switch 2960
- 1 DHCP Server
- 9 PCs (Marketing, IT, HR)

![Topology](topology.png)

## 📌 VLAN Plan
| VLAN | Department | Subnet          | Gateway       | DHCP Range           |
|------|------------|-----------------|---------------|--------------------|
| 10   | Marketing  | 192.168.10.0/24 | 192.168.10.1  | 192.168.10.50-200   |
| 20   | IT         | 192.168.20.0/24 | 192.168.20.1  | 192.168.20.50-200   |
| 30   | HR         | 192.168.30.0/24 | 192.168.30.1  | 192.168.30.50-200   |

## ⚙️ Configuration
- Switch VLAN & port assignment → see `config-switch.txt`
- Router sub-interfaces + DHCP Relay → see `config-router.txt`
- DHCP Server pools → see `config-dhcp.txt`

## 🧪 Testing
1. PC-Marketing ping 192.168.10.1 ✅
2. PC-IT ping 192.168.20.1 ✅
3. PC-HR ping 192.168.30.1 ✅
5. Cross-VLAN ping (PC-Marketing ↔ PC-IT) ✅
6. Add new PC to any VLAN → automatic IP via DHCP Relay ✅

---
