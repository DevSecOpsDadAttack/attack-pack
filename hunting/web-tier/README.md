# web-tier

Hunts against web session / HTTP telemetry — ASIM Web Session (`_Im_WebSession`) and its `CommonSecurityLog` fallback for non-ASIM workspaces.

| Query | Description |
| --- | --- |
| [`hunt-spring-boot-heapdump-exfiltration-asim.kql`](./hunt-spring-boot-heapdump-exfiltration-asim.kql) | Hunts Spring Boot Actuator heap-dump exfiltration in ASIM Web Session data by matching the endpoint ID as a path segment (position-independent) instead of hardcoding `/actuator/heapdump`. Recovers the real base path from traffic and ranks by response-size verdict. |
| [`hunt-spring-boot-heapdump-exfiltration-commonsecuritylog.kql`](./hunt-spring-boot-heapdump-exfiltration-commonsecuritylog.kql) | Non-ASIM (`CommonSecurityLog`) variant of the heap-dump hunt. Uses correct CEF field names (`ReceivedBytes` / `SentBytes`) and carries both byte directions because CEF doesn't tell you which side is the response. |
