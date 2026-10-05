---
dudas: true
tags:
  - SOA-C03
aliases:
  - Identity Center
  - ID Center
---
### Dudas
- [ ] IAM ID center es R-specific?
- [ ] ¿cómo son de distintos los Users de ID center de los de IAM? ^4e82c7
- [ ] ¿cómo se define específicamente la conexión entre ID Center y el 3P IDP?
### Notas
- [ ] app assmt -- no entiendo nada. O sea, entiendo que es asignar accs a apps, pero **¿dónde se definen?**
### Palabras clave
- concepto -- centralice accs mgmt 2 acc & apps = SINGLE SOURCE OF TRUTH => consistency x-acc
- ID source
	- ID center directory -- native
	- 3P IDP
	- AWS Directory S
- Users -- a little != from [[Identity and Access Management#^5a256f|IAM Users]] ([[IAM Identity Center#^4e82c7|duda]])
- permission set -- [[Identity and Access Management#^d4360f|IAM policies]], template-like 4 roles n permits, REC: design 1 4 each job f(x), they r then ass'd 2 users/groups
	- assmt
		- defines WHO -> WHAT
		- **creates Roles** n' trust policies in target acc
		- auto inheritance GROUP -> USR
		- changes propagate auto
- app assmt -- WHO -> WHICH APP map
- instance
	- org -- [[AWS Organizations]], REC'D
	- acc -- intra-acc, 4 isolated deploys