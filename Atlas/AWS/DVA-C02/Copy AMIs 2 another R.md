---
dudas: true
tags:
aliases:
incorrecta: true
---

Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 27 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/102901-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿Para qué se usa exactamente [[Certificate Manager]] y cómo se articula con los ss que usan [[in-flight encryption]]?
- [x] ¿existe el encryption by default?
	No.
### Notas
- 
### Situación
Run app in m-R. What will b done: src [[Amazon Machine Image|AMI]] copied 2 new R. Not all AMIs encrypt'd.

### Condiciones
- AMIs must b encrypt'd

### OPTS
a. create new encrypt'd AMIs. copy them into new R. delete unencrypt'd AMIs. ^009ab6

b. use [[Key Management Service|KMS]] 2 encrypt unpencrypt'd. copy encrypt'd 2 R. -- no se puede porque [[Amazon Machine Image#^7a3967|el encriptado se define al momento de creación]], no se lo puede editar. ^351a9b

c. [[Certificate Manager]] 2 encrypt unencrypt'd. ídem. -- no, porque ACM es para gestionar certificados SSL/TLS, no para encriptar

d. copy 2 R. enable encrypt' by default in new R. -- no existe el encriptado por defecto
### Análisis

> [!note] Mi respuesta
> [[Copy AMIs 2 another R#^351a9b|B]].
### Answer
[[Copy AMIs 2 another R#^009ab6|A]].