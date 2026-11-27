# Wazuh all-in-one server — Ubuntu Server VM

## Planned environment
- Host: Windows 11 with VMware Workstation
- Guest: Ubuntu Server 24.04 LTS (64-bit)
- VM allocation: 4 vCPU, 8 GB RAM, 50 GB disk
- Network: NAT for initial installation; configure connectivity deliberately before connecting endpoints.

## Installation
Follow the current official guide rather than relying on copied commands that may become outdated:
https://documentation.wazuh.com/current/quickstart.html

The official quickstart uses the Wazuh installation assistant for an all-in-one deployment. Record the Wazuh version installed and save the generated dashboard credentials securely.

## Verification checklist
- [ ] Ubuntu updates complete
- [ ] Wazuh indexer service healthy
- [ ] Wazuh manager service healthy
- [ ] Wazuh dashboard service healthy
- [ ] Dashboard reachable from Windows host
- [ ] Credentials stored securely (never commit them)

Useful checks (run inside Ubuntu):
```bash
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-dashboard
hostname -I
```

Do not commit passwords, private keys, tokens, or unredacted sensitive logs.
