# Asset & Account Inventory — Case 002

## Host
- Hostname: DESKTOP-MSCRJC2
- OS: Windows 10
- Role: Endpoint under investigation

---

## User Accounts

### jdoe
- Type: Standard local user
- Purpose: Target of brute-force authentication attempts
- Expected Events:
  - 4625 (failed logon)
  - 4624 (successful logon)

---

### svc_backup
- Type: Service-style account
- Purpose: Used to simulate credential misuse
- Expected Events:
  - 4625 (failed logon)
  - 4672 (special privileges assigned)

---

### tempadmin
- Type: Local user
- Purpose: Added to Administrators group during attack
- Expected Events:
  - 4732 (added to admin group)
  - 4672 (privileged session)

---

### attacker_sim
- Type: Local user
- Purpose: Account created and later deleted for cleanup
- Expected Events:
  - 4720 (user created)
  - 4726 (user deleted)

---

## Baseline User
- Account: Local-cafe
- Purpose: Legitimate user for normal activity comparison
