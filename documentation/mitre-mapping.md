# MITRE ATT&CK mapping

| Scenario | Candidate technique | Evidence needed |
|---|---|---|
| Repeated failed logons | T1110 — Brute Force | Repeated authentication failures with meaningful source/account/time pattern |
| PowerShell usage | T1059.001 — PowerShell | Process telemetry, command line and context; PowerShell use alone is not malicious |
| Local account creation | T1136.001 — Create Account: Local Account | Account creation event and authorization context |
| Scheduled task creation | T1053.005 — Scheduled Task | Task creation event, task action, author and reason |

ATT&CK is a knowledge base for describing adversary behavior. A technique mapping is not proof of compromise. Use the current ATT&CK website to verify technique names and IDs.
Reference: https://attack.mitre.org/
