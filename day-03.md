# Day 3: IAM roles, STS and Organizations

Roles are the real star of IAM.

- An EC2 instance gets permissions through an **instance profile** wrapping a role. Never put access keys on an instance.
- **STS AssumeRole** hands out temporary credentials. This is how cross-account access works: the role in account B trusts account A, and a user in A gets permission to call `sts:AssumeRole` on it.
- The role's **trust policy** says who can assume it. The permissions policy says what it can do. Two separate things, took me a minute.

AWS Organizations:
- Management account plus member accounts, grouped into OUs.
- **SCPs** set the maximum permissions for accounts in an OU. They never grant anything on their own. Even the root user of a member account is limited by them.
- SCPs don't affect the management account.
- Consolidated billing gives volume discounts across accounts.

IAM Identity Center is the recommended way to give people SSO access into many accounts. Permission boundaries are similar to SCPs but for a single user or role.
