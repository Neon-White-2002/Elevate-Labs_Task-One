# Elevate Labs (Cyber-Security Internship):

## Task 1: Scan Your Local Network for OPEN Ports  
## Objective: Learn to discover OPEN ports on devices in your Local Network to understand Network Exposure.  
## Tools: NMAP (Network-Map), Wire-Shark & Kali-Linux  

## Outcome:  
### Step One: First, Check your Local IP-Address  
Command: ifconfig 
<img width="1920" height="1050" alt="Screenshot From 2025-08-04 13-25-08" src="https://github.com/user-attachments/assets/1b42d214-744c-450f-81d6-863802c7927f" />
Result: Local IP-Address: 192.168.1.13 & Local IP-Range: 192.168.1.0 
 
### Step Two: Now, we will Discover various HOST, connected in Local-Network 
### Command: netdiscover -r 192.168.1.0/24 
### Result: 
<img width="1920" height="390" alt="Screenshot From 2025-08-04 13-25-55 1" src="https://github.com/user-attachments/assets/4c9b300a-3be7-45f5-9935-3544533f27d7" />

### Step Three: Now, we will Check whether the HOST are LIVE or NOT 
### Command: ping -4 192.168.1.4 
### Result: 
<img width="1920" height="1050" alt="Screenshot From 2025-08-04 13-25-55" src="https://github.com/user-attachments/assets/0cc863c1-cb8a-414e-a34b-d04c45754ac0" />

### Step Four: Now, we will Perform SYN Scan, & Discover OPEN Ports  
### Command: nmap -v -sS 192.168.1.0/24 
### Result: 
Starting Nmap 7.95 ( https://nmap.org ) at 2025-08-04 13:08 IST 
Initiating ARP Ping Scan at 13:08 
Scanning 255 hosts [1 port/host] 
Completed ARP Ping Scan at 13:08, 1.94s elapsed (255 total hosts) 
Initiating Parallel DNS resolution of 3 hosts. at 13:08 
Completed Parallel DNS resolution of 3 hosts. at 13:08, 0.08s elapsed 
Initiating Parallel DNS resolution of 1 host. at 13:08 
Completed Parallel DNS resolution of 1 host. at 13:08, 0.06s elapsed 
Initiating SYN Stealth Scan at 13:08 
Scanning 3 hosts [1000 ports/host] 
Discovered open port 443/tcp on 192.168.1.1 
Completed SYN Stealth Scan against 192.168.1.3 in 3.33s (2 hosts left) 
Increasing send delay for 192.168.1.1 from 0 to 5 due to max_successful_tryno increase to 4 
Discovered open port 5357/tcp on 192.168.1.7 
Completed SYN Stealth Scan against 192.168.1.7 in 34.62s (1 host left) 
Increasing send delay for 192.168.1.1 from 5 to 10 due to max_successful_tryno increase to 5 
Completed SYN Stealth Scan at 13:09, 71.74s elapsed (3000 total ports) 
Nmap scan report for Unit (192.168.1.1) 
Host is up (0.0037s latency). 
Not shown: 983 filtered tcp ports (no-response), 2 filtered tcp ports (port-unreach) 
PORT      STATE  SERVICE 
22/tcp    closed ssh 
443/tcp   open   https 
445/tcp   closed microsoft-ds 
631/tcp   closed ipp 
8099/tcp  closed unknown 
49153/tcp closed unknown 
49154/tcp closed unknown 
49155/tcp closed unknown 
49156/tcp closed unknown 
49157/tcp closed unknown 
49158/tcp closed unknown 
49159/tcp closed unknown 
49160/tcp closed unknown 
49161/tcp closed unknown 
49163/tcp closed unknown 
MAC Address: 00:00:00:00:00:00 (Unknown) 
 
Nmap scan report for 192.168.1.3 
Host is up (0.0053s latency). 
All 1000 scanned ports on 192.168.1.3 are in ignored states. 
Not shown: 1000 closed tcp ports (reset) 
MAC Address: 00:00:00:00:00:00 (Guangdong Oppo Mobile Telecommunications) 
 
Nmap scan report for 192.168.1.4 
Host is up (0.0056s latency). 
All 1000 scanned ports on 192.168.1.4 are in ignored states. 
Not shown: 1000 closed tcp ports (reset) 
MAC Address: 00:00:00:00:00:00 (Guangdong Oppo Mobile Telecommunications) 
 
Nmap scan report for 192.168.1.7 
Host is up (0.0012s latency). 
Not shown: 999 filtered tcp ports (no-response) 
PORT     STATE SERVICE 
5357/tcp open  wsdapi 
MAC Address: 00:00:00:00:00:00 (Cloud Network Technology (Samoa) Limited) 
 
### Step Five (Optional): Now, we can Perform SYN Scan & Check on Wire-Shark (Tool)  
So, firstly we have Open Wire-Shark, and then perform following command : 
### Command: nmap -v -sS 192.168.1.0/24 
Then, Open Wire-Shark and Apply Filter: tcp.flags.syn == 1 && tcp.flags.ack == 0 
### Result: 
<img width="1920" height="1050" alt="Screenshot From 2025-08-04 13-19-10" src="https://github.com/user-attachments/assets/5cec4ca6-a72d-4589-b7f6-8ab19efe7ec3" />
 
