# Investigation Methodology

## Purpose

This document defines the investigation model used throughout the lab.

The analyst follows evidence from an alert to a defensible disposition. The workflow is not intended to force a particular attack narrative.

## Investigation lifecycle

1. Alert intake
2. Initial triage
3. Initial hypothesis
4. Investigation plan
5. Evidence collection
6. Correlation and pivots
7. Timeline reconstruction
8. Evidence assessment
9. Disposition
10. Escalation or closure
11. Case documentation

## Evidence discipline

For every significant finding, distinguish:

- **Observation** — directly supported by telemetry.
- **Interpretation** — a reasonable meaning that may be drawn from the observation.
- **Hypothesis** — a proposition that still requires validation.
- **Validation** — additional evidence used to test the hypothesis.
- **Conclusion** — what the collected evidence supports.

### Example

**Observation:** A PowerShell process was created with an encoded command.

**Interpretation:** Encoded PowerShell can be associated with obfuscation.

**Hypothesis:** The execution may be malicious.

**Validation:** Inspect the parent process, decoded command, child processes, user context, and relevant network activity.

**Conclusion:** Determine only what the collected evidence supports.

## Core analyst questions

For every alert, ask:

- What triggered?
- Which host and user are involved?
- When did it occur?
- Which process or event caused it?
- What happened immediately before and after?
- Is there related network activity?
- Are there indicators worth pivoting on?
- Could legitimate activity explain the behavior?
- What does the evidence prove?
- What does it not prove?
- Is the case actionable?
- What should happen next?

## Dispositions

### True Positive

Use when the available evidence supports malicious or policy-violating activity relevant to the alert.

### False Positive / Benign

Use when the alert condition occurred but investigation establishes a legitimate explanation or otherwise shows that the security concern is not present.

### Inconclusive

Use when available evidence cannot support a sufficiently confident determination.

An inconclusive result is valid when evidence is incomplete. Document the missing evidence and recommended next actions.

## Timeline rules

Case timelines must be derived from actual telemetry.

Do not invent timestamps to make an attack narrative coherent.

When timestamps from different sources are correlated, record the source and account for known clock/time-zone differences.

## Query discipline

Before writing SPL, state:

1. The investigative question.
2. The evidence needed to answer it.
3. The data source or event type likely to contain that evidence.
4. The fields needed.
5. The condition that will identify relevant events.

Then write and test the query.

A technically valid query is not necessarily an analytically useful query.

## Coaching gate

After each major pivot, the analyst should explain in their own words:

- Why the pivot was necessary.
- What evidence was found.
- What that evidence proves.
- What it does not prove.
- What question the next pivot is intended to answer.

Do not advance a case simply because the commands or SPL work.
