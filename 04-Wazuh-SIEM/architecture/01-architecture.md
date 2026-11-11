\## Architecture - 04-Wazuh-SIEM



\- Wazuh Server: 192.168.56.104 - Wazuh Manager + Indexer + Dashboard

\- Agent 001: windows-pc - 192.168.56.1 - Windows 11 Pro

\- Agent 002: michael - 192.168.56.102 - Ubuntu 26.04.1 LTS



\## How It Works



\- Agents collect logs on Windows and Linux hosts

\- Agents send logs to Wazuh Manager on 192.168.56.104

\- Manager analyzes logs with rules, SCA, FIM, and Vulnerability Detection

\- Indexer stores alerts

\- Dashboard shows alerts, agents, and compliance



\## Flow



\- windows-pc (001) -> Wazuh Manager (192.168.56.104) -> Dashboard

\- michael (002) -> Wazuh Manager (192.168.56.104) -> Dashboard



\## Components



\- Wazuh Manager: Receives and analyzes agent data

\- Wazuh Indexer: Stores alerts and events

\- Wazuh Dashboard: Visualizes agents, alerts, SCA, FIM, vulnerabilities

\- Wazuh Agents: Installed on windows-pc and michael



\## Diagram



\- See screenshots/10-Final-SOC-Dashboard.png for final state

\- See screenshots/02-Wazuh-Dashboard.png for dashboard view

