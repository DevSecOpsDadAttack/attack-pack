# pihole

Queries against Pi-hole DNS data ingested into a Log Analytics workspace (as a custom `PiHole` / `pihole_CL` table). Useful for home-lab telemetry, DNS-based hunting practice, and workshop material.

| Query | Description |
| --- | --- |
| [`blocked-queries-over-time.kql`](./blocked-queries-over-time.kql) | Count of blocked DNS queries bucketed over time. |
| [`dns-query-volume.kql`](./dns-query-volume.kql) | Total DNS query volume over time — the baseline "how loud is DNS" view. |
| [`most-queried-domains.kql`](./most-queried-domains.kql) | Top 10 most-queried domains. |
| [`new-or-rarely-seen-domains.kql`](./new-or-rarely-seen-domains.kql) | Domains seen in the last 24h that haven't been seen recently — a classic new-domain-observed hunt. |
| [`pihole-usage.kql`](./pihole-usage.kql) | Billable ingest volume for the Pi-hole custom log over the last 90 days. |
| [`query-type-distribution.kql`](./query-type-distribution.kql) | Distribution of DNS query types (A, AAAA, TXT, etc.). |
| [`success-vs-failure.kql`](./success-vs-failure.kql) | Successful vs failed DNS query counts. |
| [`top-blocked-domains.kql`](./top-blocked-domains.kql) | Top 10 blocked domains. |
| [`top-clients.kql`](./top-clients.kql) | Top 10 clients by DNS query count. |
