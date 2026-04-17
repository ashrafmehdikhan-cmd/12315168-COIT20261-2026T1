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


# Task 2 – OSPF Basics

## Part 1. Export the Project
For this task, I used the **OSPF-Basics-Template** project provided in the unit.  
After confirming that all routers and hosts were running correctly, I exported the project and saved it in my **week_04** folder.

<img width="1365" height="712" alt="OSPF-Project-Export-12315168" src="https://github.com/user-attachments/assets/4482813c-51a5-4e9d-806d-d3c94f7dcd8f" />


## Part 2. OSPF Neighbour Table
I checked the OSPF neighbour relationships to confirm that the routers had formed adjacencies.  
On **FRR-1**, I ran the `show ip ospf neighbor` command.  
The output showed two neighbours in the **Full/DR** state, which means OSPF is operating correctly and exchanging LSAs with adjacent routers.

<img width="1365" height="706" alt="OSPF-Neighbour-FRR1-12315168" src="https://github.com/user-attachments/assets/351098f4-be57-49f2-bfa1-dc65a9053e97" />


## Part 3. IP Routing Tables
Next, I viewed the routing tables on two routers to confirm that OSPF had populated the routing information.

### FRR-1 – Routing Table
FRR-1 showed its directly connected networks and several OSPF-learned routes to remote subnets.  
This confirms that FRR-1 is receiving OSPF updates and has full visibility of the network.

<img width="1365" height="710" alt="FRR1-Routingtable-12315168" src="https://github.com/user-attachments/assets/ea9ae10a-2f29-4feb-ab18-204bed4db2eb" />


### FRR-3 – Routing Table
FRR-3 also displayed a mix of directly connected networks and OSPF-learned routes.  
The OSPF routes included next-hop information and metrics, showing that FRR-3 is participating fully in the OSPF domain.

<img width="1365" height="708" alt="FRR3-Routingtable-12315168" src="https://github.com/user-attachments/assets/36ebe477-76de-44f4-aecb-b7f20d0262a6" />


## Part 4. Summary of Routes
Using the routing tables from FRR-1 and FRR-3, I created a brief summary of how each router forwards traffic.

### FRR-1 – Route Summary
- **10.10.1.0/24**, **10.10.2.0/24**, **10.10.3.0/24** → directly connected  
- **10.10.4.0/24**, **10.10.5.0/24**, **10.10.6.0/24** → forwarded via next-hop router learned through OSPF

### FRR-3 – Route Summary
- **10.10.3.0/24** and **10.10.5.0/24** → directly connected  
- **10.10.1.0/24** and **10.10.2.0/24** → forwarded via next-hop on eth0  
- **10.10.4.0/24** and **10.10.6.0/24** → forwarded via next-hop on eth1

This confirms that OSPF is calculating the shortest paths and distributing routing information correctly.

## Part 5. Traceroute Before Link Failure
Before simulating any failures, I ran a traceroute from **Host1** to **10.10.6.102**.  
The output showed the normal shortest path through the network, passing through FRR-1 → FRR-3 → FRR-4 before reaching the destination.

<img width="1365" height="712" alt="TraceRoute-Before-12315168" src="https://github.com/user-attachments/assets/6d227b1f-8430-4a34-bd82-86db8b4903e7" />


## Part 6. Traceroute After Link Failure
I then removed one of the OSPF links in the topology to simulate a link failure.  
After waiting a few seconds for OSPF to reconverge, I ran the traceroute again.  
This time, the path changed, showing that OSPF had recalculated a new route to reach the destination.

<img width="1365" height="720" alt="TraceRoute-After-12315168" src="https://github.com/user-attachments/assets/0e2e5c9e-58ea-4ed1-8b03-bc4c921f1ce6" />


## Part 7. Reflection
This task demonstrated how OSPF dynamically learns routes and adapts to network changes.  
By checking neighbour tables and routing tables, I confirmed that all routers were exchanging LSAs and maintaining a consistent view of the network.  
The traceroute results before and after the link failure clearly showed OSPF reconvergence in action, with traffic automatically shifting to an alternative path.  
Overall, this task helped me understand why dynamic routing protocols like OSPF are preferred over static routing in larger or more complex networks.


