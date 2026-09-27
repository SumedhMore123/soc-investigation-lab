# Project Architecture

## Purpose

This repository is an evidence-driven SOC L1 investigation lab. The primary artifact is the investigation case, not the simulation script or SPL library.

## Logical flow

```text
Atomic Red Team simulation
        ↓
Windows 11 endpoint
        ↓
Sysmon + Windows Event Logs + PowerShell telemetry
        ↓
Splunk Universal Forwarder
        ↓
Splunk Enterprise
        ↓
Detection / Alert
        ↓
L1 Investigation
        ↓
Correlation + Timeline + Enrichment
        ↓
Evidence Assessment
        ↓
Disposition
        ↓
Escalation / Closure
        ↓
Incident Report
```

## Design principles

1. Simulations generate controlled telemetry; they do not determine the analyst's conclusion.
2. Cases are investigated from the alert perspective before the ground truth is reviewed.
3. Every conclusion must be traceable to evidence.
4. Supporting telemetry is added only when it materially improves an investigation.
5. Identity attacks, deep EDR investigations, and lateral-movement scenarios remain outside the flagship scope.

## Infrastructure

### Endpoint

- Windows 11 VM
- VMware Workstation Pro
- Sysmon
- Windows Event Logs
- PowerShell telemetry
- Atomic Red Team / Invoke-AtomicRedTeam for controlled simulation

### SIEM

- Ubuntu Desktop VM
- Splunk Enterprise
- Splunk Universal Forwarder
- Receiving port: TCP/9997

### Supporting network telemetry

- Zeek and/or Wireshark only for cases where network evidence is necessary.
