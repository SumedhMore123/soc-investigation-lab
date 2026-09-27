# Lab Readiness Check

Do this before running any Atomic Red Team simulation.

## Goal

Establish that the Windows endpoint produces the telemetry required for CASE-001 and that Splunk is receiving it reliably.

## Checklist

- [ ] Windows VM is isolated from unintended third-party targets.
- [ ] Sysmon service is running.
- [ ] Windows Security logging is functioning.
- [ ] PowerShell logging required by the project is enabled and producing events.
- [ ] Splunk Universal Forwarder is running.
- [ ] Forwarder can reach Splunk Enterprise on TCP/9997.
- [ ] Splunk is receiving recent endpoint events.
- [ ] Process-creation telemetry is searchable.
- [ ] The hostname and user can be identified from telemetry.
- [ ] A known benign PowerShell execution can be located in Splunk.

## Evidence to capture

Record actual output rather than paraphrasing:

- Endpoint hostname
- Logged-in test user
- Sysmon version
- PowerShell version
- Universal Forwarder version/status
- Splunk index used for Windows telemetry
- One recent process-creation event
- One recent PowerShell event

Do not run the CASE-001 simulation until this checklist is complete.

## Acceptance criterion

We must be able to answer:

> Can we reliably observe a PowerShell process, its user/host context, and its command line in Splunk?

If not, the project has a visibility problem that must be fixed before attack simulation.