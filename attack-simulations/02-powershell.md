# Scenario 2 — PowerShell process investigation

**Goal:** Learn how to investigate PowerShell process telemetry without running harmful commands.

- Telemetry: Sysmon Event ID 1 (Process Create), if Sysmon is installed and collected.
- Windows process creation auditing may also produce Security Event ID 4688 when configured.
- ATT&CK hypothesis: T1059.001 (PowerShell), based on observed use and context.

## Safe lab procedure
1. Open a normal PowerShell session on your own Windows endpoint.
2. Run a benign command such as `Get-Date` or `Get-Process`.
3. Locate the corresponding process event in Sysmon Operational logs.
4. Review image, command line, parent process, user and timestamp.
5. Confirm whether Wazuh receives the event.
6. Document what the event does and does not prove.

Do not use encoded payloads, download cradles, credential-dumping commands, or destructive scripts for this exercise.
