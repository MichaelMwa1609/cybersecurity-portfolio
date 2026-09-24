## Hands-On Lab

### Lab Environment

* Kali Linux and Ubuntu running in VirtualBox
* Both VMs use NAT and Host-only networking

### Ubuntu IP Address

* Ubuntu Host-only IP: `192.168.56.102`

### Connectivity Test

* From Kali Linux, I successfully pinged Ubuntu at `192.168.56.102`.
* This confirmed that Kali Linux and Ubuntu can communicate over the Host-only network.

### Nmap Scan

* Command used: `nmap 192.168.56.102`
* The scan identified open ports and network services on Ubuntu.

### Service Detection

* Command used: `nmap -sV 192.168.56.102`
* This identified services and their versions running on Ubuntu.

### Security Concepts Demonstrated

* Network connectivity
* Network reconnaissance
* Open ports
* Network services
* Service/version detection
* Attack surface

### Screenshots

1. Ubuntu IP
2. Connectivity
3. Nmap Scan
4. Service Detection
