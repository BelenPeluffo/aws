---
dudas: true
tags:
  - network
  - DVA02-10
aliases:
---
### Dudas
- [x] ¿el flujo que llega a través del GW y la interface pasa antes por la NAT? ¿Cómo se integran estos RR al circuito de conectividad en que están el IGW, NACL y SG?
	No. Justamente se usa el VPC EP para evitar incurrir en gastos con la NAT.
- [ ] GW vs. Interface -- ¿uno se instancia en la subnet privada y el otro en la pública?
### Notas
### Palabras clave
- concepto -- vía de conexión entre RR en [[private subnet]] y los servicios públicos de AWS
- clases
	- VPC EP GW -- conn 2 [[Simple Storage Service|S3]] and [[Atlas/AWS/DynamoDB]] ^F2uuIY4E
	- VPC EP Interface -- conn 2 all other SS ^KxYdQQ9K
