---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 536 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156696-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] Diferencia entre [[Simple Queue Service|SQS]] y SNS a la hora de mandar sms
### Notas
- 
### Situación
A developer is creating a stock trading application. The developer needs a solution to send text messages to application users to confirmation when a trade has been completed.  
  
The solution must deliver messages in the order a user makes stock trades. The solution must not send duplicate messages.  
  
Which solution will meet these requirements?

- A. Configure the application to publish messages to an Amazon Data Firehose delivery stream. Configure the delivery stream to have a destination of each user’s mobile phone number that is passed in the trade confirmation message.
	Is this even a thing?
- B. Create an Amazon [[Simple Queue Service]] (Amazon [[Simple Queue Service|SQS]]) FIFO queue. Use the SendMessageIn API call to send the trade confirmation messages to the queue. Use the SendMessageOut API to send the messages to users by using the information provided in the trade confirmation message.
	[[SQS]] es un push-s, así que no va a enviar ni mielda nada.
- C. Configure a pipe in Amazon EventBridge Pipes. Connect the application to the pipe as a source. Configure the pipe to use each user’s mobile phone number as a target. Configure the pipe to send incoming events to the users.
	Is this even a thing??
- D. Create an Amazon Simple Notification Service (SNS) FIFO topic. Configure the application to use the AWS SDK to publish notifications to the SNS topic to send SMS messages to the users.
	Para mí es ésta porque [[SNS]] se encarga de las notificaciones.
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