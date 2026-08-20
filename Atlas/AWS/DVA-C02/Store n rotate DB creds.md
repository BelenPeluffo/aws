---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 118 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107052-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is writing an application for a company. The application will be deployed on Amazon [[Elastic Compute Cloud|EC2]] and will use an Amazon [[Relational DB Service|RDS]] for Microsoft SQL Server database. The company's security team requires that **database credentials are rotated at least weekly**.  
  
How should the developer configure the database credentials for this application?

- A. Create a database user. Store the user name and password in an AWS Systems Manager [[SSM Parameter Store]] secure string parameter. Enable rotation of the AWS Key Management Service (AWS [[Key Management Service|KMS]]) key that is used to encrypt the parameter.
- B. Enable [[Identity and Access Management|IAM]] authentication for the database. Create a database user for use with IAM authentication. Enable password rotation.
- C. Create a database user. Store the user name and password in an AWS [[Secrets Manager]] secret that has daily rotation enabled.
- D. Use the EC2 user data to create a database user. Provide the user name and password in environment variables to the application.
### Condiciones
- 

### OPTS
a.

### Análisis
C, porque literalmente para este caso de uso está hecho
> [!note] Mi respuesta
> 
### Answer