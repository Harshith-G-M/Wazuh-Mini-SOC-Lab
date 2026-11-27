# Mini SOC Lab — Wazuh SIEM (Starter Project)

> **Status: In progress — documentation and detection-rule starter pack.**
> The Wazuh server and endpoint agents have not yet been deployed or validated. Add screenshots and test evidence only after reproducing the lab.

## Objective
Design a small, reproducible Security Operations Center (SOC) home lab using Wazuh to collect endpoint telemetry, investigate security alerts, map activity to MITRE ATT&CK, and document incident-handling decisions.

## Planned architecture
- **Wazuh all-in-one server:** Ubuntu Server VM running Wazuh Manager, Indexer and Dashboard.
- **Windows 11 endpoint:** Wazuh agent, Windows Security Event Logs and (planned) Sysmon telemetry.
- **Optional Linux endpoint:** Wazuh agent monitoring authentication logs and file integrity.

For a one-endpoint starter lab, run only the Ubuntu server VM and use the Windows host as the monitored endpoint. Avoid running multiple VMs simultaneously on a 16 GB laptop.

## Repository contents
| Path | Purpose |
|---|---|
| `architecture/` | Architecture and workflow diagrams |
| `installation/` | Server and endpoint setup notes |
| `detection-rules/local_rules.xml` | Example custom Wazuh rules (validate before use) |
| `attack-simulations/` | Safe, controlled test procedures |
| `incident-reports/` | Investigation report template and examples marked as templates |
| `documentation/` | MITRE ATT&CK mapping and L1 triage workflow |
| `evidence/` | Placeholder for your own screenshots and exported evidence |

## Planned detection scenarios
1. Repeated Windows logon failures — Windows Event ID 4625; ATT&CK T1110 (Brute Force), where context supports it.
2. Suspicious PowerShell execution — Sysmon Event ID 1 / process creation telemetry; ATT&CK T1059.001.
3. Local account creation — Windows Event ID 4720; ATT&CK T1136.001.
4. Scheduled task creation — Windows Event ID 4698; ATT&CK T1053.005.
5. File integrity change — Wazuh FIM alert; map to an ATT&CK technique only when the observed behavior and intent justify it.

**Important:** An event is not automatically an incident. Validate the account, host, timestamp, source, process, surrounding events and business context before escalating. ATT&CK mappings are hypotheses to support investigation, not proof of malicious activity.

## Safety
- Run simulations only on systems you own or are explicitly authorized to test.
- Use a disposable local test account and benign commands.
- Do not run malware, credential theft, destructive payloads, or attacks against public systems.
- Do not enable automatic blocking/Active Response until you understand the impact and have authorization.
- Wazuh is primarily an endpoint security monitoring platform. It does not automatically provide full network intrusion detection; network scan detection may require a network sensor such as Suricata.

## Current validation status
- [ ] Ubuntu Wazuh server installed
- [ ] Wazuh dashboard login verified
- [ ] Windows agent connected and reporting
- [ ] Sysmon installed and events visible
- [ ] Custom rules loaded without errors
- [ ] Each scenario safely simulated
- [ ] Alerts reviewed and false positives considered
- [ ] Incident reports completed with screenshots

## Evidence to add later
Place genuine screenshots in `evidence/`:
- Wazuh dashboard overview
- Agents showing active status
- Security events / alerts for each scenario
- Rule details and event fields
- Investigation timeline and completed incident reports

Do not use screenshots from another person's lab as proof of your own implementation.

## References
- Wazuh documentation: https://documentation.wazuh.com/current/
- Wazuh quickstart: https://documentation.wazuh.com/current/quickstart.html
- Wazuh Windows agent: https://documentation.wazuh.com/current/installation-guide/wazuh-agent/wazuh-agent-package-windows.html
- MITRE ATT&CK: https://attack.mitre.org/
- Sysmon: https://learn.microsoft.com/sysinternals/downloads/sysmon
- Windows Security auditing events: https://learn.microsoft.com/windows/security/threat-protection/auditing/basic-audit-logon-events

## Disclaimer
This repository is a learning-lab starter pack. The rules are illustrative and may need adjustment for your Wazuh version, decoder output, Windows audit policy and endpoint configuration. Test them in a lab and inspect `wazuh-logtest` output before relying on them.
