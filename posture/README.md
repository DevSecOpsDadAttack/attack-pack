# posture

Attack-surface and asset-posture queries — the inventory-style queries that hand you a finite, closable list rather than an infinite stream of adversary telemetry.

| Query | Description |
| --- | --- |
| [`inventory-exposed-spring-boot-actuator-endpoints.kql`](./inventory-exposed-spring-boot-actuator-endpoints.kql) | Inventory of Spring Boot Actuator endpoints that answer 200 anywhere in your estate — flips the entity from "who scanned us" (infinite) to "which of my services answer" (finite and fixable). Recovers the real management base path from traffic. |
| [`inventory-installed-npm-packages-with-lifecycle-scripts.kql`](./inventory-installed-npm-packages-with-lifecycle-scripts.kql) | Inventory of npm packages installed across your fleet that carry postinstall / preinstall / install lifecycle scripts — the finite, closable population for sins-of-the-grandfather class attacks. |
| [`which-devices-are-internet-facing.kql`](./which-devices-are-internet-facing.kql) | Identify internet-facing devices — walks through what "public" actually means for both IPv4 and IPv6 before matching. |
| [`which-devices-or-software-are-eol.kql`](./which-devices-or-software-are-eol.kql) | Devices running at least one end-of-support / end-of-life software title or version, from `DeviceTvmSoftwareInventory`. |
