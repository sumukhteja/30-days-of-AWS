# Day 2: IAM users, groups and policies

IAM day. Simple on the surface but the policy evaluation logic is where the exam questions hide.

- Users are people or apps with long-term credentials. Groups hold users (groups can't contain groups). Roles are assumed and give temporary credentials.
- Policies are JSON with `Effect`, `Action`, `Resource`, and optional `Condition`.
- **Evaluation order:** explicit Deny beats everything. Then an Allow is needed. If nothing matches, it's an implicit deny.
- Root account: turn on MFA, don't create access keys, don't use it day to day.

Things I want to remember:
- Least privilege. Start small and add, don't start with `*`.
- Use groups to attach permissions instead of attaching to each user.
- The IAM credential report (account level) and access advisor (user level) help find unused permissions.

Easy mistake when writing a policy for one S3 bucket: bucket-level actions (`s3:ListBucket`) need the bucket ARN, while object actions need `bucket/*`. You usually need both.
