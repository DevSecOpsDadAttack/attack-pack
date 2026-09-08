# hunting

Ad-hoc investigative queries. These aren't packaged as Sentinel Analytics Rules — they're the "let me pull on this thread" queries you reach for during triage, incident response, or when a stakeholder asks a specific question.

## Subfolders

- [`eventid-forensics/`](./eventid-forensics/) — questions organized around a specific Windows Event ID.
- [`file-activity/`](./file-activity/) — DeviceFileEvents-based audit queries.
- [`user-activity/`](./user-activity/) — what a specific user has been doing.
- [`web-tier/`](./web-tier/) — hunts against web session / HTTP telemetry.

## Standalone hunts

Sourced primarily from the **[KQL Detection of the Week](https://devsecopsdadattack.com/kqldetectionoftheweek/)** series — each file's header carries a `// Source:` link to the article that walked through its design.

| Query | Description |
| --- | --- |
| [`hunt-azure-diagnostic-setting-deletions.kql`](./hunt-azure-diagnostic-setting-deletions.kql) | Deletions of Azure diagnostic settings — the moment an attacker turns off logging (T1562.008). Step 1 of a two-step sequence. |
| [`hunt-blockchain-rpc-c2-dead-drop.kql`](./hunt-blockchain-rpc-c2-dead-drop.kql) | C2 traffic hidden inside blockchain-RPC calls to public utilities (QuickNode, Alchemy) — 'the dead drop is a public utility.' |
| [`hunt-c2-beacon-by-connection-window-rhythm.kql`](./hunt-c2-beacon-by-connection-window-rhythm.kql) | Low-and-slow C2 beacon hunt that counts distinct hourly time windows a process was connected in — not raw connection volume. |
| [`hunt-cav3rn-endpoint-local-log-file-artifact.kql`](./hunt-cav3rn-endpoint-local-log-file-artifact.kql) | Endpoint-side hunt for Project CAV3RN's local file artifact (`logAzure.txt` and family) — config persistence written by the module. |
| [`hunt-cloud-metadata-ssrf-normalized-forms.kql`](./hunt-cloud-metadata-ssrf-normalized-forms.kql) | Cloud instance-metadata SSRF across every string-form the attacker can write — dotted, dotless, octal, hex, IPv6, dashed hostnames, encoded slashes. Normalizes before matching. |
| [`hunt-cloud-storage-bucket-lookalike-references.kql`](./hunt-cloud-storage-bucket-lookalike-references.kql) | References to cloud storage buckets whose names are lookalikes of your real ones — homoglyphs, dashes-for-underscores, plausibly-typosquatted variants. |
| [`hunt-credential-compromise-signin-audit-alert-three-table.kql`](./hunt-credential-compromise-signin-audit-alert-three-table.kql) | Three-table credential-compromise chain: joins risky sign-ins, audit follow-up, and downstream SecurityAlert on the same user. |
| [`hunt-distributed-ssh-brute-force-per-target.kql`](./hunt-distributed-ssh-brute-force-per-target.kql) | SSH brute-force hunt that pivots on the target host, not the source IP — catches distributed attacks that stay under per-source thresholds by using thousands of IPs. |
| [`hunt-dns-aaaa-record-covert-recovery-channel.kql`](./hunt-dns-aaaa-record-covert-recovery-channel.kql) | Project CAV3RN's DNS AAAA-record recovery channel — IPv6 addresses returned in AAAA queries that decode as ASCII or structured config. |
| [`hunt-encoded-command-usage-across-fleet-time-baseline.kql`](./hunt-encoded-command-usage-across-fleet-time-baseline.kql) | Encoded-command executions correlated across the fleet against a rolling per-host time baseline. TimeBucket alone as the join key — deliberately no DeviceId. |
| [`hunt-first-time-admin-operation-user-baseline.kql`](./hunt-first-time-admin-operation-user-baseline.kql) | Baselines identities that have ever executed admin operations, then alerts when an account outside that set succeeds — 'the admin who has never administered.' |
| [`hunt-inflated-file-payload-evading-size-based-av-scan.kql`](./hunt-inflated-file-payload-evading-size-based-av-scan.kql) | File downloads anomalously large for their kind — Vidar's null-byte padding trick to slip past AV scanners that skip files above a size ceiling. |
| [`hunt-linux-process-argv0-vs-executable-mismatch.kql`](./hunt-linux-process-argv0-vs-executable-mismatch.kql) | Linux processes where argv[0] doesn't match the actual binary that was executed — a process wearing another process's name tag. |
| [`hunt-metadata-ip-any-encoded-form-inspecting-dns-answer.kql`](./hunt-metadata-ip-any-encoded-form-inspecting-dns-answer.kql) | Inspects what DNS actually resolved to (the Answer field), not what the caller wrote — catches every obfuscated string form of the metadata IPs at the resolver level. |
| [`hunt-npm-postinstall-config-modification-no-user-context.kql`](./hunt-npm-postinstall-config-modification-no-user-context.kql) | npm postinstall/lifecycle scripts that modified config without a corresponding interactive user command — AsyncAPI-shaped supply-chain compromise. |
| [`hunt-npm-postinstall-grandchild-network-payload.kql`](./hunt-npm-postinstall-grandchild-network-payload.kql) | npm supply-chain worms where the payload runs two process generations down — 'sins of the grandfather' shape. Traces npm → sh -c → curl. |
| [`hunt-outlook-calendar-c2-far-future-standing-meeting.kql`](./hunt-outlook-calendar-c2-far-future-standing-meeting.kql) | Project CAV3RN's Outlook calendar C2 — standing meetings scheduled decades in the future in fixed low-attention windows, carrying operator-agent traffic in the event body. |
| [`hunt-suspicious-user-consented-oauth-app-grants.kql`](./hunt-suspicious-user-consented-oauth-app-grants.kql) | 'The backdoor you approved yourself' — OAuth application consents granting broad Graph permissions to unfamiliar apps. Focuses on CONSENT events, not the logins that follow. |
| [`hunt-teams-phishing-then-suspicious-login-correlation.kql`](./hunt-teams-phishing-then-suspicious-login-correlation.kql) | Teams phishing messages correlated with subsequent suspicious sign-ins for the same recipient — deals with ExternalAccess not being populated by falling back to sender-domain-outside-org. |
