**Office Network Design & Configuration Lab (Cisco Packet Tracer)**

## 📌 Project Overview

This project demonstrates the design and configuration of a simple office network using Cisco Packet Tracer. The network connects two departments—Accounts and Delivery—through a single router and two switches, simulating a real-world small business environment.

The goal was to implement proper network segmentation, configure routing, and ensure end-to-end connectivity between devices.


## 🧱 Network Topology

The network consists of:

* 1 Router
* 2 Switches
* Multiple PCs (Accounts & Delivery departments)
* Network Printers

Each department operates on a separate subnet for better segmentation and management.

<img width="1366" height="768" alt="Network Topology" src="https://github.com/user-attachments/assets/3a757f81-edfb-4237-ba0a-7290be9bb8d7" />


## 🌐 IP Addressing & Subnetting

Base Network:
`192.168.40.0/24`

Subnetting applied to divide the network into two departments:

* **Subnet 1 (Accounts):**
  Network: `192.168.40.0/25`
  Usable Range: `192.168.40.1 – 192.168.40.126`
  Broadcast: `192.168.40.127`

* **Subnet 2 (Delivery):**
  Network: `192.168.40.128/25`
  Usable Range: `192.168.40.129 – 192.168.40.254`
  Broadcast: `192.168.40.255`

Subnet Mask: `255.255.255.128`

<img width="1336" height="714" alt="networkcli" src="https://github.com/user-attachments/assets/6f61bf3e-6dd8-4d7a-882f-1d81acd7f3d3" />


## Router Configuration

The router was configured to enable communication between both subnets.

### Commands Used:

```bash
enable
configure terminal

interface gig0/0
ip address 192.168.40.1 255.255.255.128
no shutdown

interface gig0/1
ip address 192.168.40.129 255.255.255.128
no shutdown

exit
write memory
```



## Host Configuration

Each device (PCs and printers) was manually configured with:

* IP Address
* Subnet Mask
* Default Gateway

### Example:

**Accounts PC:**

* IP: `192.168.40.10`
* Subnet Mask: `255.255.255.128`
* Gateway: `192.168.40.1`

**Delivery PC:**

* IP: `192.168.40.140`
* Subnet Mask: `255.255.255.128`
* Gateway: `192.168.40.129`



##  Verification & Testing

Connectivity was verified using ICMP ping tests:


<img width="1366" height="768" alt="networkcli2" src="https://github.com/user-attachments/assets/7b00506a-7b3a-4932-943c-994d206162a5" />

### Commands:

```bash
ping 192.168.40.140
ping 192.168.40.10
```

### Results:

* Successful communication between departments
* Devices able to reach printers across subnets
* Router correctly forwarding traffic

<img width="1366" height="765" alt="networkcli3" src="https://github.com/user-attachments/assets/20c6e981-624e-4689-955f-a9317bb15873" />


##  Key Skills Demonstrated

* Network Topology Design
* IP Addressing & Subnetting
* Router Configuration (Cisco CLI)
* Network Segmentation
* Troubleshooting & Connectivity Testing



##  Conclusion

This lab simulates a real-world office network and demonstrates the ability to design, configure, and troubleshoot network infrastructure using Cisco technologies.


## 🔗 More Projects

Check out more of my work:
👉 [https://github.com/cybergabby](https://github.com/cybergabby)
