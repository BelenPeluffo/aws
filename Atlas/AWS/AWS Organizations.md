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
- [ ] tag policies -- ¿sólo se pueden crear a través de la consola de AWS Orgs?
- [x] s billing -- ¿qué features de AWS Orgs se cobran? ✅ 2026-10-16
	Ninguna. Es un free service.
- [ ] org member acc creat' -- en el campo de IAM role name, ¿qué suele definirse como valor? ¿cuáles son las BPs?
- [x] org policy type -- cuando creás una org aparentemente tenés que definir el policy type. ¿o sea que una org sólo puede tener definido SCP Ó RCP? ✅ 2026-10-16
	No es que tenés que *definir*, tenés que *enable*. Pueden tener *enabled* ambos types.
- [x] SCP scoping -- ¿por qué una child acc que tiene un explicit `ALLOW` para crear un bucket no puede hacerlo si la root/parent account no tiene también un explicit `ALLOW`? ¿No es que un explicit `ALLOW` le gana a los default-`DENY`? ✅ 2026-10-16
	Si la SCP de mayor jerarquía NO TIENE la policy `FullAccess` entonces se deben definir SÍ O SÍ los `ALLOW` de forma explícita, de lo contrario se interpreta todo como default `DENY`. Las SCPs de mayor jerarquía definen el terreno de acción con sus ALLOW explícitos. Si el ALLOW de una child acc está queriendo permitir una acción o una acción sobre un servicio que estén fuera de ese terreno definido, es coherente que NO PUEDA.
	Los scopes sólo pueden ACHICARSE top-down.
	Además, los `ALLOW` deben sostenerse en cada nivel bajo el que esté la child acc, de lo contrario, no podrá hacer uso de éste.
### Notas
- `ALLOW` NO ES LO MISMO QUE `GRANT`.
- SCP = boundary, [[Identity and Access Management|IAM]] = grant'd accs. ==🟠They are complimentary, not interchangeable==.
### Palabras clave
- concepto -- centralize acc mgmt & gov, **align rr mgmt w business needs**, kostenloss
- *organizational unit* -- es para las acc lo que groups para users, f(business unit), siempre existe un root OU cuyos SCPs aplican para el resto de las OUs
- policies -- target={ OU, acc }
	- eval'
		- = level -- explicit `DENY` > `ALLOW` > default `DENY`
		- != level
			- explicit `ALLOW` in EVERY level otherwise it's not going 2 b allowed
			- explicit `DENY` in one level affects all lower levels
	- estrategias de asignación -- `FullAWSAccess` is ass'd by default
		- allow-list -- la root NO tiene `FullAWSAccess` => se deben definir los límites del scope explícitamente usando `ALLOW` y deben definirse en TODOS los niveles inclusive el nivel target
		- deny-list -- la root tiene `FullAWSAccess` => se debe acortar el scope de alcance usando `DENY` explícitos
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
		- AUTH -- secur ctrl
			- `SERVICE_CONTROL_POLICY` aka SCP -- limit accs 2 rr (which ss, what acts), **NO GRANT, JUST ==SCOPES== ACTS & SS AVAILABLE** (the s that GRANTS is [[Identity and Access Management|IAM]]/r-policy)
				- examples
					- restrict policies applicable 2 a s
					- allow x ss 2 b used and not others
					- limit instance types
					- prevent termination
				- AUTH troubleshooting? -- check 4 both SCPs & IAM
			- `RESOURCE_CONTROL_POLICY` aka RCP -- mng # `ALLOW` perms 4 each r
		- MGTM
			- declarative -- centrally mng s config
			- backup -- central backup strategies
			- [[The art of TAGS|tag]] -- standardize tags 4 tag consistency x-acc
				- structure
					```json
						{
							"tags": {
								"<policy-name>": {
									"tag_key": {
										"@@assign": "<tag-key>"
									},
									"tag_value": {
										"@@assign": [
											"value-1",
											"value-2"
										]
									},
									"enforced_for": {
										"@@assign": [
											"aws-r:name",
											"aws-r:name"
										]
									}
								}
							}
						}
					```
			- chat app -- regulate app accs from chat apps
			- AI opt-out
- API actions
	- `create-organization`
	- `create-account`
	- `invite-account`
	- `create-policy`
	- `attach-policy`
- [[Well-Architected Framework|WAF pillars]]
	- security -- MFA enforcement, acc segregation
		- x policies = f(ou) = SCP
	- cost opt -- consolidated billing
	- ops excel
		- central mgmt
			- acc creat' auto' -- via console u can add E acc n create acc
			- OU creat'
			- audit w [[CloudTrail]]