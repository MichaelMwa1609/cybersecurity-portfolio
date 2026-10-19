\# Day 19 — Logging and SIEM



\## 1. Objective



Learn how Windows records security events, how to investigate successful and failed logons, and how Security Information and Event Management (SIEM) tools help security analysts monitor systems.



\## 2. Security+ Study Notes



\### What is a log?



A log is a record of activity or events on a computer, application, or network.



Examples include:

\- Successful and failed login attempts.

\- User account changes.

\- Password-change attempts.

\- Windows services starting or stopping.

\- Firewall activity.



\### What is SIEM?



SIEM stands for Security Information and Event Management.



A SIEM collects and analyzes logs from multiple sources in one central location. It helps security analysts identify suspicious activity, connect related events, and investigate possible security incidents.



\### Important terminology



\- \*\*Log:\*\* A record of an activity or event.

\- \*\*Event:\*\* Something that happened on a system.

\- \*\*Log aggregation:\*\* Bringing logs together from multiple sources.

\- \*\*Event correlation:\*\* Connecting related events to identify patterns.

\- \*\*Alert:\*\* A notification about activity that may require investigation.

\- \*\*Windows Event Viewer:\*\* A built-in Windows tool for viewing and investigating event logs.

\- \*\*SIEM:\*\* A platform that centralizes and analyzes security information.



An alert or individual event does not automatically prove an attack. Analysts must investigate the evidence and surrounding context.



\## 3. Professor Messer Study



Completed the following Professor Messer CompTIA Security+ SY0-701 videos:



1\. Log Data — Objective 4.9.

2\. Security Monitoring — Objective 4.4.



\### What I learned from the videos



\- Systems record events that can be used during security investigations.

\- Different sources, including Windows computers and firewalls, generate logs.

\- Centralized logging makes it easier to review information from multiple systems.

\- SIEM tools help correlate events and identify suspicious patterns.

\- Security analysts investigate alerts rather than automatically assuming an attack occurred.



\## 4. Lab Environment



\*\*Lab:\*\* Windows Event Viewer Security Log Investigation



\*\*Computer:\*\* WIN-SERVER-LAB



\*\*Test account:\*\* LabUser15



\*\*Tool used:\*\* Windows Event Viewer



\*\*Log examined:\*\* Windows Logs → Security



\### Step 1: Open Event Viewer



Opened Event Viewer using:



`eventvwr.msc`



Expanded Windows Logs to view Application, Security, Setup, System, and Forwarded Events.



\### Step 2: Access the Security log



Initially, the Day 15 test account could not open the Security log. Event Viewer displayed:



“Access is denied. (5)”



Opened Event Viewer with Administrator privileges. The Security log then became accessible.



\*\*Lesson learned:\*\* Access to security logs may require elevated privileges. Least privilege means using a normal account for everyday activities and administrative privileges only when necessary.



\### Step 3: Investigate Event ID 4672



\*\*Description:\*\* Special privileges assigned to new logon.



Findings:

\- Event ID: 4672.

\- Account shown: SYSTEM.

\- Log: Security.

\- Level: Information.

\- Task category: Special Logon.

\- Keywords: Audit Success.



\*\*Interpretation:\*\* Windows recorded a logon with special privileges. This can occur during normal system operations and is not, by itself, evidence of malicious activity.



\### Step 4: Investigate Event ID 4624



Event ID 4624 records a successful logon.



Two events were examined.



\*\*First event:\*\*

\- Event ID: 4624.

\- Logon Type: 5.

\- New Logon account: SYSTEM.



Logon Type 5 means a service logon. This is associated with a service signing in under an account.



\*\*Second event:\*\*

\- Event ID: 4624.

\- Logon Type: 2.



Logon Type 2 means an interactive logon, such as a person signing in locally.



\*\*Lesson learned:\*\* The event ID identifies the type of event, while the logon type provides additional context about how the logon occurred.



\### Step 5: Investigate Event ID 4625



\*\*Description:\*\* An account failed to log on.



Findings:

\- Event ID: 4625.

\- Logon Type: 2 — Interactive.

\- Keywords: Audit Failure.

\- Logged: 12 October 2026, 1:50:36 AM.

\- Computer: WIN-SERVER-LAB.



\*\*Failure reason displayed:\*\*



“The specified account's password has expired.”



