---
dudas: true
tags:
  - DVA02-8
  - database
  - sql
  - cloud-native
aliases:
  - Aurora
---
### Dudas
- encrypt' -- ¿qué significa que se deba definir la encriptación at launch time? ¿cuándo es launch time?
- ídem -- no entiendo cómo se habilita el inflight encrypt'
- security groups -- ¿cómo se settean?
- logs -- ¿cómo se activan?
- clusters?
### Notas
### Palabras clave
- props
	- proprietary, cloud native => faster than [[Relational DB Service|RDS]]
	- postgres & sql
	- auto growth -- more data => growth by 10gb increments, max = 256tb
	- replicas -- up 2 15, replica' faster than RDS, 1 master -> m replicas, 1 master EP pointing 2 current master, 1 read EP pointing 2 all replicas (as a [[Atlas/AWS/Elastic Load Balancer]])
		- R/W EPs r asoc'd directly 2 DB
	- auto failover -- 2 a replica
	- $ $ $ RDS
	- "backtrack" -- restore at any point in time w/o backups
- integrations -- [[SQL DB security integrations]]
