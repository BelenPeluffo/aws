---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 129 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/112424-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is creating an AWS [[Lambda]] function. The Lambda function will consume messages from an Amazon [[Simple Queue Service]] (Amazon [[SQS]]) queue. The developer wants to integrate unit testing as part of the function's continuous integration and continuous delivery (CI/CD) process.  
  
How can the developer unit test the function?

- A. Create an AWS CloudFormation template that creates an [[Simple Queue Service|SQS]] queue and deploys the Lambda function. Create a stack from the template during the CI/CD process. Invoke the deployed function. Verify the output.
- B. Create an [[Simple Queue Service|SQS]] event for tests. Use a test that consumes messages from the [[Simple Queue Service|SQS]] queue during the function's Cl/CD process. -- ???
- C. Create an [[Simple Queue Service|SQS]] queue for tests. Use this [[Simple Queue Service|SQS]] queue in the application's unit test. Run the unit tests during the CI/CD process.
- D. Use the aws lambda invoke command with a test event during the CIICD process.
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