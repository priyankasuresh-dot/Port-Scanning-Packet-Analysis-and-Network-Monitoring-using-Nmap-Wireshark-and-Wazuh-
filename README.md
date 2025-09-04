# Port-Scanning-Packet-Analysis-and-Network-Monitoring-using-Nmap-Wireshark-and-Wazuh-
This project demonstrates network reconnaissance and monitoring using Nmap, Wireshark, and Wazuh in a controlled cybersecurity lab environment. It focuses on:

Performing various Nmap scans (TCP SYN, Connect, ACK, UDP, Xmas, Ping, Full Range, and targeted port scans) to identify open ports and services.

Capturing and analyzing network traffic in real-time using Wireshark to understand scan behavior at the packet level.

Monitoring and detecting suspicious activities using Wazuh, including alerts for promiscuous mode, port changes, and host-based anomalies.

# Lab Setup:

Attacker: Kali Linux VM (10.55.255.215)

Target: Cybersecurity Lab VM (10.55.255.145) with Wazuh agent installed

Tools: VMware Workstation, Nmap, Wireshark, Wazuh

# Objective:
Build practical skills in reconnaissance, scanning, packet analysis, and intrusion detection, essential for penetration testing and network defense.

# command list with definitions
nmap -sS <IP> → TCP SYN Scan: Stealth scan sending SYN packets without completing the handshake.

nmap -sT <IP> → TCP Connect Scan: Performs full handshake; more detectable.

nmap -sA <IP> → ACK Scan: Checks firewall rules without revealing open ports.

nmap -sU <IP> → UDP Scan: Scans UDP ports; slower and connectionless.

nmap -p 23 <IP> → Specific Port Scan: Scans only port 23 (Telnet).

nmap -p 23-100 <IP> → Port Range Scan: Scans ports from 23 to 100.

nmap -pU:110,T:23-25,443 <IP> → Mixed Scan: Scans both UDP and TCP ports.

nmap -sF <IP> → FIN Scan: Fast scan using FIN packets.

nmap -r <IP> → Sequential Scan: Scans ports in numerical order.

nmap -sX <IP> → Xmas Scan: Sends FIN, URG, PSH flags (“Christmas Tree” scan).

nmap -sL <IP> → List Scan: Lists IPs without sending packets.

nmap -sP <IP> / nmap -sn <IP> → Ping Scan: Checks if host is online using ICMP or ARP.

nmap -p- <IP> → Full Port Range Scan: Scans all 65,535 TCP ports.

nmap -F <IP> → Fast Scan: Scans top 100 common ports.

Wireshark filters for analysis:

tcp.flags.syn==1 → Capture SYN packets.

tcp.flags.ack==1 → Capture ACK packets.

tcp.flags.fin==1 → Capture FIN packets.

tcp.flags.fin==1 && tcp.flags.urg==1 && tcp.flags.push==1 → Capture Xmas scan packets.

tcp.port==23 → Capture traffic on port 23 (Telnet).

udp → Capture UDP traffic.

icmp → Capture ICMP ping packets.

arp → Capture ARP requests/replies.

dns → Capture DNS queries.
# summary
his project demonstrates network reconnaissance, scanning, and monitoring using Nmap, Wireshark, and Wazuh in a controlled cybersecurity lab. The goal is to understand how different types of port scans work, how they appear at the packet level, and how security monitoring tools detect suspicious activities.
