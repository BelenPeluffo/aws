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
You are responsible for an application that runs on multiple Amazon [[Elastic Compute Cloud|EC2]] instances. In front of the instances is an Internet-facing load balancer that takes requests from clients over the internet and distributes them to the EC2 instances. A health check is configured to ping the index.html page found in the root directory for the health status. When accessing the website via the internet visitors of the website receive timeout errors.

What should be checked first to resolve the issue?

- A. The ALB is warming up
	- 
- b. IAM Roles
	Éste devuelve error de auth.
- c. The application is down
	No devuelve exclusivamente el timeout error. Dependiendo de cómo esté configurada la app, quizás puede enviar otro tipo de error. Sí es cierto que es posible que este escenario devuelva timeout error, tho. PERO en la consigna dice *what should b checked FIRST*. Lo primero a checkear es el security group.
- d. Security Groups
	Es ésta.
### Condiciones
- 

### OPTS
a.

### Análisis
C
> [!note] Mi respuesta
> 
### Answer
D