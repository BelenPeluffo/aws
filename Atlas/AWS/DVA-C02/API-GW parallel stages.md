---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 21 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/102899-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
[[API Gateway|API-GW]] REST. API usage thru FE UI & [[Amazon Cognito]] auth. New app ver has new EPs and backward incompatibility.
### Condiciones
- allow acc 2 other devs w/o affecting customers
- lest op overhead

### OPTS
a. def dev stage in GW. tell devs 2 point EPs 2 dev stage -- después de la [[API-GW parallel stages#^be6b45|c]] ésta es la segunda mejor

b. new GW 2 point 2 new API code. tell devs 2 point 2 new GW. -- no, porque implica recrear todos los EPs que ya existían además de agregar los nuevos

c. implement qp in API code 2 determine which ver 2 use -- no es una buena idea porque tenés que tocar código ^be6b45

d. (not going 2 dignify that answer w a quotation)

### Análisis
Las dos primeras me parece que son un montón. Así que me decanto por la [[API-GW parallel stages#^be6b45|c]].
> [!note] Mi respuesta
> C.
### Answer
A.