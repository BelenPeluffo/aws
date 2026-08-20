---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 134 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/117334-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿qué diferencia hay entre linear y canary?
### Notas
- 
### Situación
A company is developing a **serverless** application that consists of various AWS [[Lambda]] functions behind Amazon [[API Gateway]] APIs. A developer needs to automate the deployment of Lambda function code. The developer will deploy updated Lambda functions with AWS [[CodeDeploy]]. The deployment must **minimize the exposure of potential errors** to end users. When the application is in production, the application **cannot experience downtime** outside the specified maintenance window.  
  
Which deployment configuration will meet these requirements with the **LEAST deployment time**?

- A. Use the AWS CodeDeploy in-place deployment configuration for the Lambda functions. Shift all traffic immediately after deployment. -- éste tarda mucho, porque crea una réplica
- B. Use the AWS CodeDeploy linear deployment configuration to shift 10% of the traffic every minute.
- C. Use the AWS CodeDeploy all-at-once deployment configuration to shift all traffic to the updated versions immediately. -- no porque no cumple con el zero downtime
- D. Use the AWS CodeDeploy predefined canary deployment configuration to shift 10% of the traffic immediately and shift the remaining traffic after 5 minutes. -- creo que éste porque siempre lo nombran como una buena opción para rollback y demás
### Condiciones
- 

### OPTS
a.

### Análisis
D
> [!note] Mi respuesta
> 
### Answer
D