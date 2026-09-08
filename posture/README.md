# posture

Attack-surface and asset-posture queries against Defender for Endpoint's TVM tables.

| Query | Description |
| --- | --- |
| [`which-devices-are-internet-facing.kql`](./which-devices-are-internet-facing.kql) | Identify internet-facing devices — walks through what "public" actually means for both IPv4 and IPv6 before matching. |
| [`which-devices-or-software-are-eol.kql`](./which-devices-or-software-are-eol.kql) | Devices running at least one end-of-support / end-of-life software title or version, from `DeviceTvmSoftwareInventory`. |
