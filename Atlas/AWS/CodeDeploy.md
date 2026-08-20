---
dudas:
tags:
  - DVA02-24
aliases:
---
### Dudas
- [x] CDeploy — ¿el in-place deployment sólo se realiza HalfAtATime o puede ser cualquiera de los deployments? ¿qué diferencia existe entre in-place, blue/green y los gradientes de deploys? — ~~ampliar~~
    
    In-Place y blue/green son las estrategias macro. Las graduales son como sub-estrategias que se pueden aplicar a los despliegues in-place o blue/green.
    
- [x] CDeploy — ¿por qué el agent necesita acceder al code revision del bucket? ¿para qué lo usa? — ~~ampliar~~
    
    En este caso, “revisión” significa simplemente “versión del código a deployar”.
    
- [x] CDeploy — ¿a qué se refiere en este contexto al “deployment strategy”? — ~~ampliar~~
    
    A si va a ser in-place o blue/green.
    
- [x] CDeploy — ¿al deployar a EC2 sin ASG sólo se puede realizar in-place deployment? — ~~ampliar~~
    
    Puede realizarse blue/green pero habría que hacerlo manualmente.
    
    Para aprovechar la automatización del blue/green es mejor tener ASG.
### Notas
### Palabras clave
- concepto — deploy a server ([[Elastic Compute Cloud|EC2]], on-prem, [[ECS]], [[Lambda]]), opción “serverles”: [[Elastic Beanstalk]], autorollback
- elements
	- `appspec.yml` — deploy instruction
		- deploy (general) strategy
			- in-place -- se detiene la aplicación -> se la actualiza -> se levanta de nuevo => tiempo de inactividad
			- blue/green — en base a un ASG, se crea un ASG con el mismo # de instancias con la nueva versión de código y luego el ALB pasa a apuntar al nuevo ASG
		- deploy tactics
			- AllAtOne — mayor downtime
			- HalfAtATime
			- OneAtATime — deploy + lento, menor impacto en availability
			- Custom
	- CDeploy agente — 4 EC2/on-prem, installation can be auto’d w/ Sys Manager, EC2 needs permissions 2 read bucket where code revision lies
- on Lambda — auto weighted alias shift
- on [[Elastic Container Service|ECS]] — only blue/green, hace el pasaje weighted (linear, canary, all at once)
- stages
	1. `ApplicationStop`
	2. `DownloadBundle`
	3. `BeforeInstall`
	4. `Install`
	5. `AfterInstall`
	6. `ApplicationStart`
	7. `ValidateService`