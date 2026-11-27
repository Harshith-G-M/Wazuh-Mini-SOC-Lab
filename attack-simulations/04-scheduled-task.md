# Scenario 4 — Scheduled task creation

**Goal:** Investigate a new scheduled task and distinguish expected administration from suspicious persistence.

- Event of interest: Windows Security Event ID 4698, if the relevant audit policy is enabled.
- ATT&CK hypothesis: T1053.005 (Scheduled Task/Job: Scheduled Task).

## Safe lab procedure
1. Use Task Scheduler on your own Windows lab machine.
2. Create a harmless task that launches Notepad at a chosen time or on demand.
3. Review the task name, author, trigger and action.
4. Locate Event ID 4698 in Security logs and verify Wazuh collection.
5. Delete the test task after recording evidence.

Do not create hidden tasks or tasks that execute downloaded scripts.
