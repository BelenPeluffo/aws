---
dudas:
tags:
  - DVA02-30
  - DVA02-24
aliases:
---
### Dudas
- VPC & secrets -- ¿para poder acceder a los secretos definidos en PM/SM sí o sí tengo que definir una VPN para el build project?
- ídem -- ¿se pueden definir env vars en UPDATE o sólo en CREATE?
- ídem -- ¿se pueden definir sólo mediante consola o también usando CLI o SDK?
### Notas
### Palabras clave
- quid -- fully managed CI s, auto build & test on cloud → dev puede enfocarse en otra cosa, container creates based on buildspec, 2 access VPC RR must be configure'd 2 x VPC
- source — [[Atlas/AWS/CodeCommit|CCommit]], [[Simple Storage Service|S3]]
- elements
    - build instructions — `buildspec.yml` ó input en consola
        - env vars — `variables`, `parameter-store`, `secrets-manager`
        - `phases` — pasos que tienen que ejecutarse, `install` | `pre_build` | `build` | `post_build`
        - `artifacts` — qué archivos enviar a S3
        - `cache` — qué archivos enviar a S3 para compartir con otras pruebas, por lo general dependencias
- integrations
	- [[SSM Parameter Store]] -- ref values in build project env vars, IAM Role assoc'd 2 CBuild must have permissions 2 access PS
	- [[Secrets Manager]] -- ref values in build project env vars, IAM Role assoc'd 2 CBuild must have permissions 2 access SM
	- troubleshooting
	    - S3 — store logs
	    - [[CloudWatch Logs|CW Logs]]
	    - [[CW Metrics]] — monitor statistics
	    - [[CW Alarms]] — 2 set failure thresholds
	    - [[EventBridge]] — 4 failed builds & notifs