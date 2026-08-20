---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 33 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103664-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
### Notas
- 
### Situación
[[API Gateway|API-GW]] API in us-east-2. SSL/TLS for domain from 3rd party.

### Condiciones
- [[Atlas/AWS/CloudFront]] for custom name
- how 2 set custom domain?

### OPTS
a. import cert into [[Certificate Manager|ACM]] in same R. DNS A record 4 domain.

b. import cert into CloudFront. DNS CNAME record.

c. ACM in same R. DNS CNAME. ^9e0be9

d. ACM in us-east-1. DNS CNAME. ^095f76

### Análisis

> [!note] Mi respuesta
> [[Custom domain w ACM certificate#^9e0be9|C]].
### Answer
[[Custom domain w ACM certificate#^095f76|D]]. CloudForm sólo acepta certificados de la región `us-east-1`.