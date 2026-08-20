---
dudas: true
tags:
  - version-tracking
  - secrets-storage
  - DVA02-30
  - config-storage
aliases:
---
### Dudas
- secrets storage -- ¿[[diferencias entre KMS, Secrets Manager y Parameter Store]]?
- Secrets Manager integration -- ¿cómo funciona esa integración?
### Notas
- SSM viene de [[(Simple) Systems Manager]].
### Palabras clave
- elementos -- storage 4 ==config & secrets==, ==nesting hierarchy==
	- parameters -- ==version tracking== & mgmt via console/CLI/SDK
		- tiers
			- standard -- 10k params, <4kb, no policies allowed, free
			- advanced -- 100k params, <8kb, policies allowed, $0.05/param/month
		- policies
			- ttl
		- Type=`SecureString` -- permite el cifrado del valor del parámetro ^f64ae1
- integrations
	- [[Key Management Service|KMS]] -- optional encrypt'
	- [[Identity and Access Management|IAM]] -- auth
	- [[EventBridge]]
	- [[Atlas/AWS/CloudFormation]] -- PS provee secrets para stack via [[CloudFormation#^dinamic-refs|dinamic refs]]
	- [[Secrets Manager]] -- can pull secret from that s
