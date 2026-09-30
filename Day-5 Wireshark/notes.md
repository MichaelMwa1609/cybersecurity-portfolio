# Day 5 – Wireshark Packet Capture Lab

## Objective

Use Wireshark to capture and analyze network traffic between the Kali Linux and Ubuntu virtual machines.

## Network Information

* Kali Linux IP: 192.168.56.101/24
* Ubuntu IP: 192.168.56.102/24
* Wireshark interface: eth1

## ICMP Analysis

* Captured ICMP traffic while pinging Ubuntu from Kali.
* ICMP Type 8 = Echo (ping) request.
* ICMP Type 0 = Echo (ping) reply.
* The capture showed communication between the Kali and Ubuntu IP addresses.

## ARP Analysis

* Captured ARP traffic in Wireshark.
* ARP Opcode 1 = ARP request.
* ARP Opcode 2 = ARP reply.
* The ARP packet contained sender and target IP and MAC address information.

## Evidence

1. icmp-request.png
2. icmp-reply.png
3. arp-reply.png

## What I Learned

Wireshark can capture and display network packets and can be used to identify protocols such as ICMP and ARP. I learned how to use display filters to isolate specific types of traffic and how to identify ICMP requests, ICMP replies, ARP requests, and ARP replies.
