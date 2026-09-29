# Day 9: Auto Scaling groups

Went through ASGs today.

- Set min, desired and max capacity. Uses a **launch template** (launch configurations are legacy).
- Spread across multiple AZs for availability. The ASG rebalances if one AZ ends up with too many.
- Can use ELB health checks so unhealthy instances behind the LB get replaced, not just ones that fail EC2 status checks.

Scaling policies:
- **Target tracking**: "keep CPU at 50%". Easiest, and usually the answer.
- **Step scaling**: different adjustments at different alarm thresholds.
- **Scheduled**: known traffic patterns, like scale up every Monday at 9.
- **Predictive**: uses history to scale ahead of time.

Cooldown period stops it from launching and terminating in a panic loop. Lifecycle hooks let you run something when an instance launches or terminates (like draining logs first).

Mixed instances policy can combine On-Demand and Spot in one group, which connects nicely with day 5.
