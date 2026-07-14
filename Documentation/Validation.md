# Validation Runbook

## Objective

The following validation scenarios were executed to confirm that all
endpoints were correctly sending telemetry to the Wazuh platform.

------------------------------------------------------------------------

# Environment Validation

  Validation                   Status
  ---------------------------- --------
  Wazuh Server Operational     âœ…
  Windows Agent Connected      âœ…
  Linux Agent Connected        âœ…
  Windows 11 Agent Connected   âœ…

------------------------------------------------------------------------

# Windows Security Events

## Successful Logon

**Windows Event ID:** 4624

**Result:** Successfully detected and indexed.

------------------------------------------------------------------------

## Failed Logon

**Windows Event ID:** 4625

**Result:** Successfully detected and indexed.

------------------------------------------------------------------------

## User Account Creation

**Windows Event ID:** 4720

**Result:** Successfully detected and indexed.

------------------------------------------------------------------------

## Group Membership Change

**Windows Event ID:** 4728

**Result:** Successfully detected and indexed.

------------------------------------------------------------------------

## Sysmon Process Creation

**Sysmon Event ID:** 1

**Result:** Successfully detected and indexed.

------------------------------------------------------------------------

# Linux Validation

## auditd Command Execution

Validated commands:

-   ls
-   sudo whoami
-   whoami

Result:

Successfully collected by auditd and forwarded to Wazuh.

------------------------------------------------------------------------

# Dashboard Validation

The following dashboards and searches were verified.

-   Connected Agents
-   Windows Security Events
-   Sysmon Events
-   Linux auditd Events
-   Security Event Timeline

------------------------------------------------------------------------

# MITRE ATT&CK Context

The validated events are telemetry sources that can support
investigations and detection logic associated with the following
techniques. A single event does not independently confirm that a
technique occurred.

  -----------------------------------------------------------------------
  Telemetry        Relevant Investigation Context
  ---------------- ------------------------------------------------------
  Successful Logon T1078 - Valid Accounts
  (4624)

  Failed Logon     T1110 - Brute Force
  (4625)

  User Creation    T1136 - Create Account
  (4720)

  Group Membership T1098 - Account Manipulation
  Change (4728)

  Sysmon Process   T1059 - Command and Scripting Interpreter
  Creation (Event
  ID 1)
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# Validation Summary

  Component                         Status
  --------------------------------- --------
  Windows Security Logs             âœ…
  Sysmon                            âœ…
  Linux auditd                      âœ…
  Wazuh Agents                      âœ…
  Wazuh Dashboard                   âœ…
  Cross-platform Event Visibility   âœ…
  MITRE ATT&CK Contextualization    âœ…

------------------------------------------------------------------------

# Conclusion

All documented telemetry validation scenarios completed successfully.

The SIEM platform correctly collected, parsed, indexed, and displayed
security events generated from both Windows and Linux endpoints.
