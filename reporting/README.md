# reporting

Periodic-summary queries for stakeholder reporting — weekly, monthly, or quarterly. The "here's what happened this period and what changed" view.

| Query | Description |
| --- | --- |
| [`alert-trends.kql`](./alert-trends.kql) | Alerts with significant increases vs the previous 90-day period, with severity categorized. |
| [`data-sources-with-biggest-delta-in-log-volume.kql`](./data-sources-with-biggest-delta-in-log-volume.kql) | Data sources with the biggest log-volume delta between comparison periods — configurable tunables at the top of the query. |
| [`report-queries.kql`](./report-queries.kql) | Grab-bag of reporting queries starting with MTTR against `SecurityIncident`. |
