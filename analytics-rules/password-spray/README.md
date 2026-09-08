# password-spray

Detections for password-spray patterns against Entra ID sign-in logs (`SigninLogs`). Both queries are heuristic — tune the thresholds to your environment before promoting to an Analytics Rule.

| Query | Description |
| --- | --- |
| [`detect-low-and-slow-password-spray.kql`](./detect-low-and-slow-password-spray.kql) | Low-and-slow spray pattern (Storm-0940-shaped): many unique users from the *same* IP in a day, with roughly one failed attempt per user; includes optional legacy-user-agent hints. |
| [`detect-wide-low-volume-password-sprays.kql`](./detect-wide-low-volume-password-sprays.kql) | Wide, low-volume spray: from a single IP, exactly one failed attempt per user in a day, but against many different users. |
