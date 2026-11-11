\## 04-Wazuh-SIEM - Notes



\- Wazuh Server IP: 192.168.56.104

\- Wazuh Version: v4.14.10

\- Date: Nov 12, 2026



\## Agents



\- Agent 001: windows-pc - 192.168.56.1 - Windows 11 Pro - active

\- Agent 002: michael - 192.168.56.102 - Ubuntu 26.04.1 LTS - active



\## 1 - Installation



\- Installed Wazuh Server, Indexer, and Dashboard

\- Dashboard reachable at https://192.168.56.104

\- Logged in as admin



\## 2 - Dashboard



\- Dashboard shows Agents (2), Active (2), Disconnected (0)

\- Top OS: ubuntu (1), windows (1)



\## 3 - Windows Agent



\- Installed Wazuh agent on windows-pc

\- Agent enrolled and showed as active



\## 4 - Linux Agent



\- Installed Wazuh agent on michael (Ubuntu)

\- Agent enrolled and showed as active



\## 5 - SCA



\- SCA enabled on both agents

\- windows-pc scored 25 on CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0

\- Score below 30% triggered Rule 19005, Level 9



\## 6 - Threat Hunting



\- Used Events / Threat Hunting to search alerts

\- Filtered by agent: windows-pc, rule: 19005



\## 7 - FIM



\- FIM - File Integrity Monitoring enabled

\- Monitors changes to watched files



\## 8 - Vulnerability Detection



\- Vulnerability Detection enabled

\- Shows vulnerabilities found on agents



\## 9 - Alert Investigation



\- Alert: Rule 19005, Level 9, SCA summary

\- Timestamp: Nov 11, 2026 @ 22:52:08.621

\- Full write-up: investigations/01-windows-sca-alert-19005.md



\## 10 - Final Dashboard



\- Final screenshot: screenshots/10-Final-SOC-Dashboard.png

\- Both agents active at same time

