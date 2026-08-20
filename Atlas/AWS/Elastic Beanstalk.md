---
dudas:
tags:
  - DVA02-17
aliases:
---
### Dudas
- [x]  ✅ 2026-08-05
### Notas
### Palabras clave
- concept
- props
	- pay 4 underlying RR
	- manag'd-s
		- AWS -- capacity, balancing, scaling, config
		- user -- code; can still tweak config
			- config tweakin'
				- UI
				- EB `.config` files
				- [[CloudFormation]]
	- components
		- app -- stack
			- deployment
				- modes 4 creation
					- single instance
					- high availability w/ load balancer
				- modes 4 update -- ==para actualizar SIEMPRE se tienen que dar de baja primero las instancias== #test-question 
					- all @ once -- 1. down w/ old ver -> 2. up w/ new ver; costenloss, fastest
					- rolling -- 0. definir batch (% a dar de baja) -> 1. down that %, other % is still up w/ old ver -> 2. up that % w/ new ver -> 4. down next %; costenlos, way slower
						O sea: el batch=cantidad de instancias que se darán de baja al mismo tiempo.
					- rolling w/ extra batches -- 0 -> 0.5 up that % with new ver -> ídem rolling 1 en adelante; ==$ $ 'cause of the extra instances==, slower than rolling
						O sea: el batch=cantidad de instancias que se darán de baja y cantidad de instancias que se darán de alta con anterioridad para evitar correr la app "under-capacity"
						![[Pasted image 20260724170905.png]]
					- immutable -- crea new ASG y deploya ahí -> redirige tráfico a nuevo ASC; ==$ $ $ $ 'cause of DOUBLE capacity==, slowest, lost burst balance
					- blue green -- new env con new ver running // al old, Route 53 to dirigir según % asignado a cada env (weight)
					- traffic splitting -- canary, como blue green pero usando ALB n vez de Route 53, y es mejor porque está todo automatizado, lost burst balance
		- app version
			- code -- accepts almost any language, and if not -> containerize it 'cause it supports Docker
				- dependencies -- can b stored in zip where code is located
			- lifecycle policies -- can hold up 2 1000 versions per app, > 1000 ? => no more deploys; bundle can b deleted or not when instance is deleted
				- criteria
					- time -- # days
					- space -- # de instances
		- env -- RR running "x" app ver, can have multiple envs
			- tiers (aka *types*)
				- web server -- client -> ELB -> ASG -> app, real-time HTTP/S
				- worker -- [[Simple Queue Service|SQS]] q -> ASG -> app, async, on-background
			- cloning -- use same env w/ same config
	- migrations -- dejar de apuntar a un env para apuntar a otro
		- razones
			- [[Atlas/AWS/Elastic Load Balancer]] -- si querés cambiar el type (classic, app, network), procedimiento: 1. crear new env con new LB -> 2. deploy app en new env -> 3. apuntar a nuevo env (CNAME swap, [[Atlas/AWS/Route 53]])
			- [[Relational DB Service|RDS]] -- decouple DB, procedimiento: 1. crear new env sin DB -> 2. crear env var que apunte a DB de old env -> 3. backup de DB -> 4. settear protección de borrado en RDS -> 5. eliminar stack viejo
	- [[Elastic Beanstalk CLI]]
