\# Nmap Network Security Assessment



\## 1. Overview



This assessment was performed in a controlled home lab environment using Kali Linux and Ubuntu virtual machines.



The purpose of the assessment was to identify hosts and services exposed on the lab network using Nmap.



\## 2. Environment



\* \*\*Security testing system:\*\* Kali Linux

\* \*\*Target system:\*\* Ubuntu Linux

\* \*\*Network:\*\* VirtualBox Host-Only Network

\* \*\*Tool used:\*\* Nmap



\## 3. Scans Performed



\### Basic Host Scan



A basic Nmap scan was performed to identify available hosts and determine which systems responded on the lab network.



Evidence:



\* `scans/basic-scan.txt`



\### Service Detection Scan



A service detection scan was performed to identify services and their versions running on the target system.



Evidence:



\* `scans/service-scan.txt`



\## 4. Findings



The scans demonstrated how Nmap can be used to:



\* Identify reachable systems on a network.

\* Identify open ports.

\* Determine which network services are exposed.

\* Collect service and version information for further security assessment.



The detailed scan output is stored in the `scans` directory.



\## 5. Security Considerations



Exposed services increase the attack surface of a system. In a real environment, unnecessary services should be disabled or restricted, and required services should be properly secured and monitored.



This assessment was conducted only against systems in the authorized lab environment.



\## 6. Conclusion



The assessment demonstrated the basic use of Nmap for network discovery and service enumeration.



The scan results provide evidence that can be used for further security analysis and documentation.



\## 7. Evidence



\* `scans/basic-scan.txt`

\* `scans/service-scan.txt`



