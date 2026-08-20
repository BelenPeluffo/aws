---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 544 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156700-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] Repasar lo del Lambda Function
### Notas
- 
### Situación
A company stores customer credit reports in an Amazon [[Simple Storage Service|S3]] bucket. An analytics service uses standard Amazon S3 GET requests to access the reports.  
  
A developer must implement a solution to redact personally identifiable information (PII) from the reports before the reports reach the analytics service.  
  
Which solution will meet this requirement with the **MOST operational efficiency**?

- A. Load the S3 objects into Amazon Redshift by using a COPY command. Implement dynamic data masking. Refactor the analytics service to read from Amazon Redshift.
- B. Set up an S3 Object Lambda function. Attach the function to an S3 Object Lambda Access Point. Program the function to call a PII redaction API.
- C. Use AWS Key Management Service (AWS KMS) to implement encryption in the S3 bucket. Re-upload all the existing S3 objects. Give the kms:Decrypt permission to the analytics service.
- D. Create an Amazon Simple Notification Service (Amazon SNS) topic. Implement message data protection. Refactor the analytics service to publish data access requests to the SNS topic.
### Condiciones
- 

### OPTS
a.

### Análisis
B
> [!note] Mi respuesta
> 
### Answer
B