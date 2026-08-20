---
dudas: true
tags:
  - DVA02-27
aliases:
---

### Dudas
- [x] ¿qué diferencia hay entre **user** pools y **identity** pools?
	[[Amazon Cognito#^CUP|CUP]] es una DB de users y se encarga de la autenticación a tu app. Pregunta: WHO R U?
	[[Amazon Cognito#^CIP|CIP]] se encarga de los permisos asociados a rr AWS => la autorización. Pregunta: WHAT R U ALLOWED 2 DO?
### Notas
- diferencia con [[Identity and Access Management|IAM]] -- Cognito es para auth FUERA del AWS ecosys
- CUP & CIP -- el user se auth con [[Amazon Cognito#^CUP|CUP]] y obtiene un JWT, se lo envía a [[Amazon Cognito#^CIP|CIP]] y éste valida contra CUP. Si el JWT es válido, devuelve a través de STS las temp creds al user.
### Palabras clave
- concepto -- user ID 4 web/mobile app
- services -- 1. user logs in (user pool) -> 2. user gets perms (ID pool)
	- User Pools -- sign-in functionality = authENTIC', user server- DB, API return JWT, hosted UI (so u don't have 2 code it) ^CUP
		- blocks compromised creds
		- ID providers 4 federated auth
			- social media accs
			- SAML accs -- corp envs
		- integrations
			- [[API Gateway|API-GW]]
			- [[Atlas/AWS/Elastic Load Balancer|App LB]] -- el servicio puede encargarse de la auth, desacopla lógica de auth de la app, config LB = HTTPS
			- [[Lambda]] -- can b trigger'd based on auth/sign-up/sms/token events
				- trigger events ^b533d2
					- pre sign-up
					- post confirm
					- pre auth
					- post auth
					- pre token gen
	- Identity Pools -- ==temp creds== (= authORIZE) 4 direct acc 2 rr thru [[Security Token Service|STS]]'s `AssumeRoleForWebIdentity` API ^CIP
		- role assignment -- based on user ID, must have TRUST policy 4 CIP
