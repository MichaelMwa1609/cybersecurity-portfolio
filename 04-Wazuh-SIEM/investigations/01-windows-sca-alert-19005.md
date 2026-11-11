\## Investigation - 09 - Windows SCA Alert



\- Alert description: SCA summary: CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0: Score less than 30% (25)

\- Alert timestamp: Nov 11, 2026 @ 22:52:08.621

\- Hostname: windows-pc

\- Agent name: windows-pc (001)

\- Rule ID and severity: Rule 19005, Level 9, Group: sca

\- Evidence: Screenshot 09-Wazuh-Alert-Investigation.png - Document Details shows rule.id 19005, rule.level 9, location: sca, manager.name: wazuh, rule.firedtimes: 1



\## Analysis



\- This is a Security Configuration Assessment (SCA) summary alert.

\- Wazuh scanned windows-pc against the CIS Windows 11 Enterprise Benchmark and scored 25.

\- The score is below the 30% threshold, so Wazuh raised a Level 9 alert.

\- This is not an intrusion, it is a compliance / hardening failure.

\- Many CIS checks failed on this host.



\## Was This Expected?



\- Yes, expected.

\- This is a lab host that has not been hardened to CIS Benchmark yet.

\- No attacker activity indicated.



\## Recommended Response



\- Review the failed CIS checks in Wazuh > SCA.

\- Harden the host - password policy, audit policy, firewall, unnecessary services.

\- Re-scan and confirm score improves above threshold.

\- No isolation needed.

\- Document appropriate containment and recovery actions when needed.

\- Record recommendations and lessons learned.

\- Use actual timestamps and findings in incident reports.

