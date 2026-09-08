# user-activity

"What has this user been doing?" queries. Powerful enough to be worth handling carefully — some of these return browsing history and file access details, so mind your GDPR/privacy obligations before running them in prod.

| Query | Description |
| --- | --- |
| [`rdp-logins-per-day-per-user.kql`](./rdp-logins-per-day-per-user.kql) | RDP logins per user per day (30d) rendered as a timechart. Use for baselining "normal" login volume before hunting for anomalies. |
| [`whats-this-user-doing.kql`](./whats-this-user-doing.kql) | Unions `DeviceEvents`, `DeviceNetworkEvents`, and `DeviceFileEvents` to give a timestamped activity trace for a single user, including URLs touched. Swiss-army knife for user investigations — includes a Facebook-usage example. |
| [`whos-logging-in-and-when.kql`](./whos-logging-in-and-when.kql) | Timestamped feed of RDP logon (4624/LogonType 10), logoff (4634), and reconnect/disconnect (4778/4779) events over 30 days. |
