---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 538 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156029-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company generates SSL certificates from a third-party provider. The company imports the certificates into AWS Certificate Manager ([[Certificate Manager|ACM]]) to use with public web applications.  
  
A developer must implement a solution to notify the company’s security team 90 days before an imported certificate expires. The company already has configured an Amazon [[Simple Queue Service]] (Amazon [[SQS]]) queue. The company also has configured an Amazon Simple Notification Service (Amazon [[SNS]]) topic that has the security team’s email address as a subscriber.  
  
Which solution will provide the security team with the required notification about certificates?

- A. Create an Amazon [[EventBridge]] rule that specifies the ACM Certificate Approaching Expiration event type. Set the SNS topic as the EventBridge rule’s target.
- B. Create an AWS Lambda function to search for all certificates that are expiring within 90 days. Program the Lambda function to send each identified certificate’s Amazon Resource Name (ARN) in a message to the [[Simple Queue Service|SQS]] queue. -- creo que [[Simple Queue Service|SQS]] no es útil
- C. Create an AWS Step Functions workflow that is invoked by each certificate’s expiration notification from AWS CloudTrail. Create an AWS Lambda function to send each certificate's Amazon Resource Name (ARN) in a message to the [[Simple Queue Service|SQS]] queue. -- CloudTrail???
- D. Configure AWS Config with the acm-certificate-expiration-check managed rule to run every 24 hours. Create an Amazon EventBridge rule that includes an event pattern that specifies the Config Rules Compliance Change detail type and the configured rule. Set the SNS topic as the EventBridge rule’s target. -- won't dignify this answer w a question
### Condiciones
- 

### OPTS
a.

### Análisis
A
> [!note] Mi respuesta
> 
### Answer
A