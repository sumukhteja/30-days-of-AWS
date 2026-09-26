# Day 6: EBS and instance store

Block storage day.

- **EBS** is network attached, lives in one AZ. To move it to another AZ you snapshot it and restore.
- Volume types:
  - **gp3**: default general purpose SSD. You set IOPS and throughput separately from size. Cheaper than gp2.
  - **io2 Block Express**: high IOPS, for big databases. Supports Multi-Attach (same AZ).
  - **st1**: throughput HDD for big sequential stuff like logs.
  - **sc1**: cold HDD, cheapest.
- HDD types can't be boot volumes.
- Snapshots are incremental and stored in S3 behind the scenes. You can copy them across regions for DR.
- Encryption uses KMS. Encrypting an existing unencrypted volume means snapshot, copy the snapshot with encryption, then create a new volume.

**Instance store** is disk physically on the host. Super fast, but the data is gone if the instance stops or the host fails. Fine for caches and scratch space, never for anything you need to keep.

The "Delete on termination" flag is on for the root volume by default and off for extra volumes. Good trivia.
