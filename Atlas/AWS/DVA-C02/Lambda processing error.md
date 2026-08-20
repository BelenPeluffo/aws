---
dudas:
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 60 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103807-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
An ecommerce company is using an AWS [[Lambda]] function behind Amazon [[API Gateway]] as its application tier. To **process orders during checkout**, the application calls a POST API from the frontend. The POST API invokes the Lambda function asynchronously. In rare situations, the application has not processed orders. **The Lambda application logs show no errors or failures.**  
What should a developer do to solve this problem?

- A. Inspect the frontend logs for API failures. Call the POST API manually by using the requests from the log file.
	-- como se corre asíincrona la Lambda, es probable que no lleguen los errores al FE
- B. Create and inspect the Lambda dead-letter queue. Troubleshoot the failed functions. Reprocess the events. ^7bdd11
- C. Inspect the Lambda logs in Amazon CloudWatch for possible errors. Fix the errors.
	-- ya dijo que los logs no muestran errores
- D. Make sure that caching is disabled for the POST API in API Gateway.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer
[[Lambda processing error#^7bdd11|B]].