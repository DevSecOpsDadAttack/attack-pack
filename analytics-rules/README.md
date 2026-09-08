# analytics-rules

Queries designed (or used) as the body of a Sentinel Analytics Rule — they're written to produce discrete detection events on a schedule rather than to be run interactively.

## Subfolders

- [`password-spray/`](./password-spray/) — detections for password-spray patterns against Entra ID sign-in logs.
- [`failed-logins/`](./failed-logins/) — brute-force / failed-login threshold rules.
