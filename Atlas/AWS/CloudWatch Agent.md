---
dudas:
tags:
aliases:
  - CW Agent
---
### Dudas
- [x] ¿para qué me sirve la config centralizada del agente en [[SSM Parameter Store]] y cómo se implementa?
	Para tenerla centralizada y no tener que volver a definirla en el config local de cada agente.
### Notas
### Palabras clave
- concept -- 4 virtual servers = { on-prem & [[Elastic Compute Cloud|EC2]] } logging (por defecto EC2 no loggea), needs [[Identity and Access Management|IAM]] role 2 log
	- CW Logs Agent — oldest, sends only logs
	- CW Unified Agent — more granular metrics and logs, newest