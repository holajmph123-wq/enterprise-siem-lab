# Validation Runbook

## Objective

The following validation scenarios were executed to confirm that all endpoints were correctly sending telemetry to the Wazuh platform.

---

# Environment Validation

| Validation | Status |
|------------|--------|
| Wazuh Server Operational | ✅ |
| Windows Agent Connected | ✅ |
| Linux Agent Connected | ✅ |
| Windows 11 Agent Connected | ✅ |

---

# Windows Security Events

## Successful Logon

**Windows Event ID:** 4624

**Result:** Successfully detected and indexed.

---

## Failed Logon

**Windows Event ID:** 4625

**Result:** Successfully detected and indexed.

---

## User Account Creation

**Windows Event ID:** 4720

**Result:** Successfully detected and indexed.

---

## Group Membership Change

**Windows Event ID:** 4728

**Result:** Successfully detected and indexed.

---

## Sysmon Process Creation

**Sysmon Event ID:** 1

**Result:** Successfully detected and indexed.

---

# Linux Validation

## auditd Command Execution

Validated commands:

- ls
- sudo whoami
- whoami

Result:

Successfully collected by auditd and forwarded to Wazuh.

---

# Dashboard Validation

The following dashboards and searches were verified.

- Connected Agents
- Windows Security Events
- Sysmon Events
- Linux auditd Events
- Security Event Timeline

---

# MITRE ATT&CK Validation

| Detection | MITRE Technique |
|----------|-----------------|
| Successful Logon | T1078 |
| Failed Logon | T1110 |
| User Creation | T1136 |
| Group Membership | T1098 |
| Sysmon Process Creation | T1059 |

---

# Validation Summary

| Component | Status |
|-----------|--------|
| Windows Security Logs | ✅ |
| Sysmon | ✅ |
| Linux auditd | ✅ |
| Wazuh Agents | ✅ |
| Wazuh Dashboard | ✅ |
| Event Correlation | ✅ |
| MITRE Mapping | ✅ |

---

# Conclusion

All validation scenarios completed successfully.

The SIEM platform correctly collected, parsed, indexed, and displayed security events generated from both Windows and Linux endpoints.