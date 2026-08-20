---
dudas:
tags:
  - network
  - DVA02-10
aliases:
---
### Dudas
### Notas
### Palabras clave
- concepto -- conectar dos VPCs (!= R o != user) para que funcionen como una VPC sola
- minucias
	- CIDR range no puede solaparse
	- conexión transitiva -- es directa, si A<->C y A<->B, B y C no pueden conectarse entre ellas, sí o sí debe haber una conexión explícita B<->C
