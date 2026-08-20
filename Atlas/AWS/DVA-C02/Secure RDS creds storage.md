---
dudas:
tags:
  - security
  - auto-rotation
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 48 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103918-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] [[Secrets Manager]] -- secret type?? qué es, qué tipos acepta y cómo entra en juego en la integración con [[Lambda]]? dónde se define?
	- [[Secrets Manager#^2fb160|Tipos]].
	- Lambda simplemente tiene que hacer rq a Secrets Manager y obtener las creds.
	- Se define al momento de la creación a través de la consola.
### Notas
- 
### Situación
[[Lambda]] needs ==creds 2 conn 2 [[Relational DB Service|RDS]]==. Curently creds stored in [[Simple Storage Service|S3]]

### Condiciones
- creds rotation & sec storage
- soluc should b integratable w Lambda

### OPTS
a. creds in [[SSM Parameter Store]]. [[Key Management Service|KMS]] 2 encrypt. Auto-rotation of param. Use param in Lambda.

b. (wont' dignify answer w a q)

c. creds in [[Secrets Manager]]. Secret type=[[Secrets Manager#^109370|Creds 4 RDS]]. KMS 4 encrypt' ^3cce39

d. (won't)

### Análisis

> [!note] Mi respuesta
> [[Secure RDS creds storage#^3cce39|C]], aunque está medio rara...
### Answer
C.