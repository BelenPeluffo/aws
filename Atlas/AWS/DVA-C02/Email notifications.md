---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 96 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106946-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is creating a service that uses an Amazon [[Simple Storage Service|S3]] bucket for image uploads. The service will use an AWS [[Lambda]] function to create a thumbnail of each image. Each time an image is uploaded, the service needs to **send an email notification and create the thumbnail**. The developer needs to configure the image processing and email notifications setup.  
  
Which solution will meet these requirements?

- A. Create an Amazon Simple Notification Service (Amazon [[SNS]]) topic. Configure S3 event notifications with a destination of the SNS topic. Subscribe the Lambda function to the SNS topic. Create an email notification subscription to the SNS topic.
- B. Create an Amazon Simple Notification Service (Amazon SNS) topic. Configure S3 event notifications with a destination of the SNS topic. Subscribe the Lambda function to the SNS topic. Create an Amazon [[Simple Queue Service]] (Amazon [[SQS]]) queue. Subscribe the [[Simple Queue Service|SQS]] queue to the SNS topic. Create an email notification subscription to the [[Simple Queue Service|SQS]] queue.
- C. Create an Amazon [[Simple Queue Service]] (Amazon [[Simple Queue Service|SQS]]) queue. Configure S3 event notifications with a destination of the [[Simple Queue Service|SQS]] queue. Subscribe the Lambda function to the [[Simple Queue Service|SQS]] queue. Create an email notification subscription to the [[Simple Queue Service|SQS]] queue.
- D. Create an Amazon [[Simple Queue Service]] (Amazon [[Simple Queue Service|SQS]]) queue. Send S3 event notifications to Amazon [[EventBridge]]. Create an EventBridge rule that runs the Lambda function when images are uploaded to the S3 bucket. Create an EventBridge rule that sends notifications to the [[Simple Queue Service|SQS]] queue. Create an email notification subscription to the [[Simple Queue Service|SQS]] queue.
### Condiciones
- 

### OPTS
a.

### Análisis
Yo eligiría [[Simple Email Service|SES]], pero como no hay, tendremos que ir con [[SNS]]. A es posible? B es rebuscada.
> [!note] Mi respuesta
> 
### Answer
A