\# Lab 2 – Failed SSH Login Detection (Wazuh SIEM)



\## Objective

Detect and investigate failed SSH authentication attempts using Wazuh SIEM to identify potential brute-force behavior.



\## Tools Used

\- Wazuh SIEM

\- Ubuntu Linux

\- SSH



\## Detection Logic

\- Rule 5760: SSH authentication failed

\- Rule 2502: Correlated multiple failed authentication attempts



\## Investigation Summary

Multiple failed SSH login attempts were detected against a Linux endpoint and escalated via correlation rules. Analysis confirmed no successful authentication or system compromise.



\## Evidence

Screenshots and alert metadata are provided in the `/screenshots` directory.



\## Outcome

The incident was documented and closed with recommendations to harden SSH access.



