\# Project 2: Ubuntu Linux Hardening



\## 1. Project Overview



\*\*Project:\*\* Ubuntu Linux Hardening  

\*\*Category:\*\* Cybersecurity / Linux System Security  

\*\*Environment:\*\* Ubuntu virtual machine running in Oracle VirtualBox  

\*\*Supporting machine:\*\* Kali Linux virtual machine



\### Objective



The objective of this project is to assess the security configuration of an Ubuntu Linux virtual machine, identify potential security weaknesses, apply appropriate security controls where necessary, and verify the resulting configuration.



The assessment focuses on system updates, user and administrative access, listening network services, firewall configuration, SSH security, system logs, and network exposure.



\## 2. Lab Environment



\- Ubuntu Linux virtual machine

\- Kali Linux virtual machine for network testing

\- Oracle VirtualBox

\- UFW (Uncomplicated Firewall)

\- Nmap

\- Linux system administration and log investigation commands



Testing is performed within my own virtual lab environment.



\## 3. Assessment Methodology



The project follows these stages:



1\. Review the operating system and update status.

2\. Examine user accounts and administrative group membership.

3\. Identify listening network services.

4\. Review firewall status and rules.

5\. Inspect SSH service and socket configuration.

6\. Review system and SSH logs.

7\. Apply appropriate security improvements where justified.

8\. Compare initial and final network scan results.

9\. Document findings, verification evidence, and lessons learned.



\## 4. Initial Findings



\### 4.1 System Updates



The package manager reported 18 packages that were not upgraded during the reviewed upgrade operation. A simulated upgrade indicated that the updates were deferred because of phased package updates.



This result was recorded for further review. Deferred updates should not automatically be treated as failed updates.



\### 4.2 Firewall Configuration



The reviewed UFW configuration showed:



\- Firewall status: Active

\- Incoming traffic: Denied by default

\- Outgoing traffic: Allowed by default

\- Routed traffic: Disabled

\- No numbered firewall allow or deny rules were displayed in the reviewed rules output.



The default incoming-deny policy provides a restrictive baseline. Required services and access rules should still be reviewed to ensure the configuration matches the lab's needs.



\### 4.3 Listening Services and SSH



The listening-service review identified several listening ports, including SSH on port 22, a DNS-related service on port 53, printing on port 631, and a local service on port 323.



The SSH socket was reported as enabled and active, listening on port 22 on IPv4 and IPv6 interfaces. This means SSH exposure needs to be evaluated alongside firewall rules and network scan results.



The presence of a listening service does not automatically mean it is vulnerable. Each service should be assessed for necessity and appropriate access restrictions.



\### 4.4 Automatic Updates



The automatic-update service was reported as enabled and running. The reviewed configuration enabled periodic package-list updates and unattended upgrades.



The reviewed unattended-upgrades log reported no packages available for unattended upgrading at that time.



\## 5. Security Controls and Remediation



The following controls were reviewed during the lab:



\- Package update status and automatic-update configuration

\- User and administrative access review

\- Listening-service inventory

\- UFW firewall policy and available application profiles

\- SSH service and socket configuration

\- System and SSH log review

\- Network exposure testing using Nmap



Changes should only be made when the assessment identifies a justified security improvement. Any changes must be recorded along with the reason for making them.



\## 6. Verification and Evidence



Screenshots have been collected for the Ubuntu hardening investigation. The project includes folders for initial-state evidence, final-state evidence, screenshots, scans, diagrams, and the report.



The available screenshots document several configuration and service checks. The initial and final Nmap outputs must be saved and compared before the network-exposure verification can be considered complete.



Verification should establish whether the intended configuration is active and whether any unnecessary network exposure has been reduced.



\## 7. Security Considerations



\- Use least privilege when assigning administrative access.

\- Keep the operating system and applications appropriately updated.

\- Restrict network access to services that are required.

\- Review SSH exposure and configuration carefully.

\- Monitor system and authentication logs for relevant activity.

\- Verify security changes instead of assuming they were successful.

\- Preserve evidence of the initial configuration and final results.



\## 8. Lessons Learned



This project demonstrates the importance of reviewing a Linux system as a whole rather than relying on a single security control.



A firewall can have a restrictive default policy while services still listen on network interfaces. Automatic updates can be enabled while some package updates remain deferred. Therefore, service inventory, firewall review, update checks, log analysis, and network testing should be considered together.



The project also demonstrates the value of documenting the original configuration, recording justified changes, and verifying the results with appropriate evidence.



\## 9. Project Evidence



Project evidence is organized into the following directories:



\- `before/` — Initial configuration evidence

\- `after/` — Final configuration and verification evidence

\- `screenshots/` — Supporting screenshots

\- `scans/` — Initial and final Nmap scan outputs

\- `diagrams/` — Relevant network or system diagrams

\- `report/` — Final project report



Each evidence file should have a descriptive filename and support a finding or verification step discussed in this README.



\## 10. Conclusion



This project reviews important Ubuntu Linux security controls, including updates, access privileges, listening services, firewall configuration, SSH, and logging.



The work provides practical experience in Linux security assessment, configuration review, evidence collection, and verification. The project is ready for final completion once the remaining assessment evidence, particularly the user and log reviews and the before-and-after network scan comparison, has been checked and organized.

