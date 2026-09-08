# identity

Entra ID, Active Directory, and PIM activity queries — who did what to whom, when.

| Query | Description |
| --- | --- |
| [`who-deleted-an-ad-user.kql`](./who-deleted-an-ad-user.kql) | Who deleted an AD user (`SecurityEvent` EventID `4726`) over the last 90 days. |
| [`who-removed-a-user-from-group-chat.kql`](./who-removed-a-user-from-group-chat.kql) | Teams-related removal actions performed by a specific user in the last 7 days, from `OfficeActivity` / Unified Audit Log. |
| [`whos-activating-roles-via-pim.kql`](./whos-activating-roles-via-pim.kql) | PIM role activations from `AuditLogs` — useful for tracking privileged-role usage. |
