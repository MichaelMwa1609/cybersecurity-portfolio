## Nmap Findings

### Basic Scan
The Ubuntu VM at 192.168.56.102 was scanned from Kali Linux using Nmap.

The host was reachable, but all 1,000 default TCP ports scanned by Nmap were closed.

### Service Detection
Nmap service detection also found no open TCP services on the Ubuntu VM.

### Security Assessment
No externally accessible TCP services were identified during this assessment. Therefore, no unnecessary service was identified for remediation.

### Verification
A follow-up service detection scan confirmed that the scanned TCP ports remained closed.




## Objective

The objective of this project was to perform a basic network security assessment of an Ubuntu virtual machine from Kali Linux. The assessment focused on identifying reachable hosts, exposed TCP ports, and running network services, then evaluating whether any unnecessary services required remediation.

## Lab Environment

- Attacker VM: Kali Linux
- Target VM: Ubuntu Linux
- Virtualization platform: VirtualBox
- Network type: Host-Only Adapter
- Kali IP: 192.168.56.101
- Ubuntu IP: 192.168.56.102
- Tool used: Nmap

## Methodology

1. Verified the Ubuntu VM IP address.
2. Tested connectivity from Kali Linux to Ubuntu using ICMP ping.
3. Performed a basic Nmap scan against the Ubuntu VM.
4. Performed Nmap service detection using `-sV`.
5. Reviewed the scan results for exposed TCP ports and services.
6. Documented the findings and determined whether remediation was required.
7. Performed verification using a follow-up service scan.

## Evidence

The following screenshots document the assessment:

1. `project1-ping-ubuntu.png` — Successful connectivity test from Kali Linux to Ubuntu.
2. `project1-nmap-basic.png` — Basic Nmap scan of the Ubuntu VM.
3. `project1-nmap-services.png` — Nmap service detection scan.
4. `project1-nmap-service-results.png` — Saved service-scan results showing the scanned TCP ports were closed.

## Conclusion

The assessment confirmed that the Ubuntu VM was reachable from Kali Linux over the Host-Only network. The Nmap scans found no open TCP ports among the default 1,000 ports scanned, and no exposed services requiring remediation were identified.

This assessment demonstrated the basic process of host discovery, port scanning, service detection, security assessment, and verification.