# file-activity

File-level activity queries — the "prove to an auditor we can track this" set.

| Query | Description |
| --- | --- |
| [`file-activity-audit.kql`](./file-activity-audit.kql) | Timestamped file activity (open, read, modify, delete, create) by user and device, joining `DeviceEvents`, `DeviceNetworkEvents`, and `DeviceFileEvents`. Written for a client that needed to demonstrate this capability to an auditor. |
