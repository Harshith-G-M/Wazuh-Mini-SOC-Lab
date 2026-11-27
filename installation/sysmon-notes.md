# Sysmon setup notes (Windows)

Sysmon is an optional Microsoft Sysinternals utility that records detailed system activity to the Windows Event Log. It is not a SIEM and does not independently classify activity as malicious.

1. Download Sysmon only from Microsoft's official Sysinternals page:
   https://learn.microsoft.com/sysinternals/downloads/sysmon
2. Review the official documentation and choose a configuration suitable for a small lab.
3. Install it on the Windows endpoint using an administrator terminal, following Microsoft's current instructions.
4. Confirm events appear in `Microsoft-Windows-Sysmon/Operational`.
5. Configure the Wazuh agent to collect the Sysmon operational channel using the current Wazuh documentation.
6. Validate event collection in the Wazuh dashboard before creating detections.

Avoid copying unknown Sysmon configuration files without reviewing what they collect.
