---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 31 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103513-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
Data storage in [[Simple Storage Service|S3]]. HTTP 2 store/retrieve objects.
### Condiciones
- encrypt @ rest when `PutObject`
- SSE-S3

### OPTS
a. create key w [[Key Management Service|KMS]]. assign key 2 bucket. -- no, porque usando el SSS-S3 se hace todo éso de forma automática, ¿o no?

b. `x-amz-server-side-encryption` in `PutObject` rq -- [[Simple Storage Service#^16a8e2]] ^7d929d

c. encrypt' key in header of every rq

d. TLS 2 encrypt trafit 2 bucket

### Análisis

> [!note] Mi respuesta
> [[SSE-S3#^7d929d|B]].
### Answer