\# Day 12 — Network Security Controls



\## 1. Objective



Study Security+ network security controls and apply the concepts in the Ubuntu lab by reviewing users, administrative access, permissions, services, and firewall configuration.



The Day 12 plan focuses on network security controls and reviewing Ubuntu users, permissions, and services.



\---



\## 2. Security+ Study Notes



\### Security Controls



A security control is a safeguard used to reduce or manage security risk.



Important control concepts:



\- Preventive controls help stop an unwanted event from occurring.

\- Detective controls identify or provide evidence that an event has occurred.

\- Corrective controls help restore or correct a problem.

\- Physical controls protect physical locations, equipment, or access.

\- Technical controls use technology to protect systems and data.

\- Operational controls are carried out through people and processes.

\- Managerial controls involve management direction, policies, and risk decisions.



Examples discussed:

\- Firewalls control network traffic.

\- Access controls restrict access to resources.

\- Authentication verifies identity.

\- Logging records activity.

\- Monitoring helps identify suspicious activity.



\### Segmentation and Access Control



Network segmentation separates parts of a network so access can be controlled and the impact of a security incident can be limited.



An access control list (ACL) defines what traffic or users are allowed or denied access.



An application allow list limits systems to approved applications.



Segmentation and access controls help reduce exposure and limit the spread or impact of an incident.



\### Access Controls and Least Privilege



Least privilege means giving a user or process only the permissions needed to perform its required tasks.



Authorization determines what an authenticated user is allowed to access.



Permissions control what actions a user or process can perform on a resource.



Example:

\- If a user only needs to read a file, read access is preferable to full control.



\---



\## 3. Professor Messer Study



\### Video 1 — Security Controls



Key points reviewed:



\- Security controls reduce or manage security risk.

\- Preventive controls help prevent unwanted activity.

\- Detective controls identify activity or events.

\- Corrective controls help address problems.

\- Controls can be physical, technical, operational, or managerial.



\### Video 2 — Segmentation and Access Control



Key points reviewed:



\- Network segmentation separates network areas.

\- ACLs can allow or deny access.

\- Application allow lists restrict software to approved applications.

\- Segmentation can limit the impact of a security incident.

\- Least privilege limits access to what is required.



\### Video 3 — Access Controls



Key points reviewed:



\- Least privilege provides only necessary access.

\- Authorization determines permitted access after authentication.

\- Permissions control actions on resources.

\- Access controls limit access based on authorization.



\---



\## 4. Knowledge Checks



\### Video 1 — Security Controls



Result: 5/5



1\. Main purpose of a security control — B

2\. Preventive control example — B

3\. Control designed to identify that something happened — A

4\. Policies, procedures, and security awareness category — C

5\. Security camera — A



\### Video 2 — Segmentation and Access Control



Result: 5/5



1\. Purpose of network segmentation — B

2\. Purpose of an ACL — B

3\. Approved application list — A

4\. Security benefit of segmentation — B

5\. Limiting user access — A



\### Video 3 — Access Controls



Result: 5/5



1\. Least privilege — B

2\. Authorization — B

3\. Purpose of permissions — A

4\. Read-only access when modification is unnecessary — B

5\. Importance of access controls — B



Total: 15/15



\---



\# 5. Ubuntu Lab



\## Lab Focus



The lab reviewed:



\- Ubuntu users

\- Sudo/administrative access

\- File permissions

\- Running services

\- Listening services

\- SSH service status

\- Home-directory permissions

\- UFW firewall status

\- Current user and groups



No unnecessary configuration changes were made.



\---



\## Step 1 — Review Ubuntu Users



Command:



cat /etc/passwd



Purpose:



Review the accounts configured on the Ubuntu system.



Evidence:



01-users-list.png



\---



\## Step 2 — Review Administrative Access



Command:



getent group sudo



Purpose:



Review which accounts belong to the sudo group and therefore have administrative privileges.



Evidence:



02-sudo-users.png



\---



\## Step 3 — Review Permissions on /etc/passwd



Command:



ls -l /etc/passwd



Purpose:



Review the file owner, group, and read/write/execute permissions.



Evidence:



03-passwd-permissions.png



\---



\## Step 4 — Review Listening Services



Command:



ss -tulpn



Purpose:



Review network sockets and services that are listening.



Evidence:



