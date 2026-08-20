---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 523 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156021-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] This fucking specifics -- STS Region-wise?? what about it?? ✅ 2026-08-11
	[[Security Token Service#^98fa6e|STS EPs]]
### Notas
- 
### Situación
A developer has an application that uses AWS Security Token Service (AWS [[Security Token Service|STS]]). The application calls the STS AssumeRole API operation to provide trusted users with temporary security credentials. The application calls AWS STS at the service's default endpoint: https://sts.amazonaws.com.  
  
The application is deployed in an Asia Pacific AWS Region. The application is experiencing errors that are related to intermittent latency when the application calls AWS STS.  
  
What should the developer do to resolve this issue?

- A. Update the application to use the GetSessionToken API operation.
- B. Update the application to use the AssumeRoleWithSAML API operation.
- C. Update the application to use a Regional STS endpoint that is closer to the application deployment.
- D. Update the application to use the AssumeRoleWithWebldentity API operation. Move the STS endpoint to a global endpoint.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer
C