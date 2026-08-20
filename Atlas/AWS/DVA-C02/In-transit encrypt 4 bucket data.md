---
dudas:
tags:
  - security
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 37 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103850-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
[[Simple Storage Service|S3]] con sensitive data. at-rest encrypt' w [[Key Management Service|KMS]] key.

### Condiciones
- [[in-flight encryption]] & [[at rest encryption]]
- `GetObject` para multiple acc

### OPTS
a. r-based policy on bucket, deny when `aws:SecureTransport=false` -- además, es uno de los casos de uso de [[Simple Storage Service#^919721|las bucket policies]] ^8b844f

b. ídem, allow when ídem -- no debe allow

c. role-based policy. deny when ídem -- sería muy trabajoso y además hay users de otras cuentas y el admin sólo tiene control sobre el bucket de SU cuenta; además, la mejor práctica para gestionar las formas de acceso a los rr en es usar r-based policies

d. r-based policy on KMS when ídem -- ¿por qué en la key?

### Análisis

> [!note] Mi respuesta
> [[In-transit encrypt 4 bucket data#^8b844f|A]].
### Answer
A.