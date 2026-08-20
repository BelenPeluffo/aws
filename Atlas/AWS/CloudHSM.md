---
dudas:
tags:
  - DVA02-30
aliases:
---
### Dudas
- integración con KMS -- ¿entonces CloudHSM no se puede usar sólo? ¿sí o sí necesita que KMS sirva de intermediario?
### Notas
### Palabras clave
- elements -- AWS provisions encrypt' hard, NO free tier, use case: SSE-Custom encrypt', high availability, VPC-scoped
	- Hardware Security Module -- encrypt' dedicated hard, tamper resistant, [[software layers|capa 3]]
	- keys -- user-managed
	- encrypt' -- assym & symm suported
	- Client Software -- 2 connect 2 CHSM, mgm: keys & users
- integrations
	- [[Redshift]] -- DB encrypt' & key mgmt
	- [[Atlas/AWS/Identity and Access Manager]] -- permissions: CRUD 4 HSM cluster
	- [[Key Management Service|KMS]] -- integra' para que KMS sea intermediario, CHSM funciona como custom key store de KMS