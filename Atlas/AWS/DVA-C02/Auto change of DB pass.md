---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 135 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/117333-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company created four AWS [[Lambda]] functions that connect to a relational database server that runs on an Amazon [[Relational DB Service|RDS]] instance. A security team requires the company to **automatically change the database password every 30 days**.  
  
Which solution will meet these requirements **MOST securely**?

- A. Store the database credentials in the environment variables of the Lambda function. Deploy the Lambda function with the new credentials every 30 days.
- B. Store the database credentials in AWS Secrets Manager. Configure a 30-day rotation schedule for the credentials.
- C. Store the database credentials in AWS Systems Manager Parameter Store secure strings. Configure a 30-day schedule for the secure strings.
- D. Store the database credentials in an Amazon S3 bucket that uses server-side encryption with customer-provided encryption keys (SSE-C). Configure a 30-day key rotation schedule for the customer key.
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