# Day 4 – Ubuntu Service Investigation

## Objective

Investigate services exposed by the Ubuntu VM, identify an unnecessary network-exposed service, remediate it, and verify the result.

## Lab Environment

- Virtualization: VirtualBox
- Attacking/assessment VM: Kali Linux
- Target VM: Ubuntu
- Ubuntu IP address: 192.168.56.102

## Connectivity

Kali successfully communicated with Ubuntu.

- Ubuntu IP: 192.168.56.102
- Packets transmitted: 4
- Packets received: 4
- Packet loss: 0%

## Service Investigation

The Ubuntu listening-services check showed several local services.

Avahi was identified as listening on UDP port 5353:

- Service: Avahi
- Port: 5353/UDP
- Address: 0.0.0.0:5353
- IPv6: [::]:5353

The Avahi service was confirmed as active and enabled.

## Service Assessment

Avahi was investigated before making any changes.

The investigation showed that Avahi was associated with the Ubuntu printing/service-discovery environment. CUPS and cups-browsed were also active.

Because Avahi was listening on all IPv4 and IPv6 interfaces, it was selected for remediation in this lab.

## Remediation

Avahi was stopped and disabled using:

sudo systemctl disable --now avahi-daemon

The Avahi socket was also stopped and disabled.

After the change, the Ubuntu listening-services check no longer showed an Avahi listener on UDP port 5353.

## Verification

A final Nmap scan was performed from Kali against UDP port 5353.

Before remediation:

5353/udp open|filtered zeroconf

After remediation:

5353/udp closed zeroconf

This provided before-and-after evidence that the UDP 5353 listener was no longer available after the Avahi service was stopped.

## Findings

The investigation identified Avahi as a network-listening service on UDP 5353.

The service was running and listening on all IPv4 and IPv6 interfaces.

The service was disabled as part of the controlled lab exercise, and the result was verified with a second Nmap scan.

## Lessons Learned

- Nmap can identify potentially exposed ports and services.
- A port reported as open|filtered does not always prove that a service is reachable.
- Checking the target system with ss helps identify services actually listening.
- Services should be investigated before disabling them.
- Changes should be verified with a follow-up scan.
- Before-and-after evidence makes a security assessment easier to document.