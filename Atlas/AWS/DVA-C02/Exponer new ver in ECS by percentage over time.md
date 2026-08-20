---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 80 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/108735-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿qué diferencia hay entre A y C?
### Notas
- 
### Situación
A company is planning to use AWS [[CodeDeploy]] to deploy an application to Amazon [[Elastic Container Service]] (Amazon [[ECS]]). During the deployment of a new version of the application, the company initially must expose only 10% of live traffic to the new version of the deployed application. Then, after 15 minutes elapse, the company must route all the remaining live traffic to the new version of the deployed application.  
  
Which CodeDeploy predefined configuration will meet these requirements?

- A. CodeDeployDefault.ECSCanary10Percent15Minutes
- B. CodeDeployDefault.[[Lambda]]Canary10Percent5Minutes
- C. CodeDeployDefault.LambdaCanary10Percentl15Minutes
- D. CodeDeployDefault.ECSLinear10PercentEvery1Minutes
### Condiciones
- 

### OPTS
a.

### Análisis
Justamente es Canary, pero no tengo ni idea si es A o C... O sea, como estamos hablando de el tráfico expuesto, entiendo que entonces sería con Lambda y, por lo tanto, sería con C.
> [!note] Mi respuesta
> 
### Answer
A.