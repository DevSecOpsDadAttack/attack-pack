# ingest-trends

Queries that compare ingest volume across time windows to spot upward drift, new noisy sources, or budget-eating trends.

| Query | Description |
| --- | --- |
| [`30-60-90-day-common-security-log-ingest-trends.kql`](./30-60-90-day-common-security-log-ingest-trends.kql) | Compare `CommonSecurityLog` volume by `DeviceAction` across 30-, 60-, and 90-day periods to spot which actions are driving growth. |
| [`30-60-90-day-ingest-trends.kql`](./30-60-90-day-ingest-trends.kql) | Same three-window comparison against the `Usage` table for a workspace-wide view. |
| [`day-by-day-change.kql`](./day-by-day-change.kql) | Percent change in daily ingest volume vs the previous day over the last 31 days. |
| [`log-sources-with-greatest-delta.kql`](./log-sources-with-greatest-delta.kql) | Which data sources moved the most between the previous 30 days and the current 30 days — the "who suddenly got loud" query. |