\*\*Interpretation:\*\* Windows recorded a failed interactive logon because the account's password had expired.



A failed logon may result from an ordinary account issue or suspicious activity. The reason and surrounding evidence must be considered before drawing conclusions.



\### Step 6: Inspect failed-logon details



Opened the Details tab for Event ID 4625 and inspected the available event fields.



This step demonstrated how an analyst can examine structured event information to investigate authentication failures.



\### Step 7: Review the Security event timeline



Reviewed the Security log and observed the following events on 12 October 2026:



\- 1:50:36 AM — Event ID 4625: Failed logon.

\- 1:52:35 AM — Event ID 4723: Password-change attempt.

\- 1:52:35 AM — Event ID 4624: Successful logon.

\- 1:52:38 AM — Event ID 4624: Successful logon.

\- 1:52:38 AM — Event ID 4672: Special privileges assigned.



\*\*Interpretation:\*\* The timestamps provide a timeline for investigation. Events occurring close together in time are worth examining in context, but their timing alone does not prove they are related.



\### Step 8: Investigate Event ID 4723



\*\*Description:\*\* An attempt was made to change an account's password.



Findings:

\- Event ID: 4723.

\- Target account: LabUser15.

\- Target domain name shown: WIN-SERVER-LAB.

\- Logged: 12 October 2026, 1:52:35 AM.

\- Task category: User Account Management.

\- Keywords: Audit Success.



\*\*Interpretation:\*\* Windows recorded an audited attempt to change the password for LabUser15.



Audit Success means the event was successfully audited and recorded. It does not, by itself, prove that the password change succeeded.



\## 5. Event IDs and Logon Types to Remember



\### Important Windows Security Event IDs



\- \*\*4624:\*\* Successful logon.

\- \*\*4625:\*\* Failed logon.

\- \*\*4672:\*\* Special privileges assigned to a new logon.

\- \*\*4723:\*\* Attempt to change an account's password.



\### Important Logon Types



\- \*\*Logon Type 2:\*\* Interactive logon.

\- \*\*Logon Type 5:\*\* Service logon.

\- \*\*Logon Type 3:\*\* Network logon.

\- \*\*Logon Type 10:\*\* Remote Interactive logon, commonly associated with Remote Desktop.



\## 6. Screenshots Saved



All screenshots are saved in:



`Day-19-Logging-and-SIEM/screenshots`



The filenames use sequential numbering and do not include a day number.



1\. `01-Event-Viewer-Opened.png` — Event Viewer with Windows Logs expanded.

2\. `02-Security-Log-Opened.png` — Security log opened with Administrator privileges.

3\. `03-Special-Privileges-Event.png` — Event ID 4672 properties.

4\. `04-Successful-Logon-Event.png` — Event ID 4624 service logon example.

5\. `05-Logon-Event-Comparison.png` — Event ID 4624 interactive logon example.

6\. `06-Failed-Logon-Event.png` — Event ID 4625 properties.

7\. `07-Failed-Logon-Details.png` — Details tab for the failed-logon event.

8\. `08-Security-Event-Timeline.png` — Security log showing event IDs and timestamps.

9\. `09-Password-Change-Event.png` — Event ID 4723 password-change attempt.



All nine screenshots were checked and confirmed saved.



\## 7. What I Learned



1\. How to open Windows Event Viewer.

2\. How to access and inspect the Windows Security log.

3\. Why administrative privileges may be required to view security logs.

4\. How to identify successful and failed logons using Event IDs 4624 and 4625.

5\. How to interpret Logon Types 2 and 5.

6\. How to recognize Event ID 4672 and privileged logon activity.

7\. How to investigate a password-change attempt using Event ID 4723.

8\. How to compare timestamps and build a basic event timeline.

9\. Why analysts must investigate context instead of assuming every event is malicious.

10\. How centralized logging and SIEM tools support security monitoring.



\## 8. Final Takeaways



\- Windows Event Viewer is useful for investigating operating-system and security events.

\- Security logs provide evidence about authentication and account-management activity.

\- Event IDs, logon types, account details, and timestamps help analysts understand what happened.

\- A failed login or password-change attempt does not automatically indicate an attack.

\- SIEM tools centralize and correlate logs to help analysts investigate possible incidents.

\- Accurate documentation and screenshots provide evidence of the investigation performed.



\*\*Day 19 topic: Logging and SIEM.\*\*

