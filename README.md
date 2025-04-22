# 🛡️ Cybersecurity Homelab Configuration 
**IN PROGRESS**

This SOC homelab is inspired by [Cyberwox Academy](https://www.cyberwoxacademy.com/post/building-a-cybersecurity-homelab). This lab is hosted locally utilizing VMWare Workstation Pro and tries to simulate an enterprise network to test both defensive and offensive security testing.

---

## Lab Goals

- Simulate a corporate environment with network segmentation and monitoring
- Build and analyze detections using Security Onion and Splunk
- Practice Active Directory administration and compromise scenarios
- Conduct offensive testing using Kali Linux and vulnerable machines
- Study and visualize network traffic in a safe, isolated environment

## Lab Components

### pfSense (Firewall/Router)

- **em0 (WAN)**: NAT
- **em1 (LAN)**: VMnet2 (SOC Management)
- **em2**: VMnet3 (Domain Controller/Workstations)
- **em3**: VMnet4 (SPAN Port)
- **em4**: VMnet5 (Attacker)

### Security Onion

- **Role**: IDS / NSM / Syslog Collection
- **NICs**: 
  - ens33 → VMnet2 (Mgmt)
  - ens34 → VMnet4 (Monitor)

### Kali Linux

- **Role**: Attacker VM
- **NIC**: VMnet5 (Attack)

### Windows Server 2019 (Domain Controller)

- **Role**: Active Directory, DNS
- **NIC**: VMnet3 (Domain)

### Windows 10 Clients

- **Role**: Domain-joined endpoints
- **NIC**: VMnet3 (Domain)

### Splunk

- **Role**: SIEM / Log Aggregator
- **NIC**: VMnet2 (Mgmt)




