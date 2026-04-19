# Week 06 – Static Routing

# Task 1: Resolving IP Addresses to Hardware Addresses

The screenshots of the ARP tables of Host1 at different time points, showing how the ARP table changes as devices communicate, are shown below.



<img width="1365" height="716" alt="ARP-Basics-12315168-Host1-Table1 png" src="https://github.com/user-attachments/assets/abc98cb2-b8d5-44b7-92fc-59b4fd14e1b1" />




<img width="1365" height="717" alt="ARP-Basics-12315168-Host1-Table2 png" src="https://github.com/user-attachments/assets/b2c7e0e2-08a0-4026-aa13-8f09c8d0f8a0" />




<img width="1363" height="714" alt="ARP-Basics-12315168-Host1-Table3 png" src="https://github.com/user-attachments/assets/d07bf138-b5e9-4b8a-aa45-38fd9542f67d" />


---

# Task 2: Default Gateways

This task shows how default gateways are used when sending traffic to another subnet.


---

# Part 1. Export Project

The project file for this lab has been exported and uploaded to the `week_06`  directory inside the `files` directory.


---

# Part 2. Screenshot of Network

The screenshot of the full network topology (hosts, switches, routers, and links) is shown below.

<img width="1365" height="698" alt="Default-Gateway-12315168-network png" src="https://github.com/user-attachments/assets/1be7b857-17bb-4355-80b1-ef8c8967d7f8" />


---

# Task 3. Record of IP Address and Routing Tables of Each Host and Router

The screenshots below show the IP address configuration and routing table for each host and router.

## Host1


<img width="1365" height="715" alt="Host1-IPAddress-12315168" src="https://github.com/user-attachments/assets/9834623e-ac9e-4315-9ce1-5cef7330e710" />


## Host2


<img width="1365" height="712" alt="Host2-IPAddress-12315168" src="https://github.com/user-attachments/assets/d2e7c5ad-d657-48fe-b66a-04aac2280fae" />


## Host3


<img width="1365" height="706" alt="Host3-IPAddress-12315168" src="https://github.com/user-attachments/assets/919f4618-34ca-46d1-ae29-b9e8e4291dd1" />


## Host4


<img width="1365" height="720" alt="Host4-IPAddress-12315168" src="https://github.com/user-attachments/assets/83d5cba9-7a95-49b0-9ce2-d08fbf653b01" />


## Router1


<img width="1365" height="723" alt="Router1-IPAddress-12315168" src="https://github.com/user-attachments/assets/cd0c2742-67a1-4c04-bd56-476948666928" />


<img width="1365" height="719" alt="Router1-IP-Route-12315168" src="https://github.com/user-attachments/assets/a3c8d9ce-aa21-4f2d-a7a1-404370c837da" />



## Router2


<img width="1365" height="716" alt="Router2-IPAddress-12315168" src="https://github.com/user-attachments/assets/6edbc891-d6c9-416e-9c62-409ebfd63dca" />


<img width="1365" height="717" alt="Router2-IP-Route-12315168" src="https://github.com/user-attachments/assets/32fb5a22-8eb3-4d6f-bce1-50fb346b0cce" />


---

# Task 4. Ping from a Host on One Subnet to a Host on the Other Subnet

This task shows end‑to‑end connectivity between two different subnets using the configured default gateways and routers.


<img width="1365" height="706" alt="Host1-Ping-12315168" src="https://github.com/user-attachments/assets/702d21bf-133c-46eb-b12d-31a4aff104de" />


The successful ping output confirms that the hosts on different subnets can communicate using their default gateways and the router configuration.


# Reflection

This week helped me clearly understand how communication actually happens inside a network. In Task 1, observing the ARP table before and after pinging made it much easier to see how IP addresses are mapped to MAC addresses in real time, rather than just learning it theoretically. In Task 2, configuring IP addresses, default gateways, and enabling routing gave me practical experience in how devices communicate across different subnets. I also faced issues like “network unreachable,” which helped me improve my troubleshooting skills by checking configurations step by step. Overall, this week strengthened both my conceptual understanding and hands-on confidence in networking.
