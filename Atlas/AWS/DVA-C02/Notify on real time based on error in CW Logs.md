---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 73 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106708-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company runs an application on AWS. The company deployed the application on Amazon [[Elastic Compute Cloud|EC2]] instances. The application stores data on Amazon [[Amazon Aurora|Aurora]]. 
  
The application recently logged multiple **application-specific custom DECRYP_ERROR errors** to Amazon [[CloudWatch Logs]]. The company did not detect the issue until the automated tests that run every 30 minutes failed. A developer must implement a solution that will monitor for the custom errors and **alert a development team in real time** when these errors occur in the production environment.  
  
Which solution will meet these requirements with the **LEAST operational overhead**?

- A. Configure the application to create a custom metric and to push the metric to CloudWatch. Create an AWS [[CloudTrail]] alarm. Configure the CloudTrail alarm to use an Amazon Simple Notification Service (Amazon SNS) topic to send notifications. -- CTrail es para logs de auditoría
- B. Create an AWS [[Lambda]] function to run every 5 minutes to scan the CloudWatch logs for the keyword DECRYP_ERROR. Configure the Lambda function to use Amazon Simple Notification Service (Amazon [[SNS]]) to send a notification.
- C. Use Amazon CloudWatch Logs to create a metric filter that has a filter pattern for DECRYP_ERROR. Create a [[CloudWatch Alarms]] on this metric for a threshold >=1. Configure the alarm to send Amazon Simple Notification Service (Amazon SNS) notifications. ^b8e2d6
- D. Install the CloudWatch unified agent on the EC2 instance. Configure the application to generate a metric for the keyword DECRYP_ERROR errors. Configure the agent to send Amazon Simple Notification Service (Amazon SNS) notifications.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> [[Notify on real time based on error in CW Logs#^b8e2d6|C]].
### Answer