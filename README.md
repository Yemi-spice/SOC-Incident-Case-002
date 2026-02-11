# SOC Incident Case 002 — Brute Force & Privilege Abuse (Elastic SIEM)

## Scenario Overview
This project simulates a real-world SOC investigation involving brute-force authentication attempts followed by insider-style privilege abuse on a Windows endpoint.

An attacker generates multiple failed logon attempts, eventually authenticates successfully, escalates privileges by modifying group memberships, performs privileged actions, and later attempts cleanup by removing accounts and privileges.

All activity is detected, triaged, and investigated using Elastic Security (SIEM) with Windows Security logs and Sysmon telemetry.

---

## Incident Stages

### Stage 1 — Brute Force Authentication
- Repeated failed logon attempts observed
- Successful logon after multiple failures

**Key Event IDs**
- 4625 — Failed logon
- 4624 — Successful logon

---

### Stage 2 — Privilege Escalation / Insider Abuse
- User added to privileged groups
- Special privileges assigned to the session
- Privileged operations executed

**Key Event IDs**
- 4732 — User added to local Administrators group
- 4672 — Special privileges assigned to logon
- 4673 — Privileged service called

---

### Stage 3 — Cleanup / Defense Evasion
- Privileged access removed
- User accounts deleted

**Key Event IDs**
- 4733 — User removed from privileged group
- 4726 — User account deleted

---

## Lab Environment
- Windows 10 (Victim / Telemetry)
- Elastic Stack (Elasticsearch + Kibana)
- Sysmon + Windows Security logs
- Controlled attack simulation

---

## Objectives
- Generate realistic Windows security telemetry
- Build SOC-relevant detection rules
- Perform alert triage and timeline reconstruction
- Produce investigation-ready documentation and reporting

---

## Status
🟡 In progress — telemetry generation and detection engineering

