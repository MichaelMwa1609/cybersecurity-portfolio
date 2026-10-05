\# Day 10 — Ports, Protocols \& Firewall



\## Security+ Topics



Today I studied:

\- Network ports and protocols

\- TCP and UDP

\- Secure vs. insecure protocols

\- Firewall concepts



\## Common Ports Reviewed



\- TCP 22 — SSH

\- TCP 21 — FTP

\- TCP 443 — HTTPS

\- Port 53 — DNS



\## Ubuntu Lab



\### IP Address



Command used:



&#x20;   ip addr



Ubuntu lab IP:



&#x20;   192.168.56.102/24



\### Listening Services



Command used:



&#x20;   ss -tulpn



This command was used to view listening TCP and UDP ports and services on Ubuntu.



\### Firewall



Command used:



&#x20;   sudo ufw status verbose



Results:

\- Status: active

\- Logging: on (low)

\- Incoming: deny

\- Outgoing: allow

\- Routed: disabled

\- New profiles: skip



\## Security Observation



The Ubuntu firewall is active and denies incoming connections by default while allowing outgoing connections.



\## Practice Questions



Score: 3/5



Topics I need to review:

\- SSH uses TCP port 22

\- FTP uses TCP port 21



\## What I Learned



I learned how to identify my Ubuntu IP address, view listening network services and ports, and check the current UFW firewall status. I also reviewed common Security+ ports and protocols.

