# Atomic Red Team Execution Area

This directory documents how Atomic Red Team is used to generate controlled telemetry for the SOC cases.

## Operating rule

Use individual tests, not the entire Atomic Red Team catalog.

Before execution:

- Read the current test definition.
- Check prerequisites.
- Understand what the test changes or executes.
- Confirm required telemetry is active.
- Record the expected artifacts.
- Execute only on the isolated Windows VM.
- Perform cleanup after validation.

The current Atomic Red Team documentation recommends using a test machine with the security/collection solution active and reviewing prerequisites and cleanup for each selected test. citeturn936494search1turn936494search0

## Planned first case

**CASE-001 — Suspicious PowerShell Execution**

Initial candidate:

- ATT&CK: T1059.001 — Command and Scripting Interpreter: PowerShell
- Atomic Red Team: PowerShell-based Windows test selected after telemetry validation

The exact atomic test ID and execution record will be written here only after we validate it on the actual endpoint.

## Execution record

For each run capture:

- Run date/time
- Endpoint hostname
- Atomic test
- Prerequisites
- Start/end time
- Cleanup result
- Expected telemetry
- Observed telemetry
- Detection result
