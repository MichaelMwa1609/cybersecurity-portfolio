\# Day 9 – Firewalls, IDS, IPS and Proxies



\## Study Topics



\### Firewall



A firewall controls network traffic based on security rules.



Common firewall functions:



\* Allow or deny network traffic

\* Control incoming and outgoing connections

\* Apply security rules to network traffic



\### IDS – Intrusion Detection System



An IDS monitors network activity and detects suspicious or malicious activity.



\* Detects threats

\* Generates alerts

\* Does not normally block the traffic automatically



\### IPS – Intrusion Prevention System



An IPS detects suspicious activity and can automatically block or prevent the traffic.



\* Detects threats

\* Generates alerts

\* Can block malicious traffic



\### Proxy



A proxy acts as an intermediary between a client and another system.



Common uses:



\* Filtering web access

\* Logging web activity

\* Enforcing organizational web-access policies



\### WAF – Web Application Firewall



A WAF protects web applications by filtering HTTP/HTTPS traffic.



It can help protect against attacks targeting web applications.



\## Key Difference



\* Firewall = Controls network traffic

\* IDS = Detects and alerts

\* IPS = Detects and can block

\* Proxy = Acts as an intermediary

\* WAF = Protects web applications



\---



\# Ubuntu Firewall Lab



\## Initial Firewall Check



Command used:



sudo ufw status verbose



Initial result:



Status: inactive



The firewall was initially disabled.



I also checked for added firewall rules:



sudo ufw show added



No added rules were shown.



I checked the numbered firewall rules:



sudo ufw status numbered



The firewall was inactive.



\## Ubuntu IP Address



Ubuntu lab IP:



192.168.56.102/24



\## Connectivity Before Firewall



From Kali Linux, I tested connectivity to Ubuntu:



ping -c 4 192.168.56.102



The ping test was successful.



This confirmed that Kali could communicate with Ubuntu before enabling the firewall.



\## Listening Services



On Ubuntu, I used:



ss -tulpn



This command was used to view listening network services and ports.



\## Enabling UFW



I enabled the Ubuntu firewall with:



sudo ufw enable



The firewall became active.



Firewall configuration:



\* Status: active

\* Default incoming: deny

\* Default outgoing: allow

\* Routed traffic: disabled



\## Connectivity After Firewall



From Kali Linux, I tested the Ubuntu connection again:



ping -c 4 192.168.56.102



The ping test was successful after enabling UFW.



This showed that the firewall was active while the Kali-to-Ubuntu connectivity test still succeeded.



\## What I Learned



I learned the difference between firewalls, IDS, IPS, proxies and WAFs.



I also practiced checking the Ubuntu firewall status, viewing listening services, enabling UFW, and testing network connectivity before and after enabling the firewall.



The main difference between IDS and IPS is that an IDS detects and alerts, while an IPS can detect and block suspicious traffic.



\## Day 9 Lab Evidence



Screenshots saved:



\* day9-ubuntu-firewall-status.png

\* day9-kali-to-ubuntu-ping.png

\* day9-ubuntu-listening-services.png

\* day9-ubuntu-firewall-active.png

\* day9-kali-to-ubuntu-ping-after-firewall.png



\## Day 9 Quiz



Score: 5/5



Q1: B – IDS

Q2: C – IPS

Q3: A – Firewall

Q4: D – WAF

Q5: B – Web Proxy



