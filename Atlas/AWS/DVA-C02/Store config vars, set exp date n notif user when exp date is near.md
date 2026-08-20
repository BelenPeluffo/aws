---
dudas: true
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 133 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/117335-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿difgerencia entre parámetro standard y advanced?
- [ ] Set Expiration and ExpirationNotification policy types. -- is that a thing??
### Notas
- 
### Situación
A developer needs to store **configuration variables** for an application. The developer needs to set an **expiration date and time for the configuration**. The developer wants to receive notifications before the configuration expires.  
  
Which solution will meet these requirements with the **LEAST operational overhead**?

- A. Create a standard parameter in AWS Systems Manager [[SSM Parameter Store]]. Set Expiration and ExpirationNotification policy types. -- is that a thing??
- B. Create a standard parameter in AWS Systems Manager Parameter Store. Create an AWS Lambda function to expire the configuration and to send Amazon Simple Notification Service (Amazon SNS) notifications.
- C. Create an advanced parameter in AWS Systems Manager Parameter Store. Set Expiration and ExpirationNotification policy types.
- D. Create an advanced parameter in AWS Systems Manager Parameter Store. Create an Amazon EC2 instance with a cron job to expire the configuration and to send notifications.
### Condiciones
- 

### OPTS
a.

### Análisis
Para mí es B porque A es como ??? y C y D me parece que son innecesarios por el "advanced".
> [!note] Mi respuesta
> 
### Answer
C