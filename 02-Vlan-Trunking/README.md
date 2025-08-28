# Lab 02 - VLAN, Trunking, Inter-VLAN Routing, DHCP

## 🎯 Objectives
- Implementasi segmentasi VLAN (HR, TI, SALES)
- Konfigurasikan tautan trunk antara switch dan router
- Gunakan Router-on-a-Stick untuk perutean antar-VLAN
- Sediakan DHCP per VLAN
- Uji komunikasi lintas VLAN

## 🏗️ Topology
- Router 2811
- Switch 2960
- 3 PCs (HR, IT, Sales)

![Topology](topology.png)

## 📌 VLAN Plan
| VLAN | Department | Subnet          | Gateway       | DHCP Range         |
|------|------------|-----------------|---------------|--------------------|
| 10   | HR         | 192.168.10.0/24 | 192.168.10.1  | 192.168.10.2-50    |
| 20   | IT         | 192.168.20.0/24 | 192.168.20.1  | 192.168.20.2-50    |
| 30   | Sales      | 192.168.30.0/24 | 192.168.30.1  | 192.168.30.2-50    |

## ⚙️ Configuration
- See `config-switch.txt` and `config-router.txt`

## 🧪 Testing
1. PC-HR ping 192.168.10.1 ✅
2. PC-IT ping 192.168.20.1 ✅
3. PC-Sales ping 192.168.30.1 ✅
4. Cross-VLAN ping ✅
5. Add new PC to VLAN HR → automatic IP via DHCP ✅

---
