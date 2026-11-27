# Windows 11 endpoint agent

Follow the official Windows agent installation instructions:
https://documentation.wazuh.com/current/installation-guide/wazuh-agent/wazuh-agent-package-windows.html

High-level sequence:
1. Download the Wazuh agent package from the official Wazuh repository.
2. During installation, configure the Wazuh manager address to the Ubuntu VM's reachable IP.
3. Start the Wazuh agent service.
4. Confirm the endpoint appears as active in the Wazuh dashboard.
5. Verify that the Windows agent is collecting the intended event channels.

Do not guess the server address or assume the VM network is reachable. Confirm connectivity and the required Wazuh agent ports from current official documentation.

## Windows telemetry to configure
- Windows Security Event Log (especially logon and account-management events).
- PowerShell operational logging, where appropriate.
- Sysmon for richer process and network telemetry (optional but recommended for this lab).

Reference: https://learn.microsoft.com/sysinternals/downloads/sysmon
