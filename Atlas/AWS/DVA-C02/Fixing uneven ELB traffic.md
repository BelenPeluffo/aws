---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: UDEMY
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer from your team has configured the load balancer to route traffic equally between instances or across Availability Zones. However, Elastic Load Balancing (ELB) routes more traffic to one instance or Availability Zone than the others.

Why is this happening and how can it be fixed? (Select two)

- a. Instances of a specific capacity type aren’t equally distributed across Availability Zones
	Correct.
	El tráfico que dirige ELB también se calcula en función de la capacidad de cada instancia. Instancias con menos capacidad, recibirán menor porcentaje de tráfico que otras con mayor capacidad.
- b. For Application Load Balancers, cross-zone load balancing is disabled by default
	Always enabled.
- c. There could be short-lived TCP connections between clients and instances
	- ?
- d. After you disable an Availability Zone, the targets in that Availability Zone remain registered with the load balancer, thereby receiving random bursts of traffic
	They r still registered but ELB won't send traffic their way.
- e. Sticky sessions are enabled for the load balancer
	Correct.
### Condiciones
- 

### OPTS
a.

### Análisis
E
> [!note] Mi respuesta
> 
### Answer
AE