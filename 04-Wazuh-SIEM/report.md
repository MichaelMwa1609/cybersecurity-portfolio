\## Report - 04-Wazuh-SIEM



\- Project: Wazuh SIEM Home Lab

\- Wazuh Server IP: 192.168.56.104

\- Agents: 2 active - windows-pc (001) and michael (002)

\- Date completed: Nov 12, 2026



\## Summary



\- Built a working SOC SIEM using Wazuh.

\- Connected 1 Windows host and 1 Linux host.

\- Collected logs, SCA results, FIM events, and vulnerability data in one dashboard.

\- Investigated 1 real alert end-to-end.



\## Agents



\- Agent 001: windows-pc - 192.168.56.1 - Windows 11 Pro - active

\- Agent 002: michael - 192.168.56.102 - Ubuntu 26.04.1 LTS - active



\## Findings



\- Both agents connected and reporting as Active.

\- SCA scan on windows-pc scored 25 against CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0.

\- Score was below 30% threshold, triggering Rule 19005, Level 9.

\- FIM and Vulnerability Detection enabled and reporting.

\- No intrusion found. Issue was hardening / compliance, not attack.



\## Investigation - 09



\- Alert description: SCA summary: CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0: Score less than 30% (25)

\- Alert timestamp: Nov 11, 2026 @ 22:52:08.621

\- Hostname: windows-pc

\- Agent name: windows-pc (001)

\- Rule ID and severity: Rule 19005, Level 9, Group: sca

\- Evidence: screenshots/09-Wazuh-Alert-Investigation.png

\- Analysis: SCA compliance failure, not an intrusion. Host has not been hardened to CIS Benchmark yet.

\- Was this expected: Yes, expected. Lab host not hardened yet.

\- Recommended response: Review failed CIS checks, harden host, re-scan, confirm score improves.



\## Lessons Learned



\- Wazuh needs both agents Active to give full visibility.

\- SCA alerts show configuration risk before an attacker uses it.

\- Document appropriate containment and recovery actions when needed.

\- Record recommendations and lessons learned.

\- Use actual timestamps and findings in incident reports.



\## Final State



\- Final dashboard shows Agents (2) - Active (2), Disconnected (0).

\- Screenshot: screenshots/10-Final-SOC-Dashboard.png

