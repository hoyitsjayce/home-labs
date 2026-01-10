# Incident Report - Failed SSH Login Attempts

**Date: 08 January 2026

**Severity:** Medium

**Status:** Closed



## Summary

The Wazuh SIEM flagged several failed SSH attempts against a Linux endpoint in a short time period. The individual authentication failures were logged, showing a higher severity alert, including a possible brute force attempt. The investigation found no successful authentication and no system compromise. The incident was closed with suggestions to strengthen SSH access to lower future risk.



## Detection

**Source Tool:** Wazuh SIEM

**Primary Rule ID:** 5760 sshd: authentication failed

**Correlation Rule ID:** 2502 User missed the password more than once

**Log Source:** /var/log/auth.log



## Timeline

23:18:33 Initial SSH authentication failure detected (Rule 5760)

23:18:35 to 23:18:57 Multiple failed SSH login attempts observed

23:19:01 Correlation threshold met

23:19:03 Brute-force alert triggered (Rule 2502)

23:19:05 SOC Analyst investigation started

23:19:15 Incident classified as an unsuccessful brute force attempt



## Investigation

**Endpoint:** Ubuntu Linux

**Username targeted:** ubuntu

**Source IP:** 10.0.0.12

**Authentication method:** SSH password-based login



## Impact Assessment

**System Impact:** none

**Data Impact:** none



## Remediation

**Immediate Action:** No containment actions required

**Recommended Hardening Measures:**

\- Implement account lockout

\- Restrict SSH access



Evidence Collected

\- Wazuh Alerts (Rules 5760 and 2502)

\- Timeline of failed login events

\- Alert details, including source IP, targeted username, timestamps, and rule escalation



Lessons Learned

\- Monitoring authentication can reveal early signs of brute force activity

\- Strengthening SSH can lessen vulnerability to password-based attacks
