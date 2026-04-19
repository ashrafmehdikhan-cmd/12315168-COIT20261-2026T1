# Week 02 – IP Addressing & Basic Connectivity

# Task 1. Setting Static IP Addresses

## Part 1. Export Project
The project **Setting-IP-<studentid>** was exported and saved inside the **Week_02** directory.  
This exported file contains the complete GNS3 topology used for all tasks in Week 02.

## Part 2. Screenshot of Network Topology
The following screenshot shows the full network topology, including:
- Four Linux hosts (Host1, Host2, Host3, Host4)
- One Ethernet switch
- All connections between hosts and switch
- Project annotations (student name, student ID, date)

**Screenshot:**  <img width="1365" height="707" alt="Network-Topology-12315168" src="https://github.com/user-attachments/assets/8f448823-f89a-4e2d-b70b-d9813809e7a5" />


## Part 3. Screenshots of IP Addresses

Each host was assigned a static IP address on the **10.10.2.0/24** network.  
The switch ports used were **Ethernet0/0, Ethernet0/1, Ethernet0/2, Ethernet0/3**.

### Host1 – IP Address

**Screenshot:** <img width="1365" height="718" alt="Host1-IP-12315168" src="https://github.com/user-attachments/assets/2d3e90d2-cac1-454d-8914-5c6dd4bb0c8a" />


### Host2 – IP Address

**Screenshot:** <img width="1365" height="712" alt="Host2-IP-12315168" src="https://github.com/user-attachments/assets/a3162b47-1b0e-42a3-943b-efd5793d4278" />


### Host3 – IP Address

**Screenshot:** <img width="1365" height="709" alt="Host3-IP-12315168" src="https://github.com/user-attachments/assets/8549024d-eae7-4f47-a62c-3c81e91f630a" />


### Host4 – IP Address

**Screenshot:** <img width="1365" height="717" alt="Host4-IP-12315168" src="https://github.com/user-attachments/assets/a8b901aa-352a-48d4-8c83-7ecb08d9f109" />


## Reflection
In this task, I configured static IP addresses on four Linux hosts using different methods.  
I used:
- The GNS3 GUI network configuration
- Editing `/etc/network/interfaces`
- CLI commands such as `ip address add`

I verified each configuration using `ip address show`.  
This helped me understand how Linux handles network interfaces and how devices communicate within the same subnet.

# Task 2. Testing Network Connectivity and Delay with Ping

## Part 1. Ping to a Correct IP Address
A simple ping test was performed from one host to another on the same network.


**Screenshot:** <img width="1365" height="706" alt="Ping-CorrectIP-12315168 png" src="https://github.com/user-attachments/assets/0497b06c-675e-479f-93ad-81f6dea85488" />


## Part 2. Ping to a Wrong / Unused IP Address
A ping test was performed to an IP address that does not exist on the network.


**Screenshot:** <img width="1365" height="710" alt="Ping-WrongIP-12315168 png" src="https://github.com/user-attachments/assets/79ddd8dd-7d60-4ec5-b1b1-58231994c373" />


## Part 3. Ping with Options
A ping test was performed using additional options:
- `-c` (count)
- `-i` (interval)
- `-s` (packet size)


**Screenshot:** <img width="1365" height="710" alt="Ping-Options-12315168 png" src="https://github.com/user-attachments/assets/04b21cf7-3bd6-40f6-87f2-d1990848b474" />


## Reflection
This task helped me understand how to test connectivity and diagnose network issues.  
I observed:
- Successful pings show low latency and 0% packet loss.
- Pinging an unused IP results in “Destination Host Unreachable.”
- Changing packet size, interval, and count affects the timing and output.

Overall, I now feel more confident using `ping` to test network performance and troubleshoot connectivity problems.
