---
dudas: true
tags:
aliases:
  - 3TA
---
### Dudas
- [ ] subnets -- ¿dónde iría el [[RDS Proxy]] en esta arquitectura? En data o public?
### Notas
### Palabras clave
- capas
	- [[public subnet]] -- donde estará el load balancer ([[Atlas/AWS/Elastic Load Balancer]])
	- [[private subnet]] -- donde vive la app detrás de un [[auto-scaling grou]] ([[Elastic Compute Cloud|EC2]])
	- data subnet -- DB y cache ([[Relational DB Service|RDS]], [[ElastiCache]], [[Amazon Aurora|Aurora]])
