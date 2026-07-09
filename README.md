# Home Lab Portfolio

Hands-on cybersecurity and information technology labs utilizing VMWare and VirtualBox with Kali Linux, Ubuntu, Metasploitable, Wazuh, and Splunk documenting offensive and defensive cybersecurity techniques.

---

## Table of Contents

- [Lab 1: Nmap Observation on Metasploitable](lab1-nmap/README.md)
- [Lab 2: Failed SSH Login Detection (Wazuh SIEM)](lab2-wazuh-failed-ssh/README.md)
- [Lab 3: Active Directory & Splunk Homelab](lab3-ad-splunk-lab/README.md)
- [Disclaimer](#disclaimer)

---

## Lab 1: Nmap Observation on Metasploitable

- Performed network scanning against a deliberately vulnerable Metasploitable VM
- Identified open ports, running services, and operating system fingerprints
- Practiced interpreting scan results and documenting findings

## Lab 2: Failed SSH Login Detection (Wazuh SIEM)

- Simulated brute force SSH authentication attempts against an Ubuntu endpoint
- Detected and alerted on failed login activity using Wazuh SIEM
- Documented how monitoring authentication logs reveals early signs of brute force behavior

## Lab 3: Active Directory & Splunk Homelab

- Built a small enterprise environment with Active Directory (ADDC01), a target endpoint (demo), Splunk SIEM, and Kali Linux attacker
- Configured Splunk Universal Forwarder and Sysmon for endpoint telemetry
- Simulated brute force attacks using Crowbar/Hydra and detected them via Splunk SPL queries

---

## Disclaimer

All exercises are performed in isolated lab environments using virtual machines. No unauthorized systems or networks were accessed. This repository is for educational purposes only.
