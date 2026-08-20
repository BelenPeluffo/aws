---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#:~:text=33-,Question%20%2314,-Topic%201
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- PII = personally identifiable information.
### Situación
Financial company. Must store customer data w PII 4 ten years. PII data can only b acc by a few people only. Company wants 2 share data without sharing PII data.

Records saved in [[Simple Storage Service|S3]] as is. [[Lambda]] fx 2 remove PII.
### Condiciones
- how 2 comply with regulations using this stack?

### OPTS
a. S3 notific that invokes lambda when GET.

b. S3 notific that invokes lambda when PUT. -- no, porque sólo queremos que sea de lectura, no escritura.

c. define lambda as S3 Object Lambda acc point. Use this 2 remove PII. -- ésto existe: [[Simple Storage Service#^5fab14|object lambda]]. ^5f20ab

d. define acc point... -- no.

### Análisis

> [!note] Mi respuesta
> [[Access formatted documents#^5f20ab|C]].
### Answer
C.