# Troubleshooting Notes - Lab 02

### Common Issues

1. **Router sub-interface down**
   - Run `show ip int brief`
   - Fix: `interface fa0/0` → `no shutdown`

2. **Wrong VLAN encapsulation**
   - Check config: `encapsulation dot1Q <VLAN-ID>`
   - VLAN ID must match switch VLAN

3. **Switch trunk misconfigured**
   - Run `show interface fa0/24 switchport`
   - Fix: 
     ```
     interface fa0/24
     switchport mode trunk
     ```

4. **PC not in VLAN**
   - Run `show vlan brief`
   - Fix:
     ```
     interface fa0/x
     switchport mode access
     switchport access vlan <ID>
     ```

5. **PC gets 169.254.x.x (APIPA)**
   - DHCP not working
   - Check DHCP pool in router and excluded-address
