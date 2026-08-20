---
dudas: true
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 81 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106899-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿Qué permite hacer el [[CloudWatch Agent|CW Agent]]?
### Notas
- 
### Situación
A company hosts a batch processing application on AWS [[Elastic Beanstalk]] with instances that run the most recent version of Amazon Linux. The application sorts and processes large datasets.  
  
In recent weeks, the application's performance has decreased significantly during a peak period for traffic. A developer suspects that the application issues are related to the memory usage. The developer checks the Elastic Beanstalk console and notices that memory usage is not being tracked.  
  
How should the developer gather more information about the application performance issues?

- A. Configure the Amazon CloudWatch agent to push logs to Amazon CloudWatch Logs by using port 443.
- B. Configure the Elastic Beanstalk .ebextensions directory to track the memory usage of the instances.
- C. Configure the Amazon CloudWatch agent to track the memory usage of the instances.
- D. Configure an Amazon CloudWatch dashboard to track the memory usage of the instances.
### Condiciones
- 

### OPTS
a.

### Análisis
Creo que es A porque como underlying tiene [[Elastic Compute Cloud|EC2]] y el EC2 necesita un agente, creo que es A.
> [!note] Mi respuesta
> 
### Answer
C