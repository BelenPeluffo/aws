---
dudas: true
tags:
  - DVA02-30
  - secrets-storage
  - auto-rotation
aliases:
---
### Dudas
- [ ] integración con [[Atlas/AWS/CloudFormation]] -- ¿cómo se implementa y para qué casos de uso?
- [ ] ídem -- `SecretRDSAttachment` -- ¿en el template de qué recurso tengo que linkear a la instancia de RDS para que rote? ¿en el mismo template en que defino la creación de la instancia de RDS? ¿y cómo funciona éso?
### Notas
### Palabras clave
- elementos -- ==secrets rotation==, m-R secrets = secret read replicas
- what is a secret? -- API keys, DB creds, auth tokens, sensible configs
	- types -- se define al momento de la creación vía consola ^2fb160
		- Creds 4 [[Relational DB Service|RDS]] #test-question  ^109370
		- Generic Secrets -- { API keys, tokens } = secrets not belonging 2 AWS ss
		- m-R secrets -- m-R secret replica'
- integraciones
	- [[Lambda]]
		- auto secrets gen' when rotate'
		- f(x) can use 2 get encrypted variables -- fx must have `secretsmanager:GetSecretValue` IAM permissions
	- [[Relational DB Service|RDS]] -- can store user & password 4 DB, `ManageMasterUserPassword=true` = implicit admin secret, retrievable 4 CForm via `!GetAtt <cluster>.MasterUserSecret.SecretArn`
	- [[Key Management Service|KMS]] -- secret encrypt'
	- [[CloudFormation]] -- SM provee secrets para stack via [[CloudFormation#^dinamic-refs|dinamic refs]]