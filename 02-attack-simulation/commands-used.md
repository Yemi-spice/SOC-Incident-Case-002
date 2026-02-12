## Account Creation (Preparation Phase)

Created local users to simulate insider misuse and privilege escalation.

Commands:
- net user jdoe Password123! /add
- net user svc_backup Backup123! /add
- net user tempadmin TempAdmin123! /add
- net user attacker_sim Temp123! /add
- net localgroup administrators tempadmin /add

Expected Events:
- 4720 (User created)
- 4732 (Added to Administrators group)
