\# Windows Security Monitoring — Incident Investigation Report



\## 1. Report Overview



\*\*Project:\*\* 03-Windows-Security-Monitoring  

\*\*Lab environment:\*\* Windows Server 2025 Standard Evaluation  

\*\*Monitoring tool:\*\* Windows Event Viewer  

\*\*Log source:\*\* Windows Logs → Security  

\*\*Event investigated:\*\* 4625 — Failed logon  

\*\*Report purpose:\*\* Document observed authentication failures, evidence handling, analysis, risks, and recommendations.



This report documents an educational lab investigation. The available evidence does not confirm a malicious attack.



\## 2. Detection



The investigation began by opening Windows Event Viewer and navigating to Windows Logs → Security.



The Security log was filtered for Event ID 4625, which records failed logon attempts. Three matching event records were examined.



The records showed different timestamps and failure reasons. They are documented as separate observations and are not assumed to represent one incident.



\## 3. Timeline



The following timestamps were read from the investigated Windows Security events.



| Recorded timestamp | Account | Event ID | Observation |

|---|---|---|---|

| 12 October 2026, 1:50:36 AM | LabUser15 | 4625 | The specified account's password had expired |

| 16 October 2026, 12:31:00 AM | LabUser15 | 4625 | Unknown user name or bad password |

| 19 October 2026, 12:52:04 AM | Administrator | 4625 | Failed logon; the available details do not establish the cause conclusively |



These are the event timestamps recorded in the Windows Security log. They are not a complete timeline of a single confirmed incident.



\## 4. Evidence



Nine screenshots were retained in the project's `screenshots/` folder.



1\. `01-Project-Folder-Structure.png` — Project folder structure

2\. `02-Event-Viewer-Opened.png` — Event Viewer opened

3\. `03-Windows-Logs-Expanded.png` — Windows Logs expanded

4\. `04-Security-Log-Opened.png` — Security log opened

5\. `05-Failed-Logon-Events.png` — Filtered failed-logon events

6\. `06-Failed-Logon-Event-Details.png` — Failed-logon event details

7\. `07-Test-Account-Failure-Details.png` — Test-account authentication failure

8\. `08-Expired-Password-Failure.png` — Expired-password failure

9\. `09-Expired-Password-Event-Details.png` — Expired-password event details



The `Evidence-Inventory.txt` file lists these screenshots. The chain-of-custody notes record the storage location and state that no evidence transfer has been recorded.



\## 5. Analysis



\### Event A — Administrator



\- Event ID: 4625

\- Recorded timestamp: 19 October 2026, 12:52:04 AM

\- Account: Administrator

\- Computer: WIN-SERVER-LAB

\- Status: `0xC000010B`

\- Source address: `::1`

\- Source port: 0



The event records a failed logon. The displayed failure reason and available status details do not establish a definitive cause. The source address is a loopback address, but that alone does not explain why the logon failed.



\### Event B — LabUser15



\- Event ID: 4625

\- Recorded timestamp: 16 October 2026, 12:31:00 AM

\- Account: LabUser15

\- Logon type: 2 (Interactive)

\- Failure reason: Unknown user name or bad password

\- Status: `0xC000006D`

\- Substatus: `0xC000006A`

\- Caller process shown: Microsoft Edge



The recorded failure is consistent with an unsuccessful authentication attempt involving the displayed account and failure reason. The event alone does not establish whether the cause was user error or malicious activity.



\### Event C — LabUser15



\- Event ID: 4625

\- Recorded timestamp: 12 October 2026, 1:50:36 AM

\- Account: LabUser15

\- Failure reason: The specified account's password has expired

\- Status: `0xC0000224`

\- Source address: `127.0.0.1`

\- Source port: 0



The event records an expired-password failure. The loopback source address indicates a local host address; it does not independently prove malicious activity.



\### Overall assessment



The three records document failed authentication for different reasons. No confirmed attack, attacker identity, or single related incident has been established from these records alone.



\## 6. Containment



No specific containment action is recorded in the evidence collected for this report.



Because the observed records do not independently confirm a malicious incident, this report does not claim that an account was disabled, a host was isolated, or an attacker was blocked.



If future investigation identifies credible malicious activity, appropriate containment should be selected based on the evidence and documented at the time it occurs.



\## 7. Recovery



No specific recovery action is recorded in the collected evidence.



This report does not claim that a system was restored, a password was changed, or an account was recovered as part of the investigation.



Any future recovery should be documented and verified before being reported as complete.



\## 8. Recommendations



1\. Review failed-logon events in context and investigate unusual patterns.

2\. Check account status and password-expiration issues when relevant.

3\. Continue reviewing Windows Security logs.

4\. Preserve original screenshots and document evidence access or transfers.

5\. Reassess the preliminary risks in `Risk-Register.txt` when additional evidence is available.

6\. Follow the requirements in `Lab-Security-Policy.txt`.

7\. Record any future containment or recovery actions accurately, including their actual timestamps and verification results.



\## 9. Lessons Learned



\- Windows Event Viewer provides useful evidence for authentication investigations.

\- Event IDs, timestamps, account names, status codes, and failure reasons help structure analysis.

\- Failed logons do not automatically establish malicious activity.

\- Different event timestamps and reasons should not be treated as one incident without supporting evidence.

\- Evidence inventories and chain-of-custody records help document how evidence is stored and handled.

\- Risk registers and security policies provide a structured way to record potential weaknesses and recommended controls.

\- Investigation reports should distinguish observed facts, interpretations, and actions actually performed.



\## 10. Limitations



This report is based on three examined Event ID 4625 records and the nine project screenshots. It does not establish a confirmed security breach or a complete incident timeline.



No containment or recovery actions are claimed because none are documented in the collected evidence. Risk ratings remain preliminary estimates.



\## 11. Related Project Files



\- `README.md` — Project overview and findings

\- `Evidence-Inventory.txt` — Screenshot inventory and chain-of-custody notes

\- `Risk-Register.txt` — Preliminary risk assessment

\- `Lab-Security-Policy.txt` — Lab security requirements

\- `screenshots/` — Nine retained screenshots

