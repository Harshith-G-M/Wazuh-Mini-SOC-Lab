# Scenario 1 — Repeated failed Windows logons

**Goal:** Observe failed authentication events and determine whether repeated failures warrant investigation.

- Event of interest: Windows Security Event ID 4625.
- ATT&CK hypothesis: T1110 (Brute Force), only when pattern and context support it.
- Expected evidence: account name, logon type, source workstation/IP when available, timestamp, status/substatus.

## Safe lab procedure
1. Use a local disposable test account on your own Windows lab machine.
2. Attempt a small, deliberate number of incorrect logons (for example, 5) at the console.
3. Do not target domain accounts, other devices, or remote systems.
4. Open Event Viewer → Windows Logs → Security and locate Event ID 4625.
5. Check whether Wazuh receives the event and whether your threshold rule fires.
6. Record the result, including any missing fields or false positives.

## Analyst questions
- Is the account expected to exist?
- Are failures from one source or multiple sources?
- Is there a subsequent successful logon?
- Is the logon type interactive, network, or RemoteInteractive?
- Does the activity match normal user behavior?

## Cleanup
Stop testing and leave the account in its original state. Do not lock out real users.
