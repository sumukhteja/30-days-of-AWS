# Day 5: EC2 pricing options

This one matters a lot for cost questions.

- **On-Demand**: pay per second, no commitment. Short or unpredictable workloads.
- **Reserved Instances**: 1 or 3 years, up to ~72% off. Standard RIs can't change family, Convertible can.
- **Savings Plans**: commit to a $/hour spend for 1 or 3 years. Compute Savings Plans are the most flexible (any family, region, even Lambda and Fargate).
- **Spot**: up to 90% off but AWS can take it back with a 2-minute warning. Great for batch jobs, CI, anything that can be interrupted.
- **Dedicated Hosts**: a whole physical server, needed for some per-socket or per-core licenses.
- **Dedicated Instances**: hardware not shared with other customers, but you don't control placement.
- **Capacity Reservations**: guarantee capacity in an AZ, no discount on their own.

Rule of thumb I'm going with: steady baseline on Savings Plans or RIs, spikes on On-Demand, interruptible stuff on Spot. Spot Fleet can mix instance types to keep capacity up.
