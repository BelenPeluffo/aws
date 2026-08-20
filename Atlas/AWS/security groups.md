---
dudas: true
tags:
  - security
  - DVA02-10
aliases:
  - security group
---
### Dudas
- [ ] ¿con qué servicios se puede usar security groups?
### Notas
### Palabras clave
- concepto -- virtual firewall
- [[VPC]]-bound
- traffic -- only `ALLOW` policies, must define source/target
	- direction
		- in-bound -- por defecto no permite ninguno, must b explicit
		- out-bound -- por defecto permite todo ^5d828e
	- error
- lo más recomendado es referir a SGs más que a IPs.