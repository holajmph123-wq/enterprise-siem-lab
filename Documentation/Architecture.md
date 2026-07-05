# Wazuh Enterprise SIEM Lab Architecture

## Overview

This lab simulates a hybrid enterprise environment where Windows and Linux endpoints send security telemetry to a centralized Wazuh SIEM platform.

The objective is to demonstrate endpoint visibility, centralized log collection, security event correlation, and detection validation across multiple operating systems.

---

# Infrastructure

| Host | Operating System | Role |
|------|------------------|------|
| JeanPc | Windows 11 Pro | Physical Host / Management Workstation / Wazuh Agent |
| DC01 | Windows Server 2022 | Active Directory Domain Controller / Sysmon / Wazuh Agent |
| linux-01 | Ubuntu Server 24.04 LTS | Linux Endpoint / auditd / Wazuh Agent |
| wazuh-server | Ubuntu Server 24.04 LTS | Wazuh Manager / Indexer / Dashboard |

---

# Virtualization

The lab is distributed across two virtualization platforms.

## Oracle VirtualBox

- Windows Server 2022
- Active Directory Domain Services
- Sysmon
- Wazuh Agent

## VMware Workstation Pro

- Wazuh Server
- Ubuntu 24.04 LTS
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

- linux-01
- Ubuntu 24.04 LTS
- auditd
- Wazuh Agent

---

# Monitoring Components

## Windows Endpoint

- Windows Security Event Logs
- Sysmon
- PowerShell Logging
- File Integrity Monitoring (FIM)
- Security Configuration Assessment (SCA)

---

## Linux Endpoint

- auditd
- Journald
- File Integrity Monitoring (FIM)
- Security Configuration Assessment (SCA)

---

# Event Flow

Windows Server 2022 (DC01)
        │
        │ Windows Events + Sysmon
        ▼
   Wazuh Agent
        │
        ▼
 Wazuh Manager
        │
        ▼
 Wazuh Indexer
        │
        ▼
Wazuh Dashboard


Ubuntu linux-01
        │
        │ auditd
        ▼
   Wazuh Agent
        │
        ▼
 Wazuh Manager
        │
        ▼
 Wazuh Indexer
        │
        ▼
Wazuh Dashboard

---

# Detection Sources

## Windows

- Security Log
- Sysmon Operational Log
- PowerShell Logs

## Linux

- auditd
- systemd-journald

---

# Security Features

- Centralized Log Collection
- Windows Security Monitoring
- Linux Security Monitoring
- Sysmon Telemetry
- auditd Monitoring
- Active Directory Monitoring
- File Integrity Monitoring
- Security Configuration Assessment
- MITRE ATT&CK Mapping

---

# Lab Diagram

See:

```
Screenshots/05-lab-architecture.png
```

---

# Status

**Completed**