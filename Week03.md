# Week 03 – Simple Application Communications & Netcat

# Task 1. Netcat Basic Communication

## Part 1. Starting Server and Client
Host1 was used as the Netcat server and Host2 as the client.  
Both consoles were opened side‑by‑side.  
The server was started on Host1 and Host2 connected to it.

### Commands Used

Host1 (Server):
``` nc -l -p 4444 ```

Host2 (Client):
``` nc 10.10.2.1 4444 ```

## Part 2. Message Exchange
After the connection was established, I sent my name from Host2 to Host1.  
Then I sent my student ID from Host1 back to Host2.

Messages:

- Host2 → Host1: Ashraf Mehdi Khan  
- Host1 → Host2: 12315168

## Screenshot
<img width="1365" height="718" alt="Week03-Netcat-Communication-12315168" src="https://github.com/user-attachments/assets/ffd66311-c629-45de-9445-044e3b7628e8" />



# Task 2. Netcat File Transfer

## Part 1. Creating the File on Host2
A small text file was created on Host2 to be transferred to Host1.

### Commands Used
Host2 (Create File):
``` echo "This is my Week 03 file" > Week03.txt ``` 
``` cat Week03.txt ```

Host1 (Receiver):
``` nc -l -p 5555 > received.txt ```

Host2 (Sender):
``` nc 10.10.2.1 5555 < Week03.txt ```

Host1 (Verify):
``` cat received.txt ```

## Screenshot
<img width="1365" height="720" alt="Week03-Netcat-FileTransfer-12315168" src="https://github.com/user-attachments/assets/48cecc53-23e1-4284-a21a-418815371f12" />
