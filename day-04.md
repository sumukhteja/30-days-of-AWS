# Day 4: EC2 basics

The compute basics.

- Instance type naming: `m7g.large` means family m (general purpose), generation 7, g for Graviton, size large.
- Families to know: **t/m** general purpose, **c** compute, **r/x** memory, **i/d** storage heavy, **p/g** GPU.
- **Security groups** are stateful and only have allow rules. Return traffic is automatically allowed.
- User data runs once at first boot as root. Good for installing packages.
- AMIs are regional. You can copy them to other regions.

Placement groups came up too:
- **Cluster**: same rack, lowest latency, HPC. One AZ, higher risk if hardware fails.
- **Spread**: each instance on separate hardware, max 7 per AZ. For a small number of critical instances.
- **Partition**: groups of racks, for things like Kafka, Cassandra, HDFS.

Also learned EC2 Instance Connect and Session Manager. Session Manager means no SSH port open at all, which is nicer.
