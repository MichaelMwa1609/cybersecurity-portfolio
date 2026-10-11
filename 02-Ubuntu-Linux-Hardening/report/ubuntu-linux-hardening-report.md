\# Ubuntu Linux Hardening Report



\## 1. Project Overview



\*\*Project:\*\* Ubuntu Linux Hardening  

\*\*Target System:\*\* Ubuntu Linux Virtual Machine  

\*\*Target IP Address:\*\* `192.168.56.102`  

\*\*Assessment Tool:\*\* Kali Linux and Nmap



\### Objective



The objective of this project was to investigate an Ubuntu Linux system, review its security configuration, examine running services and network exposure, and document recommendations to improve its security.



\## 2. Security Assessment



The following areas were examined during the assessment:



\- User accounts and group membership

\- Sudo group membership and permissions

\- File permissions for `/etc/passwd`

\- Running services and listening network ports

\- SSH service status

\- Home directory permissions

\- UFW firewall configuration

\- Automatic security updates



\## 3. Key Findings



\### 3.1 Firewall Configuration



The UFW firewall was active.



The recorded firewall configuration showed:



\- Incoming traffic: Denied by default

\- Outgoing traffic: Allowed by default

\- Routed traffic: Disabled

\- No numbered firewall rules were displayed during the check.



\*\*Recommendation:\*\* Continue using a default-deny incoming policy and permit only the network traffic required for the system's intended purpose.



\### 3.2 Listening Services



The service investigation identified listening ports associated with:



\- \*\*Port 22:\*\* SSH remote administration

\- \*\*Port 53:\*\* DNS-related service activity on a loopback interface

\- \*\*Port 631:\*\* Printing service

\- \*\*Port 323:\*\* Local service activity



The presence of a listening port does not automatically indicate a vulnerability. Services should be checked to determine whether they are required and whether they are exposed beyond the intended interfaces.



\*\*Recommendation:\*\* Disable unnecessary services and restrict remote administration to trusted systems or networks.



\### 3.3 SSH Configuration



The SSH service was enabled and active, listening on IPv4 and IPv6 port 22.



\*\*Recommendation:\*\* Use SSH key-based authentication where appropriate, restrict access to trusted sources, and review authentication settings to reduce unauthorized access risk.



\### 3.4 User Accounts and Permissions



The assessment included checks of user account information, sudo group membership, account identity, and file permissions.



The permissions of `/etc/passwd` were inspected as part of the review.



\*\*Recommendation:\*\* Apply the principle of least privilege, grant administrative access only when required, and regularly review account permissions and group membership.



\### 3.5 Automatic Security Updates



The unattended-upgrades service was enabled and running. The configuration and logs were also reviewed.



The log indicated that no packages were available for unattended upgrading at the time of the check.



The package upgrade command reported that 18 packages were not upgraded because of phased updates.



\*\*Recommendation:\*\* Continue monitoring security updates and review package status regularly. Confirm that important security patches are installed when they become available.



\## 4. Nmap Network Scan Results



Nmap scans were performed from Kali Linux against the Ubuntu virtual machine at `192.168.56.102`.



The recorded baseline and final scans reported that:



\- The target host was reachable.

\- All 1,000 scanned default TCP ports were reported as filtered.

\- No open TCP ports were identified in the scanned port range.



Filtered ports indicate that Nmap could not determine whether those ports were open or closed, often because of firewall filtering or other network controls.



\### Scan Limitation



The baseline scan files were created after the initial hardening checks rather than before the hardening work began. Therefore, these scans cannot establish a reliable before-and-after comparison of the system's security posture.



The scans provide evidence of the network exposure observed during the recorded tests, but they do not prove that hardening caused the filtered-port results.



\## 5. Recommendations



1\. Maintain a default-deny incoming firewall policy.

2\. Allow only necessary network services and ports.

3\. Secure SSH access and restrict it to trusted sources.

4\. Review user accounts, sudo membership, and permissions regularly.

5\. Disable services that are not required.

6\. Monitor security updates and verify that important patches are installed.

7\. Save dated baseline and final scans for future assessments.

8\. Review logs and repeat security checks periodically.



\## 6. Conclusion



The Ubuntu Linux Hardening project provided practical experience in Linux security assessment, user and permission review, firewall verification, service investigation, update monitoring, and network scanning.



The assessment confirmed that UFW was active and that all 1,000 default TCP ports scanned by Nmap were reported as filtered. The review also identified services and configuration areas that should be monitored and secured according to operational requirements.



Because the baseline scans were not captured before hardening, the available evidence does not demonstrate a measured before-and-after improvement. Future assessments should capture an initial scan before making configuration changes and repeat the same scan afterward.



\## 7. Evidence and Supporting Files



Supporting evidence is stored in the project folders:



\- `scans/project2-baseline-scan.txt`

\- `scans/project2-final-scan.txt`

\- `scans/project2-scan-comparison.txt`

\- `screenshots/`

\- `Readme.md`



These files support the documented assessment findings and provide a record of the work completed.



