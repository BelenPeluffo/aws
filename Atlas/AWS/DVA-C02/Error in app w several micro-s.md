---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 138 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/117795-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] X-RAY -- diferencia entre sidecar container y daemonset? (y, por lo tanto, entre A y B)
### Notas
- 
### Situación
Users are reporting errors in an application. The application consists of **several microservices** that are deployed on Amazon [[Elastic Container Service]] (Amazon [[ECS]]) with AWS [[Atlas/AWS/Fargate]].  
  
Which combination of steps should a developer take to fix the errors? (Choose two.)

- A. Deploy AWS [[X-Ray]] as a sidecar container to the microservices. Update the task role policy to allow access to the X-Ray API.
- B. Deploy AWS X-Ray as a daemonset to the Fargate cluster. Update the service role policy to allow access to the X-Ray API. -- creo que ésta es la que centraliza el daemon
- C. Instrument the application by using the AWS X-Ray SDK. Update the application to use the PutXrayTrace API call to communicate with the X-Ray API. -- definitivamente ésta
- D. Instrument the application by using the AWS X-Ray SDK. Update the application to communicate with the X-Ray daemon. -- o ésta?
- E. Instrument the [[Elastic Container Service|ECS]] task to send the stdout and stderr output to Amazon CloudWatch Logs. Update the task role policy to allow the cloudwatch:PullLogs action. -- ésta no, porque para éso estamos usando X-Ray
### Condiciones
- 

### OPTS
a.

### Análisis
Una de las opciones contendrá X-Ray porque dijo "microservices". B y C?
> [!note] Mi respuesta
> 
### Answer
AC