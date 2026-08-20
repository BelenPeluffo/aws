---
dudas:
tags:
  - network
  - monitoring
  - troubleshooting
  - connectivity
  - DVA02-10
aliases:
---
### Dudas
### Notas
### Palabras clave
- concepto -- observa tráfico a VPC, subnet e ENIs ([[Internet Gateway]])
- (algunas) propiedades del log
	- puerto e IP de origen y destino
	- start y end time -- hora de dicho movimiento
	- action -- si se permitió o no el tráfico
- integraciones
	- almacenamiento/tráfico de logs -- [[Simple Storage Service|S3]], [[CloudWatch Logs|CW Logs]], [[Kinesis Data Firehose]]
	- 