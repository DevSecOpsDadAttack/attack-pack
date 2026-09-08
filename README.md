# KQL-Queries

Hi, I'm Ian Hanley. This is my running library of deceptively simple KQL queries — the ones I keep coming back to whenever a complicated problem shows up in Microsoft Sentinel, Defender XDR, or Log Analytics. Each folder has its own README with a one-line description of every query inside.

Long-form write-ups on many of these live at [hanley.cloud](https://hanley.cloud) / DevSecOpsDad.com.

## Index

| Folder | What's in it |
| --- | --- |
| [`cost-and-ingest/`](./cost-and-ingest/) | Ingest volume, billable trends, and cost breakdowns by table, event ID, and source — the FinOps side of Sentinel. |
| [`analytics-rules/`](./analytics-rules/) | Queries packaged (or ready to be packaged) as Sentinel Analytics Rules. |
| [`hunting/`](./hunting/) | Ad-hoc investigative queries — "what's this user doing", "which device threw this Event ID", etc. |
| [`identity/`](./identity/) | Entra ID / AD / PIM activity — role activations, user deletions, Teams removals. |
| [`email-and-phishing/`](./email-and-phishing/) | Defender for Office 365 / EmailEvents queries — phishing, malware, external-account abuse. |
| [`posture/`](./posture/) | Attack-surface and asset-posture queries — internet-facing devices, EOL software. |
| [`mitre-attack/`](./mitre-attack/) | ATT&CK-mapped tactics and techniques observed in the environment. |
| [`health-checks/`](./health-checks/) | Meta-queries about the workspace itself — rule health, alert volume. |
| [`reference/`](./reference/) | Teaching examples that illustrate a KQL concept rather than solving a specific problem. |
| [`reporting/`](./reporting/) | Periodic-summary queries for stakeholder reporting — weekly, monthly, or quarterly. |
| [`pihole/`](./pihole/) | Pi-hole DNS analytics ingested into a Log Analytics workspace. |

## Naming conventions

- File names use `kebab-case.kql`.
- Folder READMEs list every query with a one-line description.
- Queries authored by me start with an `// Author:` header block.
