# failed-logins

Brute-force / failed-login threshold rules.

| Query | Description |
| --- | --- |
| [`failed-login-attempts.kql`](./failed-login-attempts.kql) | 3+ failed sign-ins (`ResultType == 50126` — invalid username or password) for the same UPN within a 2-minute window. Written for a demo that pairs with a Logic App to auto-disable or lock the account. |
