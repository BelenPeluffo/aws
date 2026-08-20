---
dudas: true
tags:
  - DVA02-6
  - storage
  - ec2
  - network
  - permanent
aliases:
  - EBS
---
### Dudas
- vol types -- provisioned -- ¿pueden ser boot type? ^provisioned-vol-type-boot
	Sí, sólo los HDD no puede serlo.
### Notas
### Palabras clave
- concept -- storage 4 [[Elastic Compute Cloud|EC2]] (like a network usb stick), allows 4 encrypt' in all fronts via [[Key Management Service|KMS]]
- props
	- data persistance after termination
	- 1 vol->1 [[Elastic Compute Cloud|EC2]], but 1 EC2-> M vols, can b attach'd on demand
	- AZ-scop'd
	- connected via network
	- provision'd capacity -- increasable
	- `delete on termination` -- by default: root=true & non-root=false, customizable
	- multi-attach -- 1vol -Z M EC2 within 1AZ
	- vol types
		- general purpose SSD -- boot vol
			- gp2 -- older, IOPS&troughput
			- gp3 -- IOPS//throughput
		- provisioned IOPS SSD -- IOPS performance, MULTI-att support'd ([[Elastic Block Store#^provisioned-vol-type-boot|duda]])
			- io1
			- io2 block express -- fastest
		- hard disk drives (HDD) -- no boot, capacity as io1
			- st1 -- IO optimiz'd HDD, data warehouse/log processing
			- sc1 -- cold HDD, data infreq acc'd
- Snapshots ^ebs-snapshots
	- vol backup ready 2 restore (or transfer)
	- uses [[Simple Storage Service|buckets]] bts
		- Snapshot Archive -- uses archive tear, cheaper, 24/72hs restore time
	- Recycle Bin -- rules 4 retain b4 deleting 2 recovering, ttl: 1d-1y
	- Fast Snapshot Restore -- 4 big vols n' fast init, $ $ $ $ $