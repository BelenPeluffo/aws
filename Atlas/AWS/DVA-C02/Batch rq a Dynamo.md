---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/#:~:text=16-,Question%20%237,-Topic%201
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
Una app usa `BatchGetItem` contra [[Atlas/AWS/DynamoDB]]. Las respuestas suelen devolver valores en `UnprocessedKeys`.
### Condiciones
¿Cómo puede ==aumentarse la resiliencia== de la app cuando se obtienen valores en esa prop? Seleccionar 2.

### OPTS
a. retry batch inmediatamente -- no, porque puede sobrecargar DB ^b0abaa

b. retry con expo backoff y delay random -- sí, enfoque estándar ^443706

c. upd app para que use una API del [[Atlas/AWS/SDK]] -- podría usarse pero no sirve para ==estabilizar la resiliencia==^70d73c

d. aumentar provisioned read capacity ^f8b84c

e. aumentar provisioned write capacity ^2b536a

### Análisis
[[Batch rq a Dynamo#^443706|b]] no me suena mucho por el random delay. [[Batch rq a Dynamo#^b0abaa|a]] tampoco me convence. Y la [[Batch rq a Dynamo#^2b536a|e]] me parece que definitivamente no es porque la API es GET no POST/PUT.
> [!note] Mi respuesta
>  [[Batch rq a Dynamo#^70d73c|c]] y [[Batch rq a Dynamo#^f8b84c|d]].
### Answer
B y D.