04-listening-services.png



This provides information about the network-facing services and helps identify the system's attack surface.



\---



\## Step 5 — Review Running Services



Command:



systemctl --type=service --state=running



Purpose:



Review services currently running on Ubuntu.



Evidence:



05-running-services.png



The output showed multiple normal Ubuntu system services. The service list was reviewed rather than disabling services without a security or operational reason.



\---



\## Step 6 — Review SSH Service



Command:



systemctl status ssh



Finding:



\- SSH service was loaded.

\- SSH was disabled.

\- SSH was inactive (dead).

\- The output showed it was triggered by ssh.socket.



Evidence:



06-ssh-service-status.png



No change was made to SSH.



\---



\## Step 7 — Review Home-Directory Permissions



Command:



ls -ld \~



Observed result included:



drwxr-x--- ... michael michael ... /home/michael



This showed that the home directory was owned by the user and the displayed permissions restricted access for other users.



Evidence:



07-home-directory-permissions.png



\---



\## Step 8 — Review UFW Firewall



Command:



sudo ufw status verbose



Observed firewall state:



\- Status: active

\- Logging: on (low)

\- Default: deny incoming

\- Default: allow outgoing

\- Routed: disabled

\- New profiles: skip



This is an important network security control.



Evidence:



08-ufw-firewall-status.png



No firewall changes were made because the firewall was already active with a restrictive default for incoming connections.



\---



\## Step 9 — Verify Current User and Groups



Command:



id



Purpose:



Verify the current Ubuntu user identity and associated groups.



Evidence:



09-user-id-verification.png



\---



\# 6. Findings



\### Users and Administrative Access



The Ubuntu account configuration and sudo group were reviewed. This helps identify which accounts exist and which accounts have administrative privileges.



\### Permissions



Linux permissions were reviewed using /etc/passwd and the user's home directory.



The key security principle is least privilege: users should have only the permissions required for their tasks.



\### Services



Running and listening services were reviewed to understand the system's attack surface.



SSH was found to be inactive and disabled, so no change was required.



\### Firewall



UFW was already active with:



\- Incoming traffic denied by default

\- Outgoing traffic allowed by default

\- Low-level logging enabled



No unnecessary firewall modification was performed.



\---



\# 7. Verification



The lab successfully verified the current security configuration of the Ubuntu VM.



Evidence was collected for:



1\. Users

2\. Sudo access

3\. File permissions

4\. Listening services

5\. Running services

6\. SSH status

7\. Home-directory permissions

8\. Firewall status

9\. User/group identity



\---



\# 8. What I Learned



\- Security controls reduce or manage security risk.

\- Preventive, detective, and corrective controls have different purposes.

\- Network segmentation can limit exposure and the impact of incidents.

\- ACLs can control which traffic or users are allowed or denied.

\- Least privilege means providing only the access that is required.

\- Authorization determines what an authenticated user is allowed to do.

\- Linux permissions control access to files and directories.

\- Running and listening services contribute to a system's attack surface.

\- Unnecessary services should be investigated rather than automatically left exposed.

\- A firewall is an important network security control.

\- A restrictive default-deny incoming firewall policy can reduce unsolicited inbound exposure.

\- Security configuration should be reviewed before making changes.



\---



\# 9. Security+ Exam Takeaways



Remember:



Security controls → reduce risk



Preventive → stop



Detective → identify



Corrective → fix/restore



Segmentation → separate and limit exposure



ACL → allow/deny access



Least privilege → minimum required access



Authorization → what you are allowed to do



Permissions → what actions can be performed on a resource



Services → functionality that can increase attack surface



Firewall → controls network traffic



\---



\# 10. Screenshots



The Day 12 evidence set contains:



\- 01-users-list.png

\- 02-sudo-users.png

\- 03-passwd-permissions.png

\- 04-listening-services.png

\- 05-running-services.png

\- 06-ssh-service-status.png

\- 07-home-directory-permissions.png

\- 08-ufw-firewall-status.png

\- 09-user-id-verification.png



Each screenshot documents part of the Day 12 lab and can be placed in the Day 12 screenshots folder.



\---



\## Day 12 Completion



Study: Complete



Professor Messer videos: Complete



Knowledge checks: 15/15



Ubuntu lab: Complete



Evidence screenshots: Complete



Final notes: Complete

