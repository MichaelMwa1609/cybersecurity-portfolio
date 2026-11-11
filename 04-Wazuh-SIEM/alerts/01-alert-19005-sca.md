\## Alert - Rule 19005 - SCA Summary



\- Alert description: SCA summary: CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0: Score less than 30% (25)

\- Alert timestamp: Nov 11, 2026 @ 22:52:08.621

\- Hostname: windows-pc

\- Agent name: windows-pc (001)

\- Agent IP: 192.168.56.1

\- Rule ID and severity: Rule 19005, Level 9, Group: sca

\- Wazuh Server: 192.168.56.104



\## What Happened



\- SCA scan ran on windows-pc

\- Host scored 25 out of 100 on CIS Windows 11 Benchmark

\- Score was below 30% threshold, so Wazuh raised Rule 19005



\## Evidence



\- Screenshot: screenshots/09-Wazuh-Alert-Investigation.png

\- Full investigation: investigations/01-windows-sca-alert-19005.md



\## Verdict



\- Not an intrusion. Compliance / hardening failure.

\- Host not hardened to CIS Benchmark yet.



\## Action



\- Review failed CIS checks in SCA results

\- Harden host, re-run SCA scan, confirm score improves

