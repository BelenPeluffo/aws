---
dudas: false
tags:
  - DVA02-29
  - security
aliases:
  - STS
---
### Dudas
- [x] `AssumeRoleWithSAML` -- ??
- [x] `DecodeAuthorizationMessage` -- ??
### Notas
### Palabras clave
- concept -- allow acc via token up 2 1h
- props
	- use case
		- user externo acceda a cuenta para hacer algunos trabajos
		- x-acc role-assumption
	- APIs
		- ==`AssumeRole`==
		- `AssumeRoleWithSAML` -- para loggearse con users de ID providers (IdP) que usan estándar SAML y evitar tener que crear un principal en AWS
		- `AssumeRoleWithWebIdentity` -- para logins federados que usan google/fb que usa estándar OIDC, pero ahora se prefiere el uso de [[Atlas/AWS/Cognito]]
		- ==`GetSessionToken`==
		- `GetFederationToken`
		- ==`GetCallerIdentity`== -- retorna data de la identidad asociada a las creds
		- ==`DecodeAuthorizationMessage`== -- para decodificar mensaje de error de auth
	- endpoints -- se define a través de la definición de la llamada con el SDK en el código de la app ^98fa6e
		- global -- `sts.amazonaws.com`, accesible globally, may lead 2 latency
		- regional -- `sts.<region>.amazonaws.com`, fixes latency err, using it is BP