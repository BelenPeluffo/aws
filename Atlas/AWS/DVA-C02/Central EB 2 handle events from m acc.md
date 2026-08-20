---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 89 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/111295-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
on-prem -> m API-GW in m acc -> central EB
### Situación
A company is using an Amazon [[API Gateway]] REST API endpoint as a webhook to **publish events from an on-premises source** control management (SCM) system to Amazon [[EventBridge]]. The company has configured an EventBridge rule to listen for the events and to control application deployment in a **central AWS account**. The company needs to receive the same events across multiple receiver AWS accounts.  
  
How can a developer meet these requirements without changing the configuration of the SCM system?

- A. Deploy the API Gateway REST API to all the required AWS accounts. Use the same custom domain name for all the gateway endpoints so that a single SCM webhook can be used for all events from all accounts.
- B. Deploy the API Gateway REST API to all the receiver AWS accounts. Create as many SCM webhooks as the number of AWS accounts. -- hay solo 1 receiver, y es la acc central, ¿o no?
- C. Grant permission to the central AWS account for EventBridge to access the receiver AWS accounts. Add an EventBridge event bus on the receiver AWS accounts as the targets to the existing EventBridge rule. -- again, sólo hay una cuenta con EB que es el central and only receiver, ¿cierto?
- D. Convert the API Gateway type from REST API to HTTP API. -- no
### Condiciones
- 

### OPTS
a.

### Análisis
~~C??~~ A??
> [!note] Mi respuesta
> 
### Answer
C