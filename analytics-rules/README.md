# analytics-rules

Queries designed (or used) as the body of a Sentinel Analytics Rule — they're written to produce discrete detection events on a schedule rather than to be run interactively.

## Subfolders

- [`password-spray/`](./password-spray/) — detections for password-spray patterns against Entra ID sign-in logs.
- [`failed-logins/`](./failed-logins/) — brute-force / failed-login threshold rules.

## Standalone detections

Sourced primarily from the **[KQL Detection of the Week](https://devsecopsdadattack.com/kqldetectionoftheweek/)** series — each file's header carries a `// Source:` link to the article that walked through its design.

| Query | Description |
| --- | --- |
| [`detect-autogen-studio-agent-tool-execution-anomaly.kql`](./detect-autogen-studio-agent-tool-execution-anomaly.kql) | AutoGen Studio-hosted AI agent taking code-execution or sensitive-tool actions outside its baseline set — the 'AutoJack' agent-abuse shape. |
| [`detect-ci-build-egress-to-first-seen-domain.kql`](./detect-ci-build-egress-to-first-seen-domain.kql) | CI/CD build process reaching out to a domain never seen from your build fleet before — 'the build that called a stranger.' |
| [`detect-diagnostic-deletion-then-tenant-activity-same-session.kql`](./detect-diagnostic-deletion-then-tenant-activity-same-session.kql) | Enhanced log-suppression sequence detection that further requires the follow-on activity to share the same CallerIpAddress — same session, not just same identity. |
| [`detect-diagnostic-deletion-then-tenant-activity-sequence.kql`](./detect-diagnostic-deletion-then-tenant-activity-sequence.kql) | T1562.008 sequence: Azure diagnostic-setting deletion followed by any activity from the same Caller within 60 minutes. |
| [`detect-dll-masquerading-as-microsoft-defender.kql`](./detect-dll-masquerading-as-microsoft-defender.kql) | DLLs pretending to be Microsoft Defender via resource-level publisher/original-filename metadata — a Vidar Stealer TTP. |
| [`detect-excel-xll-addin-spawning-shell-or-network.kql`](./detect-excel-xll-addin-spawning-shell-or-network.kql) | Excel loading an XLL add-in that then spawns a shell or beacons out — the spreadsheet-as-shell malware delivery vector. |
| [`detect-nextjs-middleware-authorization-bypass.kql`](./detect-nextjs-middleware-authorization-bypass.kql) | Next.js middleware authorization-bypass pattern — successful requests to authenticated routes without going through the expected auth path. |
| [`detect-oauth-token-used-from-novel-country.kql`](./detect-oauth-token-used-from-novel-country.kql) | OAuth token used from a country the user has never signed in from — ToddyCat/Umbrij downstream shape where the token itself is the payload. |
| [`detect-peoplesoft-process-spawning-unexpected-shell.kql`](./detect-peoplesoft-process-spawning-unexpected-shell.kql) | Oracle PeopleSoft server processes (psadmin, psappsrv, java) spawning cmd, bash, whoami, curl, or net — post-exploitation shape of a PeopleSoft RCE. |
| [`detect-remote-shell-command-arrival-over-wire.kql`](./detect-remote-shell-command-arrival-over-wire.kql) | Shell command that arrived over the network — outbound-then-inbound-executed script pattern uncommon in legitimate remote code execution. |
| [`detect-sharepoint-toolshell-rce-encoded-command.kql`](./detect-sharepoint-toolshell-rce-encoded-command.kql) | SharePoint ToolShell RCE: encoded PowerShell arriving via SharePoint worker processes. Multi-token needles (`certutil -decode`) need `contains`, not `has_any`. |
| [`detect-smartconnect-session-without-signin.kql`](./detect-smartconnect-session-without-signin.kql) | Microsoft SmartConnect (CVE-2026-55040) sessions lacking a corresponding sign-in event — absence-detection with windowed leftouter + countif. |
| [`detect-successful-login-following-distributed-ssh-brute-force.kql`](./detect-successful-login-following-distributed-ssh-brute-force.kql) | Successful SSH login against a host that just weathered a distributed brute-force campaign. Pair with the Act-I hunt to know if the lightning hit anything. |
| [`detect-telegram-tdata-session-theft-file-access.kql`](./detect-telegram-tdata-session-theft-file-access.kql) | Theft of Telegram's tdata session directory by an unexpected process. Uses actual DeviceFileEvents ActionTypes (FileCreated/Modified) — `FileRead` doesn't exist. |
| [`detect-unsigned-dll-load-verified-signing-state.kql`](./detect-unsigned-dll-load-verified-signing-state.kql) | Unsigned DLL loads, using IsSigned/SigningStatus rather than treating an empty SHA256 as unsigned (the field is documented as usually-populated, not always). |
| [`detect-vpn-session-without-prior-authentication.kql`](./detect-vpn-session-without-prior-authentication.kql) | PAN-OS GlobalProtect VPN sessions established without a matching auth event in the preceding 5 minutes — the shape of CVE-2026-0257. Uses windowed leftouter, not range-predicate leftanti. |
