# Case Design

## Purpose

Cases are designed to teach investigation rather than isolated attack techniques.

Each case must have:

- A realistic alerting condition.
- A meaningful investigative question.
- Enough telemetry to support investigation.
- At least one useful pivot.
- A defensible outcome.
- A clear learning objective.
- A validation method for the analyst's conclusion.

## Planned Portfolio

### CASE-001 — Suspicious PowerShell Execution

**Focus:** Endpoint triage, process lineage, command-line analysis, PowerShell telemetry.

**Core question:** What actually happened when the alert fired, and is the execution malicious?

**Primary evidence:** Sysmon process telemetry, PowerShell logs, Windows events.

### CASE-002 — Suspicious-Looking but Legitimate Activity

**Focus:** False-positive reasoning and contextual analysis.

**Core question:** Does suspicious-looking execution have a legitimate explanation?

**Primary evidence:** Endpoint process and PowerShell telemetry plus contextual events.

### CASE-003 — Process + Network Correlation

**Focus:** Correlating process execution with network activity.

**Core question:** Which process initiated the observed network activity, and what does the relationship establish?

**Primary evidence:** Sysmon process/network telemetry with Zeek or Wireshark when justified.

### CASE-004 — IOC Investigation and Pivoting

**Focus:** Scoping an indicator across available telemetry and adding contextual enrichment.

**Core question:** Where, when, and in what context did the indicator appear?

**Primary evidence:** Endpoint/network telemetry plus appropriate enrichment.

### CASE-005 — Insufficient Evidence

**Focus:** Evidence gaps, uncertainty, and escalation.

**Core question:** Can the available evidence support a confident disposition?

**Primary evidence:** Available endpoint telemetry with deliberately identified evidence limitations.

## Case Integrity

The analyst-facing case must not reveal its expected verdict.

Simulation ground truth and validation material should be separated from analyst-facing documentation and kept out of public case materials when disclosure would undermine the exercise.

## No Fabricated Evidence

If telemetry does not support a finding, the finding must not appear in the final case report.

Timestamps, IOCs, process relationships, network activity, and attacker behavior must come from observed lab telemetry.
