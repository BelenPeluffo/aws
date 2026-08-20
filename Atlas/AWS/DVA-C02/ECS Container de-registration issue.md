---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: UDEMY
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A junior developer working on [[Elastic Compute Cloud|EC2]] instances terminated a container instance in Amazon Elastic Container Service (Amazon ECS) as per instructions from the team lead. But the container instance continues to appear as a resource in the ECS cluster.

As a Developer Associate, which of the following solutions would you recommend to fix this behavior?

- a. A custom software on the container instance could have failed and resulted in the container hanging in an unhealthy state till restarted again
	- 
- b. The container instance has been terminated with AWS CLI, whereas, for ECS instances, Amazon ECS CLI should be used to avoid any synchronization issues
	- 
- c. You terminated the container instance while it was in STOPPED state, that lead to this synchronization issues
	Correcto.
- d. You terminated the container instance while it was in RUNNING state, that lead to this synchronization issues
	No. Cuando terminás una `RUNNING` se desregistra automáticamente luego de darse de baja.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer
C