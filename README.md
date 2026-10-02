# Enterprise Home SOC Lab

A virtualized enterprise environment built to practice SOC analyst skills: log collection, threat detection, and incident investigation using Active Directory, Sysmon, and Wazuh SIEM.

**Status:** In progress. This README is updated as each stage is completed.

## Goals

- Build a realistic Windows domain environment
- Collect endpoint telemetry (Windows Event Logs + Sysmon) in a central SIEM
- Simulate common attacker behavior from a Kali Linux machine
- Detect, investigate, and document each attack, mapped to MITRE ATT&CK

## Lab Architecture

| Machine | OS | Role |
|---|---|---|
| DC01 | Windows Server | Domain Controller (AD DS, DNS) |
| WIN11-CLIENT | Windows 11 | Domain-joined workstation (Sysmon + Wazuh agent) |
| WAZUH-SERVER | Linux (Ubuntu) | Wazuh SIEM (manager, indexer, dashboard) |
| KALI | Kali Linux | Attacker machine |

All machines run in an isolated virtual network (host-only/internal) with no exposure to the internet or any real systems.

**Tools:** VirtualBox/VMware, Windows Server, Windows 11, Active Directory, Sysmon, Wazuh, Kali Linux, PowerShell

## Progress

- [ ] Virtual network and VMs created
- [ ] Windows Server promoted to Domain Controller
- [ ] AD configured (users, groups, OUs, Group Policies, DNS)
- [ ] Windows 11 joined to the domain
- [ ] Sysmon installed with a config file
- [ ] Wazuh server deployed
- [ ] Wazuh agents installed and forwarding logs
- [ ] Attack simulation 1: network reconnaissance (Nmap)
- [ ] Attack simulation 2: failed logins / brute force
- [ ] Attack simulation 3: suspicious PowerShell activity
- [ ] Investigation write-ups completed
- [ ] Custom Wazuh detection rules written

## Attack Simulations and Detections

| # | Activity | MITRE ATT&CK | Log source / Event ID | Detected in Wazuh? | Write-up |
|---|---|---|---|---|---|
| 1 | Network scan (Nmap) | T1046 | TBD | TBD | TBD |
| 2 | Brute-force login attempts | T1110 | Windows Event ID 4625 | TBD | TBD |
| 3 | Encoded PowerShell command | T1059.001 | Sysmon Event ID 1 / PowerShell logs | TBD | TBD |

## Investigation Write-ups

Each write-up follows this structure:

1. **Summary**: what happened
2. **Detection**: which alert/rule fired and where
3. **Evidence**: screenshots and log excerpts
4. **MITRE ATT&CK mapping**
5. **Remediation / recommendations**

Write-ups will be stored in the `/investigations` folder.

## What I'm Learning

- How Windows authentication and Active Directory generate security logs
- How Sysmon improves endpoint visibility
- How to read SIEM alerts and separate noise from real threats
- How to document findings the way a SOC analyst would

## Disclaimer

All attack simulations are performed only inside my own isolated lab environment for learning purposes.

## Contact

Saideep Vengurlekar | [LinkedIn](https://linkedin.com/in/saideep-vengurlekar)
