# Task 1 – View Routing Tables

## Part 1. Export the Project
I created a new GNS3 project named **View-Routes-12315168** and exported it after completing the setup.  
The exported project file is saved inside the **week_04** folder in my repository.

## Part 2. Screenshot of Network
The network topology for this task includes three hosts, one router, and one switch.  
Host1 and Host2 are connected to the router through the switch (Subnet 10.1.1.0/24), and Host3 is connected directly to Router1 on a different interface (Subnet 10.1.2.0/24).

<img width="1365" height="720" alt="Network-Topology-12315168" src="https://github.com/user-attachments/assets/5b6df575-a9b7-4d31-8fbb-f667b94f9a39" />

## Part 3. IP Address and Routing Table Screenshots
I configured static IPv4 addresses on all hosts and router interfaces.  
The first subnet uses **10.1.1.0/24**, and the second subnet uses **10.1.2.0/24**.  
I used `ip address show` and `ip route show` on each device to verify the configuration.

### Host1 – IP Address & Routing Table
<img width="1365" height="716" alt="Host1-IP-ROUTE-12315168" src="https://github.com/user-attachments/assets/b2f0cdec-f272-4a13-b31f-2696aedca46e" />


### Host2 – IP Address & Routing Table
<img width="1365" height="706" alt="Host2-IP-ROUTE-12315168" src="https://github.com/user-attachments/assets/90acd9aa-ac53-4ecc-b632-483bae749701" />


### Host3 – IP Address & Routing Table
<img width="1365" height="705" alt="Host3-IP-ROUTE-12315168" src="https://github.com/user-attachments/assets/11d87790-370d-4237-8c02-68e221412663" />


### Router1 – IP Address & Routing Table
<img width="1361" height="716" alt="1-Router1-IP-Route-12315168" src="https://github.com/user-attachments/assets/f23a22c7-f52c-46cd-a049-8e5067f736bd" />

<img width="1365" height="705" alt="2-Router1-IP-Route-12315168" src="https://github.com/user-attachments/assets/7706bd39-4e3f-4194-90e6-11c9563ebe70" />


## Part 4. Ping from One Subnet Host to Another Subnet Host
To confirm routing between the two subnets, I tested connectivity from **Host1 (10.1.1.10)** to **Host3 (10.1.2.10)** using the `ping` command.  
Since the hosts are on different networks, the packets travel through Router1.  
The ping was successful with **0% packet loss**, confirming that IPv4 forwarding on the router is working correctly and both subnets can communicate.

<img width="1365" height="690" alt="Ping-host1-3-12315168" src="https://github.com/user-attachments/assets/b3a7d535-b6d8-47e7-a517-876be5a01a9e" />
