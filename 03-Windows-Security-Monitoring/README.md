\# Project 3: Windows Security Monitoring \& Incident Investigation



\## 1. Project Overview



This project demonstrates basic Windows security monitoring, authentication-event investigation, digital evidence handling, risk assessment, and security policy documentation.



The project follows the Windows Security Monitoring section of the Security+ 30-Day Study Plan \& Cybersecurity Home Lab Portfolio Guide.



\## 2. Lab Environment



\- Operating system: Windows Server 2025 Standard Evaluation

\- Monitoring tool: Windows Event Viewer

\- Log source: Windows Logs → Security

\- Evidence storage: `screenshots/`

\- Project documentation: `README.md` and `report/report.md`



\## 3. Objectives



\- Review Windows Security events.

\- Examine failed-logon events.

\- Record relevant event details and possible explanations.

\- Preserve evidence and document chain of custody.

\- Identify and assess potential security risks.

\- Establish basic security requirements for the lab.



\## 4. Methodology



1\. Opened Windows Event Viewer.

2\. Navigated to Windows Logs → Security.

3\. Filtered for Event ID 4625, which records failed logon attempts.

4\. Examined event details, including account names, timestamps, logon information, and failure reasons where available.

5\. Saved screenshots of the environment and observed events.

6\. Created an evidence inventory and chain-of-custody notes.

7\. Created a preliminary risk register.

8\. Created a lab security policy.



\## 5. Findings



Three failed-logon event records were examined.



\### Finding 1 — Administrator



\- Event ID: 4625

\- Recorded timestamp: 19 October 2026, 12:52:04 AM

\- Account: Administrator

\- Computer: WIN-SERVER-LAB

\- Status: `0xC000010B`

\- Source address: `::1`

\- Observation: The event records a failed logon. The available details do not establish the cause conclusively.



\### Finding 2 — LabUser15



\- Event ID: 4625

\- Recorded timestamp: 16 October 2026, 12:31:00 AM

\- Account: LabUser15

\- Logon type: 2 (Interactive)

\- Failure reason: Unknown user name or bad password

\- Status: `0xC000006D`

\- Substatus: `0xC000006A`

\- Observation: The event records an authentication failure associated with the account and the displayed failure reason.



\### Finding 3 — LabUser15



\- Event ID: 4625

\- Recorded timestamp: 12 October 2026, 1:50:36 AM

\- Account: LabUser15

\- Failure reason: The specified account's password has expired

\- Status: `0xC0000224`

\- Observation: The event records an expired-password authentication failure.



These events occurred at different times and have different recorded reasons. They are documented as separate observations; the available evidence does not confirm that they form one incident or prove malicious activity.



\## 6. Risk Management



`Risk-Register.txt` records preliminary risks related to authentication failures, evidence handling, and account monitoring.



The likelihood and impact ratings are initial educational estimates and should be reassessed if further evidence becomes available.



\## 7. Evidence Handling



`Evidence-Inventory.txt` lists nine project screenshots. Chain-of-custody notes record the current storage location and state that no transfer has been recorded.



Original screenshots should be preserved unchanged, and any future evidence access or transfer should be documented.



\## 8. Lab Security Policy



`Lab-Security-Policy.txt` documents basic requirements for authorised lab use, account security, logging, evidence handling, incident reporting, and review.



\## 9. Screenshots



All screenshots are stored in `screenshots/`.



1\. `01-Project-Folder-Structure.png`

2\. `02-Event-Viewer-Opened.png`

3\. `03-Windows-Logs-Expanded.png`

4\. `04-Security-Log-Opened.png`

5\. `05-Failed-Logon-Events.png`

6\. `06-Failed-Logon-Event-Details.png`

7\. `07-Test-Account-Failure-Details.png`

8\. `08-Expired-Password-Failure.png`

9\. `09-Expired-Password-Event-Details.png`



\## 10. Recommendations



\- Investigate failed logons in context rather than treating every failure as an attack.

\- Review account status and password-expiration issues.

\- Continue reviewing relevant Windows Security events.

\- Preserve original evidence and document evidence handling.

\- Reassess preliminary risks when new information becomes available.



\## 11. Lessons Learned



\- Windows Event Viewer provides useful authentication-event evidence.

\- Event IDs, timestamps, account details, and failure reasons help structure an investigation.

\- Failed logons need context and do not independently prove malicious activity.

\- Evidence inventories and chain-of-custody records support evidence integrity.

\- Risk registers and security policies help organise security improvements.



\## 12. Limitations



This project is an educational lab exercise. The findings are limited to the observed records and screenshots. No confirmed malicious activity, complete incident timeline, or verified containment and recovery action is claimed.



\## 13. Project Status



Project documentation is being completed as part of the Security+ 30-day study and home lab plan.

