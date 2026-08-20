---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 54 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103757-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
Retail app migration 2 AWS. session mgmt in memory, this slows down considerably site when high demand. [[Elastic Compute Cloud|EC2]], [[AutoScaling Group]] y [[Elastic Load Balancer|ALB]].
### Condiciones
- qué cambios adicionales hacer para mejorar la performance?

### OPTS
a. EC2 host de DB. user&sess data in said DB.

b. [[ElastiCache]] 4 Memcached 4 user&sess data. [[Relational DB Service|RDS]] 4 app data DB. ^46d8e9

c. EC 4 user, sess & app data

d. EC2 session data. RDS 4 app data.

### Análisis
Pensé en las [[Elastic Load Balancer#^e97dfe|sticky sessions]] pero no serviría porque lo que queremos es GESTIONAR esos datos de user. Las sticky sessions para lo único que sirven es para mantener la sesión del user sin importar a qué EC2 esté siendo redirigidx.
> [!note] Mi respuesta
> [[App slows down 4 handling user-session data in memory#^46d8e9|B]].
### Answer