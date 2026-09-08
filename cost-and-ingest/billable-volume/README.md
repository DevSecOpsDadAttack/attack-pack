# billable-volume

Raw billable-volume queries — how many GB per day, per table, per solution — plus the "efficiency exercise" that walks through why some formulations of these questions are much cheaper to run than others.

| Query | Description |
| --- | --- |
| [`90-day-billable-cost-per-day-formatted.kql`](./90-day-billable-cost-per-day-formatted.kql) | Daily billable GB and cost over 90 days, formatted as human-readable strings (`$X.XX / Day`, `XGB / Day`). Table-friendly, not chart-friendly. |
| [`90-day-billable-cost-per-day.kql`](./90-day-billable-cost-per-day.kql) | Daily billable GB and cost over 90 days with numeric `CostUSD`. The default cost-over-time view — plottable and aggregatable. |
| [`90-day-billable-volume-by-solution.kql`](./90-day-billable-volume-by-solution.kql) | Billable GB per day for the past 90 days, sliced by Solution, rendered as a column chart. |
| [`efficiency-exercise.kql`](./efficiency-exercise.kql) | Teaching walkthrough of the "average daily ingest" question written four ways, from a slow `search *` to an efficient `Usage`-scoped version with cost. Read this before writing your own daily-average query. |
| [`gb-per-table.kql`](./gb-per-table.kql) | Ingest volume in GB for a single table (defaults to `SecurityEvent`, swap as needed). |
