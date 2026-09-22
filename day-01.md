# Day 1: Cloud basics and global infrastructure

Started with the big picture before touching any service.

- A **Region** is a physical area (like us-east-1). Each region has multiple **Availability Zones**, which are separate data centers with their own power and networking, close enough for low latency.
- **Edge locations** are way more numerous than regions. CloudFront and Route 53 live there.
- Most services are regional. A few are global: IAM, Route 53, CloudFront, WAF (for CloudFront).
- Picking a region comes down to four things: compliance (data residency), latency to users, service availability, and price. Prices really do differ between regions.

The shared responsibility model finally clicked for me. AWS secures the cloud itself (hardware, facilities, the hypervisor). I secure what I put in it (data, IAM, OS patches on EC2, security groups). For managed services like RDS, AWS takes over more of that line, like patching the DB engine.

Plan for the next 29 days: one area per day, notes here, and keep a list of the things I get wrong in `mistakes.md`.
