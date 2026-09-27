# Lab

This directory contains the reproducible lab configuration and simulation workflow.

## Environment

- Windows 11 endpoint VM
- Ubuntu Desktop VM with Splunk Enterprise
- Splunk Universal Forwarder on Windows
- Sysmon on Windows
- PowerShell telemetry
- Atomic Red Team / Invoke-AtomicRedTeam on the Windows endpoint

## Build principle

Do not reinstall working components without a concrete technical reason.

Before any case simulation:

1. Confirm the endpoint is isolated.
2. Confirm Sysmon and required Windows telemetry are functioning.
3. Confirm the Universal Forwarder is running.
4. Confirm Splunk is receiving recent endpoint events.
5. Confirm the selected atomic test and cleanup behavior.
6. Take a VM snapshot when practical.

## Case execution

The operator generates the activity first. The analyst then works from the alert/case packet and collected telemetry.

Simulation and analyst documentation should remain separate.
