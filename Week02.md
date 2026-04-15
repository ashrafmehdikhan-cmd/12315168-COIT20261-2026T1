# Week 02 – IP Addressing & Basic Connectivity

## Overview
This week I configured static IP addresses on all four hosts in GNS3 and tested basic network connectivity using different ping commands.

## Task 1 – Configure IP Addresses

### What I did
- Added Host1, Host2, Host3, Host4 and connected each eth0 interface to the switch.
- The switch ports used were: Ethernet0/0, Ethernet0/1, Ethernet0/2, Ethernet0/3.
- Assigned static IP addresses using different methods (CLI, GUI, interfaces file).
- Restarted each host to apply the settings.
- Verified all IPs using `ip address show`.

### Host1 – CLI
ip address add 10.10.2.1/24 dev eth0
ip link set eth0 up
ip address show

### Host2 – GUI Network Config
auto eth0
iface eth0 inet static
    address 10.10.2.2
    netmask 255.255.255.0

### Host3 – /etc/network/interfaces
auto eth0
iface eth0 inet static
    address 10.10.2.3
    netmask 255.255.255.0

### Host4 – CLI
ip address add 10.10.2.4/24 dev eth0
ip link set eth0 up
ip address show

### Commands used
ip address add <IP>/<MASK> dev eth0
ip link set eth0 up
ip address show


## Task 2 – Ping Tests

### 2.1 Simple Ping (Host1 → Host2)
ping 10.10.2.2
# Result: Successful, 0% packet loss.
# <img width="1365" height="706" alt="Ping-Basics-12315168-simple png" src="https://github.com/user-attachments/assets/22dc539d-0a57-40bf-8f2f-dfb78dcd75d9" />


### 2.2 Ping to Wrong IP
ping 10.10.2.250
# Result: Destination Host Unreachable, 100% packet loss.
# <img width="1365" height="710" alt="Ping-Basics-12315168-error png" src="https://github.com/user-attachments/assets/59a737a8-bf1a-4f3d-af5e-49de0ab02f80" />


### 2.3 Ping with Options
ping -c 3 -i 2 -s 80 10.10.2.2
# Result: 3 packets sent, 3 received, 0% loss.
# <img width="1365" height="710" alt="Ping-Basics-12315168-options png" src="https://github.com/user-attachments/assets/a10db175-e3d4-415f-b3b5-d7d0104f5520" />
