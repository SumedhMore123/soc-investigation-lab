# Investigation Methodology

## Purpose

This document defines the investigation model used throughout the lab.

The analyst follows evidence from an alert to a defensible disposition. The workflow is not intended to force a particular attack narrative.

## Investigation Lifecycle

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

## Evidence Discipline

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

## Core Analyst Questions

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

Use when available evidence supports malicious or policy-violating activity relevant to the alert.

### False Positive / Benign

Use when the alert condition occurred but investigation establishes a legitimate explanation or otherwise shows that the security concern is not present.

### Inconclusive

Use when available evidence cannot support a sufficiently confident determination.

An inconclusive result is valid when evidence is incomplete. Document the missing evidence and recommended next actions.

## Timeline Rules

Case timelines must be derived from actual telemetry.

Do not invent timestamps to make an attack narrative coherent.

When timestamps from different sources are used, record the source and account for any known timestamp normalization or timezone differences.

## Querying Rules

SPL should answer a specific investigative question.

Before writing a query, identify:

1. The question.
2. The required evidence.
3. The event source.
4. The relevant fields.
5. The expected relationship or condition.

A complicated query is not inherently better than a simple query.

## Scope Rules

The flagship lab focuses on L1 SOC investigation. Identity attack investigation, deep EDR investigation, and lateral-movement analysis are separate project areas and should not become core dependencies here.

## Learning Gate

After each major case, the analyst should be able to explain the investigation without reading the final report. If the reasoning cannot be explained, the case is not considered complete.
