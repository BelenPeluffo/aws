---
dudas: true
tags:
  - SOA-C03
aliases:
  - AWS Orgs
---
### Dudas
- [x] SCP -- creación via CLI -- ¿qué otros valores puede tomar la propiedad `--type?` ✅ 2026-10-15
	[[AWS Organizations#^ec2d90|types]].
### Notas
### Palabras clave
- concepto -- centralize acc mgmt & gov, **align rr mgmt w business needs**
- *organizational unit* -- es para las acc lo que groups para users, f(business unit), siempre existe un root OU cuyos SCPs aplican para el resto de las OUs
- policies -- target={ OU, acc }, eval': explicit `DENY` > `ALLOW` > default `DENY`
	- elementos
		- `Action`
		- `Effect`
		- `Statement` -- `Array<Policy>`
		- `StatementID` -- friendly name
		- `Version`
		- `Condition`
		- `NotAction` -- es !Action = las acciones definidas no podrán accionarse
		- `Resource`
	- creation
		- via console
		- via CLI -- `aws organizations create-policy --content <.json> --name <name> --type SERVICE_CONTROL_POLICY`
	- examples
		- `FullAWSAccess` -- x defecto al crear
	- types ^ec2d90
		- AUTH -- sec ctrl
			- `SERVICE_CONTROL_POLICY` aka SCP -- limit accs 2 rr
			- `RESOURCE_CONTROL_POLICY` aka RCP -- mng # `ALLOW` perms 4 each r
		- MGTM
			- declarative -- centrally mng s config
			- backup -- central backup strategies
			- [[The art of TAGS|tag]] -- standardize tags
			- chat app -- regulate app accs from chat apps
			- AI opt-out
- [[Well-Architected Framework|WAF pillars]]
	- security -- MFA enforcement, acc segregation
		- x policies = f(ou) = SCP
	- cost opt -- consolidated billing
	- ops excel
		- central mgmt
			- acc creat' auto'
			- audit w [[CloudTrail]]