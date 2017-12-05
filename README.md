# fantastic-enigma
When to RAID
	Storage requirements > 16TB
	Throughput requirements > 500 MB/s
	IOPS requirements > 20,000 @ 16K
Avoid RAID for redundancy
	EBS data is already replicated
	RAID1 havles available EBS bandwidth
	RAID5/6 loses 20-30% of usable I/O to parity
Best practices: taking snapshots from Linux
	Quiesce I/O
		Database: FLUSH and LOCK tables
		Filesystem: sync and fsfreeze
		EBS: snapshot all volumes
		When CreateSnapshot API returns success, it is safe to resume.

