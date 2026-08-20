---
dudas: true
tags:
  - DVA02-6
aliases:
  - EC2
---
### Dudas
- [ ] Control de tráfico — ¿a qué niveles se puede hacer? Security groups es para EC2, ¿NACL para donde? ¿Era para a nivel de red o de VPN? Repasar qué contiene a qué.
    
    R > AZ, R = VPC
    
    VPC > subnets, 1 VPC → M subnets,
    
    AZ = subnet
    
    VPC = SG
    
    ![[Pasted image 20260721121135.png]]
    
- [x] SSH v. EC2 Instance Connect — ¿la diferencia era que con IC no tenés que usar SSH?
    
    La diferencia está en que facilita el acceso al SO de la instancia, pero IC usa SSH por debajo.
    
- [x] EC2 User Data #test-question
    
    Script con comandos a ejecutar antes de levantar la instancia, para instalar/descargar/actualizar lo que ésta necesite para que lo que contenga funcione sin problemas. ^14430b
### Notas
### Palabras clave
- User Data — bootstrapping commands, runs once when first launched by default (can b changed, tho), scripts run as root by default (can b changed, tho) #test-question
- Instance Connect — conexión por SSH mediante consola en navegador
- types
    - memory optimized — in-memory
    - compute optimized — hpc/hcp
    - storage optimized — OLTP (online transaction processing) db, a lot of O/I requests
- purchasing opts
    - dedicated hosts — software license, compliance reqs, dedicated servers, hardware info
- Security groups — EC2, IN/OUT, only `allow`, source: IG/otro SG, M SG → M EC2, scope: VPC
- storage options
	- data storage
		- [[Elastic Block Store]] vol, [[Elastic Block Store#^ebs-snapshots|snapshots]] -- permanent, network conn
		- [[EC2 Instance Storage]] -- ephemeral, faster, physical conn
		- [[Elastic File System]]
	- boot & init storage -- [[Amazon Machine Image]], EBS
- EC2 instance metadata (IMDS) EP — NO need 4 AWS CLI or SDK → str8 from any CLI, `169.254.169.254/latest/metadata` → access 2 instance meta-dir, accessor 2 BOTH user/meta data, contains: role name & public/private IP & launch script (userdata) & role creds, this is how AWS accesses EC2 creds
    - v1 — straight forward: curl the URL
    - v2 — secure: get a session token AND THEN curl the URL with token in request `X-aws-ec2-metadata-token` header
- Image Builder
- Elastic Network Adapter (ENA) -- para alto rendimiento de red