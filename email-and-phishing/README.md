# email-and-phishing

Defender for Office 365 queries against `EmailEvents` — phishing volume, malware, and external-account abuse patterns.

| Query | Description |
| --- | --- |
| [`external-email-accounts-synced-to-outlook-sending-attachments.kql`](./external-email-accounts-synced-to-outlook-sending-attachments.kql) | Employees using Outlook on corporate machines to send email via third-party SMTP servers, with attachments — a common data-exfiltration pattern. |
| [`top-blocked-malware-email-events.kql`](./top-blocked-malware-email-events.kql) | Top blocked malware email events. Does what it says on the tin. |
| [`top-phishing-domains.kql`](./top-phishing-domains.kql) | Top phishing *sender domains* with severity categorized by volume. |
| [`top-phishing-sender-recipient-pairs.kql`](./top-phishing-sender-recipient-pairs.kql) | Top phishing volume grouped by *(recipient, sender-domain)* pair — useful for spotting targeted campaigns against specific users. |
| [`top-phishing-targets.kql`](./top-phishing-targets.kql) | Top *recipients* of phishing emails (targeted individuals) with severity by volume. |
| [`whos-clicking-on-junk-mail.kql`](./whos-clicking-on-junk-mail.kql) | Users who clicked links in messages that landed in the Junk folder — a strong "who needs training" signal. |
