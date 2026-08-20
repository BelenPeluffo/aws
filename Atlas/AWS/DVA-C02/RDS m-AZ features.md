---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: UDEMY
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
The development team at a health-care company is planning to migrate to AWS Cloud from the on-premises data center. The team is evaluating Amazon RDS as the database tier for its flagship application.

Which of the following would you identify as correct for RDS Multi-AZ? (Select two)

- a. Amazon RDS automatically initiates a failover to the standby, in case primary database fails for any reason
	Ésta está bien, es la que elegí.
- b. Updates to your DB Instance are asynchronously replicated across the Availability Zone to the standby in order to keep both in sync
	Ésta está mal: se replica sincrónicamente.
- c. RDS applies OS updates by performing maintenance on the standby, then promoting the standby to primary and finally performing maintenance on the old primary, which becomes the new standby
	Ésta es la segunda correcta. Lo que hace acá es explicar cómo es el proceso de pasar a la failover.
- d. To enhance read scalability, a Multi-AZ standby instance can be used to serve read requests
	Para la read scalability usas read-replicas. Es más barato, incluso.
- e. For automated backups, I/O activity is suspended on your primary DB since backups are not taken from standby DB
	No es necesario suspender la DB, el backup se hace solo y de forma automática al mismo tiempo en que se actualiza la principal.
### Condiciones
- 

### OPTS
a.

### Análisis
A y B
> [!note] Mi respuesta
> 
### Answer
A y C