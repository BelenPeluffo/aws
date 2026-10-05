---
dudas: true
tags:
  - SOA-C03
aliases:
---
### Dudas
- [x] MFA -- ¿dónde se implementa éso? ✅ 2026-09-30
	Es una de [[Identity and Access Management#^c8e889|las settings de user]].
- [x] Accs patterns w [[Identity and Access Management#^938a32|IAM]]? ✅ 2026-10-02
	[[Identity and Access Management#^d543e7|accs pattern]]
- [x] [[Identity and Access Management#^fda6f7|r-policies]] - Cuando se definen los `Principals` en la r-policy, ¿debe listarse el s que accederá a él o el Role que el s asumirá para acceder a él? ✅ 2026-10-02
	El rol.
- [x] ídem -- ¿[[Lambda]] sí o sí siempre debe actual a través de un Role cuando es `Principal` sin importar que el accs se esté gestionando en el otro r a través de sus r-policies? ✅ 2026-10-02
	Sí.
- [x] ídem -- es siempre `Principal.AWS`? ✅ 2026-10-02
	No. [[The art of policies#^9cbc74|Hay otras]]. En los ejemplos aparece mucho `AWS` y `Service` porque el primero es para definir el ROL y el segundo para los servicios.
- [x] [[Identity and Access Management#^5ec1d6|trust policies]] -- ¿dónde se definen? ¿en el ctx del Role? ✅ 2026-10-02
	Sí, en el ctx del Role.
### Notas
### Palabras clave
- concept -- PILLAR: [[Well-Architected Framework#^8f68ef|SECURITY]]
- temario
	- [[Identity and Access Management#^1a7412|core components]]
	- [[Identity and Access Management#^938a32|Roles]]
	- [[Identity and Access Management#^5a256f|Users]]
	- [[Identity and Access Management#^454e79|Federation]]
	- [[Identity and Access Management#^d543e7|accs patterns]]
	- [[Identity and Access Management#^d4360f|policies]]
		- permission
			```json
			{
				"Version": "",
				"Statement": [
					{
						"Effect": "Allow",
						"Action": ["s3:GetObject"],
						"Resource": "arn:aws:s3:::my-bucket/*"
					}
				]
			}
			```
		- [[Identity and Access Management#^5ec1d6|trust]]
		```json
			{
				"Version": "",
				"Statement": [
					{
						"Effect": "Allow",
						"Principal": {
							"Service": "lambda.amazonaws.com"
						},
						"Action": "sts:AssumeRole"
					}
				]
			}
		```
		- r-based (en este caso, 4 x-acc accs)
			```json
			{
				"Version": "",
				"Statement": [
					{
						"Effect": "Allow",
						"Principal": {
							"AWS": "arn:aws:iam::111122223333:role/lambda-execution-role"
						},
						"Action": "s3:GetObject",
						"Resource": "arn:aws:s3:::account-b-bucket/*",
						"Condition": {
							"StringEquals": {
								"aws:SourceAccount": "111122223333"
							}
						}
					}
				]
			}
			```
	- [[Identity and Access Management#^54dabf|BPs]]
- tools
	- [[Identity and Access Management|IAM]] -- entities & MFA
	- [[IAM Identity Center]] -- centralized auth & acc ctrl
	- [[IAM Access Analyzer]]
	- [[AWS Organizations]] -- 4 enforcing RCPs n SCPs x-acc
	- [[The art of policies|policies]]

