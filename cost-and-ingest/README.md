# cost-and-ingest

The FinOps side of Sentinel and Log Analytics — how much you're ingesting, where it's coming from, and what it's costing you. Everything here targets the `Usage` table, `_BilledSize`, or specific noisy sources.

## Subfolders

- [`ingest-trends/`](./ingest-trends/) — how ingest volume is changing over time (30/60/90-day comparisons, day-over-day delta, biggest movers).
- [`billable-volume/`](./billable-volume/) — raw billable volume queries (daily average, GB per table, cost calculations).
- [`cost-by-table/`](./cost-by-table/) — cost broken down by table / log source.
- [`cost-by-eventid/`](./cost-by-eventid/) — cost broken down by Windows Event ID or Syslog severity.

Many of these expect you to plug in your own effective per-GB rate for your workspace's region and commitment tier. See [Sentinel Cost Optimization Part 2](https://www.hanley.cloud/2023-05-15-Sentinel-Cost-Optimization-Part-2/) for how to calculate it.
