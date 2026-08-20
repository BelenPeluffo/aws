---
dudas: false
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 41 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103858-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] Count metric -- ? ✅ 2026-08-06
	[[API Gateway#^0b349c|La cantidad de rqs recibidas]].
### Notas
- 
### Situación
[[API Gateway|API-GW]] exposing [[Lambda]] 4 processing rqs. During testing, GW times out inspite Lambda finishing before set limit.

A developer is building a web application that uses Amazon API Gateway to expose an AWS Lambda function to process requests from clients. During testing, the developer notices that the **API Gateway times out** even though the Lambda function finishes under the set time limit.  
Which of the following API Gateway metrics in Amazon [[CloudWatch]] can help the developer troubleshoot the issue? (Choose two.)

- A. CacheHitCount
- B. IntegrationLatency
- C. CacheMissCount
- D. Latency
- E. Count
### Condiciones
- which TWO [[CW Metrics]] can help troubleshoot

### OPTS
- A. CacheHitCount -- no tiene que ver con el cache
- B. IntegrationLatency -- [[API Gateway#^2a7236]] ^d42099
- C. CacheMissCount -- no tiene que ver con el cache
- D. Latency -- [[API Gateway#^54c760]] ^b42915
- E. Count -- no tiene que ver con la cantidad de rqs

### Análisis
Creo que quizás sea [[API-GW time-out CW metric troubleshooting#^d42099|B]] pero por una cuestión de que creo que es por la latencia y porque probablemente tenga que ver con la integración? Como son 2, elijo por defecto también la [[API-GW time-out CW metric troubleshooting#^b42915|D]].
> [!note] Mi respuesta
> B y D.
### Answer
B y D.