---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 25 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103510-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
Migración on-prem -> [[Relational DB Service|RDS]]. Read-heavy wl.
### Condiciones
- optimize read queries perf
- least current/future effort

### OPTS
a. multi-AZ RDS deploy. increase # conn/increase pool size -- high-availability & failover but no better perfo

b. multi-AZ RDS deploy. modify code 2 acc secondary instance. -- mucho cambio de código

c. RDS read-replicas deploy. modify code 2 query read-replicas. ^dcc512

d. (I will not dignify that answer w a question)

### Análisis

> [!note] Mi respuesta
> Para mí, es la [[Better RDS query performance#^dcc512|C]] porque justamente para éso están las read-replicas.
### Answer
C.