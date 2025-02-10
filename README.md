# OSPFv2 Configuration - Packet Tracer Lab

This repository contains the **Point-to-Point Single-Area OSPFv2 Configuration** setup for Cisco Packet Tracer. The lab involves configuring OSPF across three routers (R1, R2, R3) and ensuring proper routing between different networks.

## 📌 **Project Overview**
- **Routing Protocol:** OSPFv2 (Process ID 10)
- **Routers:** R1, R2, R3
- **LAN Networks:** 192.168.10.0/24, 192.168.20.0/24, 192.168.30.0/24
- **WAN Networks:** 10.1.1.0/30, 10.1.1.4/30, 10.1.1.8/30
- **Features Implemented:**
  - OSPF Configuration
  - Router IDs Assignment
  - Passive Interfaces Configuration
  - OSPF Verification

## 🖥️ **Configuration Files**
The following routers have been configured with OSPFv2:

### 🔹 **Router R1 Configuration**
```
enable
configure terminal
hostname R1

interface g0/0/0
 ip address 192.168.10.1 255.255.255.0
 no shutdown
 exit

interface s0/1/0
 ip address 10.1.1.1 255.255.255.252
 no shutdown
 exit

interface s0/1/1
 ip address 10.1.1.5 255.255.255.252
 no shutdown
 exit

router ospf 10
 router-id 1.1.1.1
 network 192.168.10.0 0.0.0.255 area 0
 network 10.1.1.0 0.0.0.3 area 0
 network 10.1.1.4 0.0.0.3 area 0
 passive-interface g0/0/0
 exit
```

### 🔹 **Router R2 Configuration**
```
enable
configure terminal
hostname R2

interface g0/0/0
 ip address 192.168.20.1 255.255.255.0
 no shutdown
 exit

interface s0/1/0
 ip address 10.1.1.2 255.255.255.252
 no shutdown
 exit

interface s0/1/1
 ip address 10.1.1.9 255.255.255.252
 no shutdown
 exit

router ospf 10
 router-id 2.2.2.2
 network 192.168.20.0 0.0.0.255 area 0
 network 10.1.1.2 0.0.0.3 area 0
 network 10.1.1.8 0.0.0.3 area 0
 passive-interface g0/0/0
 exit
```

### 🔹 **Router R3 Configuration**
```
enable
configure terminal
hostname R3

interface g0/0/0
 ip address 192.168.30.1 255.255.255.0
 no shutdown
 exit

interface s0/1/0
 ip address 10.1.1.10 255.255.255.252
 no shutdown
 exit

interface s0/1/1
 ip address 10.1.1.6 255.255.255.252
 no shutdown
 exit

router ospf 10
 router-id 3.3.3.3
 network 192.168.30.0 0.0.0.255 area 0
 network 10.1.1.10 0.0.0.3 area 0
 network 10.1.1.6 0.0.0.3 area 0
 passive-interface g0/0/0
 exit
```

## 🔍 **Verification Commands**
To check if OSPF is working properly, use the following commands:
```
show ip ospf neighbor
show ip route ospf
show ip protocols
```

## 📜 **How to Use This Configuration**
1. Open **Cisco Packet Tracer** and create the network topology.
2. Apply the configurations to each router.
3. Verify OSPF neighbor relationships using `show ip ospf neighbor`.
4. Test connectivity using `ping` between different networks.

## 📌 **Contributors**
- **Bilal Azam**

## 📜 **License**
This project is open-source and free to use under the MIT License.

🚀 **Upload this to GitHub to document your OSPF setup!**
