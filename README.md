# SOC Investigation & Incident Triage Lab

> An evidence-driven Security Operations Center (SOC) lab focused on alert triage, endpoint investigation, telemetry correlation, IOC pivoting, evidence assessment, and documented incident disposition.

## Project Objective

This project simulates the workflow of an L1 SOC analyst receiving security alerts and determining what happened, what the available evidence supports, what remains uncertain, and what action should follow.

The project is intentionally **case-driven rather than tool-driven**. Splunk, Sysmon, Windows Event Logs, and supporting network telemetry are evidence sources; the primary objective is to demonstrate sound investigation and analytical reasoning.

## Core Investigation Workflow

```text
Alert
  ↓
Initial Triage
  ↓
Investigation Hypothesis
  ↓
Investigation Plan
  ↓
Endpoint / Network Evidence
  ↓
Correlation & IOC Pivoting
  ↓
Timeline Reconstruction
  ↓
Evidence Assessment
  ↓
Disposition
  ├── True Positive → Escalate
  ├── False Positive / Benign → Close
  └── Inconclusive → Document Gaps / Recommend Further Investigation
  ↓
Incident Report
```

## Lab Architecture

```text
Windows 11 VM
├── Sysmon
├── Windows Event Logs
└── PowerShell Telemetry
        │
        ▼
Splunk Universal Forwarder
        │ TCP 9997
        ▼
Ubuntu VM
└── Splunk Enterprise
        │
        ▼
SOC Investigation
```

Supporting network telemetry such as Zeek or Wireshark is introduced only when it materially improves a case.

## Planned Case Portfolio

| Case | Investigation Focus | Primary Learning |
|---|---|---|
| CASE-001 | Suspicious PowerShell Execution | Endpoint triage, process lineage, command-line analysis |
| CASE-002 | Suspicious-Looking but Legitimate Activity | False-positive reasoning and contextual analysis |
| CASE-003 | Process + Network Correlation | Correlating endpoint and network evidence |
| CASE-004 | IOC Investigation & Pivoting | Indicator scoping, enrichment, and contextual validation |
| CASE-005 | Insufficient / Missing Evidence | Inconclusive disposition, limitations, and escalation |

The final verdict for each case must be supported by collected telemetry rather than a predetermined attack narrative.

## Evidence Discipline

Each investigation distinguishes:

- **Observation** — what the telemetry directly shows
- **Interpretation** — what the observation may indicate
- **Hypothesis** — what we currently suspect
- **Validation** — evidence required to test the hypothesis
- **Conclusion** — what the available evidence supports

The project explicitly avoids fabricating telemetry, timestamps, IOCs, or attacker behavior.

## Scope

The flagship project focuses on SOC L1 investigation fundamentals:

- Alert triage
- Windows and Sysmon telemetry analysis
- Process-tree and command-line investigation
- PowerShell investigation
- Timeline reconstruction
- Endpoint/network correlation where justified
- IOC extraction and pivoting
- Basic threat-intelligence enrichment
- MITRE ATT&CK mapping when supported by evidence
- Evidence-based disposition
- Escalation / closure decisions
- Professional incident documentation

Identity-focused investigations, deep EDR investigation, and lateral-movement scenarios remain outside the core scope unless a narrowly scoped reference is necessary to explain a finding.

## Learning Method

For major investigative steps, the analyst should first:

1. State the investigative objective.
2. Form an initial hypothesis.
3. Identify the telemetry needed.
4. Construct the query or analysis approach.
5. Review the resulting evidence.
6. Explain what the evidence proves and does not prove.
7. Pivot to the next relevant evidence source.
8. Reach and justify a disposition.
9. Document the investigation.

Finished SPL or commands are not the learning objective. Understanding the investigative question and the evidence is.

## Repository Structure

The repository will evolve toward:

```text
soc-investigation-lab/
├── README.md
├── docs/
├── lab/
├── detections/
├── cases/
├── mitre/
├── screenshots/
├── templates/
└── .gitignore
```

Case directories are first-class project artifacts and will contain the alert, investigation evidence, timeline, findings, limitations, disposition, and final report.

## Safety

All simulations are performed in an isolated lab environment under the project's defensive-investigation purpose. No activity should target real systems or third-party infrastructure.

## Flagship-Ready Standard

The project is considered complete only when the implementation demonstrates working telemetry, multiple evidence-driven investigations, documented true-positive/false-positive/inconclusive outcomes, professional case reports, and the ability of the analyst to explain the investigation decisions without relying on memorized documentation.
