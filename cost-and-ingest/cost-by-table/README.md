# cost-by-table

Cost broken down by table or log source. Most of these use a manually-set `rate` variable that you should set to your region's effective per-GB price ([Sentinel pricing](https://azure.microsoft.com/en-us/pricing/details/microsoft-sentinel/)).

| Query | Description |
| --- | --- |
| [`cost-of-a-table.kql`](./cost-of-a-table.kql) | Estimated dollar cost of a single table over a chosen window, given your effective per-GB rate. |
| [`cost-of-workstations-logging-direct-to-sentinel.kql`](./cost-of-workstations-logging-direct-to-sentinel.kql) | Find workstations shipping logs directly to Sentinel and estimate what it's costing you. |
| [`how-loud-is-a-table.kql`](./how-loud-is-a-table.kql) | Row-count-per-day graph for a given table (defaults to `Syslog`) — a quick "is this table getting louder?" check. |
| [`top-10-billable-mde-tables.kql`](./top-10-billable-mde-tables.kql) | Top 10 most expensive Microsoft Defender for Endpoint tables over the last 90 days. |
| [`top-10-common-security-logs-by-reason-with-cost-enhanced.kql`](./top-10-common-security-logs-by-reason-with-cost-enhanced.kql) | Top `CommonSecurityLog` rows by `Reason` and `LogSeverity` (90d), ranked by event count, with an emoji cost-tier column. Filters out empty/`N/A` reasons. |
| [`top-10-common-security-logs-by-severity-with-cost.kql`](./top-10-common-security-logs-by-severity-with-cost.kql) | Top `CommonSecurityLog` groupings by `DeviceVendor`, `DeviceProduct`, and `LogSeverity` (30d), with numeric `CostUSD`. |
| [`top-10-log-sources-with-cost-enhanced.kql`](./top-10-log-sources-with-cost-enhanced.kql) | Top log sources by `DataType` (30d) with an emoji cost-tier and formatted `$X.XX` string — table/dashboard friendly. |
| [`top-10-log-sources-with-cost.kql`](./top-10-log-sources-with-cost.kql) | Top log sources by `DataType` (30d) with numeric `CostUSD`. The chart-friendly default. |
| [`top-10-security-events-with-cost-enhanced.kql`](./top-10-security-events-with-cost-enhanced.kql) | Top `SecurityEvent` `EventID`s (30d) with GiB, emoji cost-tier, and formatted `$X.XX` string. |
| [`top-10-security-events-with-cost.kql`](./top-10-security-events-with-cost.kql) | Top `SecurityEvent` `EventID`s with `Activity` (30d) and numeric `CostUSD`. |
| [`top-10-tables-exclude-mde.kql`](./top-10-tables-exclude-mde.kql) | Top 10 most expensive log sources over 90 days, excluding MDE, via the fast `Usage` table. |
