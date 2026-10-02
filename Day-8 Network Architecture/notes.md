\# Day 8: Network Architecture and Segmentation



\## Study Topics

\- Network architecture

\- Network segmentation

\- VLANs

\- Zero Trust

\- Defense in depth

\- Demilitarized zones (DMZ)



\## Lab: Ubuntu Network Configuration



\### Objective

Inspect Ubuntu's network interfaces and routing table to understand its network configuration.



\### Commands Used

\- `ip addr` — displays network interfaces and IP addresses.

\- `ip route` — displays the routing table.



\### Results



\*\*Network Interface 1\*\*

\- Interface: enp0s3

\- IPv4 address: 10.0.2.15/24

\- Default gateway: 10.0.2.2



\*\*Network Interface 2\*\*

\- Interface: enp0s8

\- IPv4 address: 192.168.56.102/24

\- Connected network: 192.168.56.0/24



\### Observations

Ubuntu has two network interfaces connected to different networks.



The enp0s3 interface has a default route through 10.0.2.2.



The enp0s8 interface is connected to the 192.168.56.0/24 network, which is used for host-only networking in this lab.



\### Security Relevance

Understanding network interfaces and routing tables helps administrators troubleshoot connectivity and identify how systems communicate across networks.



Network segmentation can help separate systems and restrict unnecessary communication between network areas.



\### Evidence

\- screenshots/ubuntu-network-configuration.png



\### Conclusion

I used the `ip addr` and `ip route` commands to inspect Ubuntu's network configuration and identify its interfaces, IP addresses, and routing information.

