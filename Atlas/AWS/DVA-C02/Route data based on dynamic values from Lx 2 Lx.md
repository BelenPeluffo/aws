---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 547 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/157499-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿qué diferencia hay entre B, C y D?
### Notas
-- data --> Lambda -- data' --> Lambda(field value)
### Situación
A developer is designing an **event-driven** architecture. An AWS [[Lambda]] function that processes data needs to ==push== processed data to a subset of four consumer Lambda functions. The data must be routed based on the value of one field in the data.  
  
Which solution will meet these requirements with the **LEAST operational overhead**?

- A. Create an Amazon [[Simple Queue Service]] (Amazon [[Simple Queue Service|SQS]]) queue and event source mapping for each consumer Lambda function. Add message routing logic to the data-processing Lambda function. -- creo que no, porque es event driven y con [[Simple Queue Service|SQS]] las Lambdas tendrían que hacer pull por lo que deberían ser scheduled, creo
- B. Create an Amazon Simple Notification Service (Amazon SNS) topic. Subscribe the four consumer Lambda functions to the topic. Add message filtering logic to each consumer Lambda function. Subscribe the data-processing Lambda function to the SNS topic.
- C. Create a separate Amazon Simple Notification Service (Amazon SNS) topic and subscription for each consumer Lambda function. Add message routing logic to the data-processing Lambda function to publish to the appropriate topic.
- D. Create a single Amazon Simple Notification Service (Amazon SNS) topic. Subscribe the four consumer Lambda functions to the topic. Add SNS subscription filter policies to each subscription. Configure the data-processing Lambda function to publish to the topic.
### Condiciones
- 

### OPTS
a.

### Análisis
D
> [!note] Mi respuesta
> 
### Answer