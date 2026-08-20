---
dudas:
tags:
  - DVA02-7
  - auto-scaling
aliases:
  - ASG
---
### Dudas
- [x] ¿El ASG se puede usar con cualquier servicio?
    
    No. El ASG es un mecanismo de autoscaling específico de [[Elastic Compute Cloud|EC2]]. Otros recursos tienen OTROS mecanismos de autoscaling y no se llaman ASG.
    
### Notas
### Palabras clave
- concept — scales group in/out based on needs & config, can’t go under/over min/max user values when scaling-in/out, free service (u pay 4 EC2 instances underneath), uses [[CW Alarms]] as trigger
- Launch Template — config para dar de alta instancia EC2
- Scaling Policy — dynamic adjustment based on real-time demand based on aggregated group CW metrics, useful metrics: # requests, cpu usage
	- types
		- Target Tracking — set desired metric value 2 sustain
		- Simple/Step — set specific unit amount 2 scale based on metric conditions
		- Schedule — set specific time frame of scaling based on knowledge of use patterns
		- Predictive — scaling = f(forcast = f(historic pattern))
- Cooldown Period — time after scaling activity 2 wait 4 metrics 2 stabilize, avoids creating/deleting instances every second
- Instant Refresh — permite reemplazar progresivamente instancias definidas con template deprecado a instancias con template actualizado