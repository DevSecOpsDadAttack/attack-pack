# cost-by-eventid

Cost broken down at the Event ID or Syslog-severity level — for when you need to justify filtering a specific noisy event out at the DCR.

| Query | Description |
| --- | --- |
| [`cost-of-eventid.kql`](./cost-of-eventid.kql) | Estimated cost of a single Event ID over a time window, using your effective per-GB rate. |
| [`cost-of-eventid-by-computer.kql`](./cost-of-eventid-by-computer.kql) | Breaks the cost of a specific Event ID out by originating computer (defaults to `EventID == 4672`). |
| [`cost-of-syslog-events-by-severity.kql`](./cost-of-syslog-events-by-severity.kql) | Cost of Syslog events grouped by severity level. |
| [`eventid-by-billedsize.kql`](./eventid-by-billedsize.kql) | Ingest volume in GB per Event ID from the `SecurityEvent` table. |
| [`top-10-eventids-windows-securityevents.kql`](./top-10-eventids-windows-securityevents.kql) | Top 10 most expensive Event IDs from the `SecurityEvent` table over the last 90 days. |
| [`top-10-windowsevent-eventids.kql`](./top-10-windowsevent-eventids.kql) | Top 10 most expensive Event IDs from the `WindowsEvent` table (AMA-shipped) over the last 90 days. |
