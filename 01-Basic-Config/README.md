# Lab 01 – Basic Configuration dengan DHCP

## 🎯 Tujuan
- Membuat jaringan sederhana dengan 2 LAN terhubung router
- Router berfungsi sebagai DHCP server
- PC mendapatkan IP address secara otomatis (DHCP)

---

## 🏗️ Topologi

## 📡 IP Addressing
| Device | Interface        | IP Address (DHCP) | Gateway     |
|--------|------------------|------------------|-------------|
| PC1    | FastEthernet0    | 192.168.1.x      | 192.168.1.1 |
| PC2    | FastEthernet0    | 192.168.2.x      | 192.168.2.1 |
| Router | FastEthernet0/0  | 192.168.1.1      | -           |
| Router | FastEthernet0/1  | 192.168.2.1      | -           |

---

## 🔍 Testing
1. PC1 → `ping 192.168.1.3` ✅  
2. PC2 → `ping 192.168.2.2` ✅  
3. PC1 → `ping 192.168.2.x` (alamat PC2) ✅  

---

## 📌 Kesimpulan
- DHCP berhasil memberikan IP address ke PC secara otomatis  
- LAN pusat (`192.168.1.0/24`) dan LAN cabang (`192.168.2.0/24`) berhasil terhubung melalui router