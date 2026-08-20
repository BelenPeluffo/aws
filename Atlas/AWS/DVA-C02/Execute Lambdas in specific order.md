---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 528 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/152779-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is building an ecommerce application that uses multiple AWS [[Lambda]] functions. Each function performs a specific step in a customer order workflow, such as order processing and inventory management.  
  
The developer must ensure that the Lambda functions run in a specific order.  
  
Which solution will meet this requirement with the LEAST operational overhead?

- A. Configure an Amazon [[Simple Queue Service]] (Amazon [[SQS]]) queue to contain messages about each step a function must perform. Configure the Lambda functions to run sequentially based on the order of messages in the [[Simple Queue Service|SQS]] queue.
- B. Configure an Amazon Simple Notification Service (Amazon [[SNS]]) topic to contain notifications about each step a function must perform. Subscribe the Lambda functions to the SNS topic. Use subscription filters based on the step each function must perform.
- C. Configure an AWS [[Step Functions]] state machine to invoke the Lambda functions in a specific order.
- D. Configure Amazon [[EventBridge]] Scheduler schedules to invoke the Lambda functions in a specific order.
### Condiciones
- 

### OPTS
a.

### Análisis
C
> [!note] Mi respuesta
> 
### Answer
C