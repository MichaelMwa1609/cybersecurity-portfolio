\# Day 11 — VPN, Wireless Security \& SSH



\## Objective



Day 11 focused on VPN and wireless security, with a practical review of SSH configuration on the Ubuntu lab VM.



\## Lab Work Completed



\### 1. Checked SSH before installation



Command:

sudo systemctl status ssh



Result:

\- `ssh.service` could not be found.

\- SSH was not installed on the Ubuntu VM.



\### 2. Confirmed OpenSSH Server was not installed



Command:

dpkg -s openssh-server



Result:

\- `openssh-server` was not installed.



\### 3. Updated Ubuntu



Command:

sudo apt update



Result:

\- Update completed successfully.

\- Ubuntu reported that 85 packages could be upgraded.



\### 4. Installed OpenSSH Server



Command:

sudo apt install openssh-server



Result:

\- OpenSSH Server installed successfully.

\- The SSH configuration file was created.

\- The SSH service was installed.



\### 5. Checked SSH service status



Command:

sudo systemctl status ssh



Result:

\- OpenSSH server was loaded.

\- Service was disabled.

\- Service was inactive (dead).

\- It was associated with `ssh.socket`.



No SSH configuration settings were changed.



\## SSH Configuration Review



\### SSH Port



The configuration contained:



\#Port 22



I checked the effective configuration with:



sudo sshd -T > /tmp/ssh-settings.txt



Then:



grep '^port ' /tmp/ssh-settings.txt



Result:



port 22



SSH is using the standard SSH port 22.



\### Password Authentication



Command:



grep '^passwordauthentication ' /tmp/ssh-settings.txt



Result:



passwordauthentication yes



Password authentication is enabled in the effective SSH configuration.



\### Public-Key Authentication



Command:



sudo grep PubkeyAuthentication /etc/ssh/sshd\_config



Result:



\#PubkeyAuthentication yes



The setting is commented out, so it was not explicitly changed during this lab.



\### Root Login



Command:



sudo grep PermitRootLogin /etc/ssh/sshd\_config



Result:



\#PermitRootLogin prohibit-password



The setting is commented out, so it was not explicitly changed during this lab.



\## Configuration Validation



Command:



sudo sshd -t



Result:

\- No error was displayed.

\- The command returned to the terminal prompt normally.

\- The SSH configuration passed the syntax check.



\## Changes Made



The main change made during the lab was installing the OpenSSH Server package.



I did not modify the SSH configuration settings.



\## Screenshots



1\. `01-SSH-Not-Installed.png` — SSH service not found.

2\. `02-APT-Update.png` — Ubuntu package update.

3\. `03-SSH-Installed.png` — OpenSSH Server installation.

4\. `04-SSH-Service-Status.png` — SSH service status.

5\. `05-SSH-Port-22.png` — Effective SSH port 22.

6\. `06-Password-Authentication.png` — Password authentication enabled.

7\. `07-Public-Key-Authentication.png` — Public-key authentication configuration.

8\. `08-Root-Login-Setting.png` — Root login configuration.

9\. `09-SSH-Config-Validation.png` — Successful SSH configuration validation.



\## Security Observations



\- SSH provides secure remote administration.

\- SSH configuration should be reviewed carefully before making changes.

\- Unnecessary remote services can increase the attack surface.

\- Authentication settings are important when securing SSH.

\- Configuration changes should be validated before restarting the SSH service.



\## What I Learned



I learned how to install and safely review OpenSSH Server on Ubuntu. I checked the SSH service status, identified the effective SSH port, reviewed authentication-related settings, checked the root-login configuration, and validated the SSH configuration without making unnecessary configuration changes.



\## Day 11 Result



Day 11 lab completed successfully.



The SSH configuration was reviewed and validated, and the work was documented with screenshots for my cybersecurity GitHub portfolio.

