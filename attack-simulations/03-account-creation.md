# Scenario 3 — Local account creation

**Goal:** Detect and validate a local account-management change.

- Event of interest: Windows Security Event ID 4720 (user account created).
- Related events may include 4722 (account enabled) and 4732 (member added to a local security-enabled group).
- ATT&CK hypothesis: T1136.001 (Create Account: Local Account).

## Safe lab procedure
1. On your own lab endpoint, create a clearly named disposable standard local test account using Windows Settings.
2. Confirm Event ID 4720 in Security logs.
3. Review the subject account, new account name, timestamp and host.
4. Check whether Wazuh collected the event.
5. Remove the disposable test account after evidence collection, if no longer needed.

Do not create an administrator account for the test unless there is a specific, authorized reason.
