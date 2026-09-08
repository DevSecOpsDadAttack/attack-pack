# eventid-forensics

Investigative queries organized around a specific Windows Event ID — the "who, where, when, how often" set. Replace the sample `EventID` value in each query with the one you're chasing.

| Query | Description |
| --- | --- |
| [`how-many-times-does-this-eventid-fire-from-this-machine.kql`](./how-many-times-does-this-eventid-fire-from-this-machine.kql) | Count of a specific Event ID from a specific machine, bucketed daily and rendered as a column chart. |
| [`which-accounts-are-throwing-this-eventid.kql`](./which-accounts-are-throwing-this-eventid.kql) | Which accounts fire a specific Event ID and how often, per day. |
| [`which-devices-are-throwing-this-eventid.kql`](./which-devices-are-throwing-this-eventid.kql) | Which computers fire a specific Event ID and how often, per day. |
| [`which-eventid-fires-the-most-in-a-month.kql`](./which-eventid-fires-the-most-in-a-month.kql) | Noisiest Event IDs across the last month — good for spotting new noise sources. |
| [`which-eventids-are-suddenly-acting-weird-with-context.kql`](./which-eventids-are-suddenly-acting-weird-with-context.kql) | Same deviation analysis as the basic variant, joined with `Computer` and `Account` so you can see which host or user is driving the spike in one shot. Uses a 30-day recent window to reduce join noise. |
| [`which-eventids-are-suddenly-acting-weird.kql`](./which-eventids-are-suddenly-acting-weird.kql) | Which Event IDs have recently spiked (7d) versus their 90-day baseline, sorted by deviation ratio. Basic variant — just EventID + counts. |
