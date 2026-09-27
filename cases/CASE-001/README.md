# CASE-001 — Suspicious PowerShell Execution

**Status:** Preparation

## Investigation objective

Investigate a SOC alert involving suspicious PowerShell execution and determine what actually happened using endpoint telemetry.

## Analyst challenge

The initial case packet must not reveal the simulation's final behavior.

The analyst should determine:

- Which process executed?
- Which user initiated it?
- What was the command line?
- What was the parent process?
- What happened immediately before and after execution?
- Did the activity create additional endpoint artifacts?
- Is there relevant network activity?
- Which evidence supports or weakens the suspicious-activity hypothesis?
- What does the evidence prove?
- What does it not prove?
- What is the appropriate disposition?

## Primary telemetry

- Sysmon process creation
- PowerShell telemetry
- Windows event logs

## Supporting telemetry

Use network evidence only if the collected activity creates a meaningful network question.

## Simulation

Atomic Red Team will be used only as the controlled activity generator. The exact test selection will be finalized after validating the Windows telemetry pipeline.

## Completion condition

The case is not complete when the Atomic test runs.

It is complete only when:

1. The generated activity is visible in Splunk.
2. A defensible alert is produced.
3. The analyst investigates from the alert.
4. A timeline is reconstructed from telemetry.
5. The disposition is justified by evidence.
6. Limitations are documented.
7. The analyst can explain the case without reading the report.
