---
dudas:
tags:
aliases:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/#:~:text=5%25-,Question%20%235,-Topic%201
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
[[Lambda]] que se triggerea por [[Simple Storage Service|S3 notifications]] para escribir en [[Atlas/AWS/DynamoDB]]. Por alguna razón, devuelve error al querer escribir en la tabla.
### Condiciones
¿Qué podría estar generando el error?

### OPTS
a. Lambda alcanzó su límite. -- si fuera así, no se ejecutaría o fallaría en todas las ejecuciones; daría error `TooManyRequestsException`

b. DynamoDB requiere secondary index. -- imposible

c. Lambda no tiene permisos [[Identity and Access Management|IAM]] para escribir en la tabla. ^c07370

d. La tabla no está en la misma AZ. -- imposible

### Análisis

> [!note] Mi respuesta
> [[Lambda writes in Dynamo#^c07370|C]].
### Answer
C.