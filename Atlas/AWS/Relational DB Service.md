---
dudas: true
tags:
  - DVA02-8
  - database
  - sql
aliases:
  - RDS
---
### Dudas
- [ ] `ManageMasterUserPassword` -- ¿puede settearse desde la consola o sólo desde [[CloudFormation]]?
- [ ] storage backed by EBS -- ¿éso qué significa? ¿cómo se usa EBS tras bambalinas? ^35170a
- [ ] auto scale -- ¿cuáles son los criterios? ¿dónde se maneja? ¿cómo se settea? no entendí ^57b666
- [ ] read replicas & multi-az -- ¿dónde se settea para usar uno u otro? ^774a65
- [x] R disaster recovery & read replicas -- ¿cómo se settea para que una read replica esté stand-by para estar disponible en cuanto suceda el disaster?
	Es de forma manual (o mediante scripts que hagas vos). Seleccionás la réplica y la promovés a master. El tema es que hay que tener [[RDS Proxy]] para que al promover la réplica no haya que actualizar las referencias a la DB original en la app.
- [x] RDS & IAM -- ¿cómo se habilita la autenticación con IAM? ^79309d
	[[SQL DB security integrations#IAM DB auth|IAM DB auth]]
	
### Notas
### Palabras 
- concepto -- relational DB, SQL, managed
- prop
	- suprt'd engines -- postgres, mysql, mariadb, oracle, [[Atlas/AWS/Aurora]]
	- AWS manag'd -- auto backups, monitor dashboard, storage by [[Elastic Block Store|EBS]] ([[Relational DB Service#^35170a|duda]])
		- auto scaling -- use case: unpredictable workloads ([[Relational DB Service#^57b666|duda]]) ^69f360
	- read replica -- same/x-AZ (costenlos) | x-R ($ $), only 4 READ,
		- `async` replic' aka [[eventually consistent]] => might not always b up 2 date, promotable 2 own DB,
		- 1 new replica = 1 new EP that needs 2 b ref'd in sql conn string in app (use [[RDS Proxy]] 2 automate this)
		- ==use case: scaling reads, but can b used as failover in disaster recovery== ([[Relational DB Service#^774a65|duda]])
		- source not encrypt' ? replicas not encrypt'd : replicas encrypt'd
	- multi-AZ --
		- `sync` replica' 2 standby db,
		- same DNS name 4 failover,
		- ==use case: disaster recovery==,
		- how 2: modify DB & set 2 multi-AZ => DBsnapshot -> restore in stby db
- integrations -- [[SQL DB security integrations]] ([[Relational DB Service#^79309d|duda]])
