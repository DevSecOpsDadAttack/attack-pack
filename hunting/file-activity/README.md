# file-activity

File-level activity queries — the "prove to an auditor we can track this" set, plus artifact-based detections that read files as evidence of network events.

| Query | Description |
| --- | --- |
| [`detect-spring-boot-heapdump-artifact-on-disk.kql`](./detect-spring-boot-heapdump-artifact-on-disk.kql) | Detects Spring Boot Actuator heap-dump theft by the artifact Spring writes to disk during the request (`heapdump<timestamp>[-live]<digits>.hprof`). The filename is proof an HTTP request hit the endpoint even when the web tier didn't log the URL. |
| [`file-activity-audit.kql`](./file-activity-audit.kql) | Timestamped file activity (open, read, modify, delete, create) by user and device. Written for a client that needed to demonstrate this capability to an auditor. |
