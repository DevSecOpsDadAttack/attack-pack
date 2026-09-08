# health-checks

Meta-queries about the workspace itself — is your detection stack actually working, and what's it firing on?

| Query | Description |
| --- | --- |
| [`analytics-rule-health.kql`](./analytics-rule-health.kql) | Analytics Rules that ran successfully in the last 90 days but never produced an alert — candidates for review or tuning. |
| [`top-10-alerts.kql`](./top-10-alerts.kql) | Top 10 alert names over 90 days with percentage of total and color-coded impact level (High / Moderate / Low). |
