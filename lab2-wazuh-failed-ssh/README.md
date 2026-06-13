# Lab 2: Failed SSH Login Detection (Wazuh SIEM)

**Date:** January 8, 2026
**Environment:** Ubuntu Linux and Wazuh Manager via VMWare

---

## Objective

Detect and document failed SSH authentication attempts using Wazuh SIEM to identify potential brute force behavior on a Linux endpoint.

---

## Lab Environment

| Machine | Role | OS |
|---|---|---|
| Wazuh Manager | SIEM / Alert Engine | Ubuntu Linux |
| Target Endpoint | SSH target being monitored | Ubuntu Linux |
| Attacker | Simulated brute force source (10.0.0.12) | Kali Linux |

---

## Detection

| Field | Detail |
|---|---|
| Source Tool | Wazuh SIEM |
| Log Source | `/var/log/auth.log` |
| Primary Rule | `5760` — sshd: authentication failed |
| Correlation Rule | `2502` — User missed the password more than once |
| Targeted Username | `ubuntu` |
| Source IP | `10.0.0.12` |
| Auth Method | SSH password-based login |

---

## Timeline

| Time | Event |
|---|---|
| 23:18:33 | Initial SSH authentication failure detected (Rule 5760) |
| 23:18:35 – 23:18:57 | Multiple failed SSH login attempts observed |
| 23:19:01 | Correlation threshold met |
| 23:19:03 | Brute force alert triggered (Rule 2502) |
| 23:19:05 | SOC Analyst investigation started |
| 23:19:15 | Incident classified as unsuccessful brute force attempt |

---

## Incident Report

**Severity:** Medium
**Status:** Closed

### Summary

Wazuh SIEM flagged several failed SSH attempts against a Linux endpoint in a short time period. Individual authentication failures were logged, escalating to a higher severity brute force alert. The investigation found no successful authentication and no system compromise.

### Impact Assessment

- **System Impact:** None
- **Data Impact:** None

### Remediation

- Implement account lockout policy
- Restrict SSH access (disable password auth, use key-based only)

### Evidence Collected

- Wazuh alerts for Rules 5760 and 2502
- Timeline of failed login events
- Alert details including source IP, targeted username, timestamps, and rule escalation

---

## Key Takeaways

- Monitoring authentication logs can reveal early signs of brute force activity before a successful compromise occurs
- Wazuh's correlation rules (Rule 2502) effectively escalate individual failures into actionable brute force
