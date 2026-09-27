# Day 7: EFS and FSx

File storage day. The trick is knowing which one fits which question.

**EFS**
- Managed NFS for Linux. Many instances across AZs can mount it at the same time.
- Scales automatically, you pay for what you use.
- Storage classes with lifecycle policies (Standard, Infrequent Access, Archive) to save money.
- Performance modes and throughput modes. Elastic throughput is the easy default now.

**FSx**
- **FSx for Windows File Server**: SMB, Active Directory integration. Anything that says Windows shares.
- **FSx for Lustre**: HPC and ML. Can link to an S3 bucket.
- **FSx for NetApp ONTAP**: NFS, SMB and iSCSI, good for lifting existing NetApp setups.
- **FSx for OpenZFS**: NFS, snapshots, low latency.

My quick filter:
- Linux shared files across AZs: EFS
- Windows / SMB / AD: FSx for Windows
- HPC, "high performance parallel": FSx for Lustre
- One instance needs a disk: EBS
