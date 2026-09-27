# Atomic Red Team in This Lab

## Role

Atomic Red Team is the controlled activity-generation layer of this project.

It is not the investigation itself.

The intended flow is:

```text
Select atomic test
   ↓
Inspect prerequisites / behavior
   ↓
Predict expected telemetry
   ↓
Execute in isolated Windows VM
   ↓
Verify telemetry arrived in Splunk
   ↓
Generate or validate alert
   ↓
Investigate without relying on the simulation's ground truth
   ↓
Review ground truth after disposition
   ↓
Document detection/visibility gaps
```

## Selection criteria

An atomic test is eligible for this project when it:

- Runs safely in the isolated lab
- Produces useful telemetry
- Supports a clear SOC investigation question
- Has understandable prerequisites and cleanup
- Does not pull the project into identity, deep EDR, or lateral-movement scope unnecessarily

## Ground-truth separation

Simulation details that could bias the analyst should not appear in the initial case packet.

The simulator/operator record is separate from the analyst case record.

## Safety

Only execute tests on the isolated lab endpoint. Review the Atomic Red Team test definition, prerequisites, attack behavior, and cleanup steps before execution.

## Case record

Each simulation should eventually record:

- ATT&CK technique
- Atomic test identifier
- Test name
- Date/time actually executed
- Host actually used
- Operator notes
- Prerequisite status
- Cleanup status
- Expected telemetry
- Observed telemetry
- Visibility gaps

The date/time and host values must be captured from the actual lab run.
