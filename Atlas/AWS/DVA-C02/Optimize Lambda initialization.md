---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 521 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/153503-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company is hosting an Amazon [[API Gateway]] REST API that calls a single AWS [[Lambda]] function. The function is infrequently invoked by multiple clients at the same time.  
  
The code performance is optimal, but the company wants to optimize the startup time of the function  
  
What can a developer do to optimize the initialization of the function?

- A. Enable API Gateway caching for the REST API.
	Como son varios AL MISMO tiempo, yo diría que ésta es la mejor opción.
- B. Configure provisioned concurrency for the Lambda function.
	Si es *infrequently invoked*, sería costoso ésto. Pero me tienta lo de *optimizar la inicialización*... porque la concurrencia provisionada funciona justo para ésto.
- C. Use Lambda proxy integration for the REST API
	¿Sirve para algo ésto? Me parece que no.
- D. Configure AWS Global Accelerator for the Lambda function.
### Condiciones
- 

### OPTS
a.

### Análisis
Como no me está pidiendo que ahorre en costos ni que tampoco sea cost-efficient, yo voy por la B porque la provisioned concurrency es justamente para éso.
> [!note] Mi respuesta
> 
### Answer
B