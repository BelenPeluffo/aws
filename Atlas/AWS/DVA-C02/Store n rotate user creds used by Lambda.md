---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 121 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107055-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company's developer is building a static website to be deployed in Amazon [[Simple Storage Service|S3]] for a production environment. The website integrates with an Amazon [[Amazon Aurora|Aurora]] PostgreSQL database by using an AWS [[Lambda]] function. The website that is deployed to production will use a Lambda alias that points to a specific version of the Lambda function.  
  
The company must rotate the database credentials every 2 weeks. Lambda functions that the company deployed previously must be able to use the most recent credentials.  
  
Which solution will meet these requirements?

- A. Store the database credentials in AWS [[Secrets Manager]]. Turn on rotation. Write code in the Lambda function to retrieve the credentials from Secrets Manager.
- B. Include the database credentials as part of the Lambda function code. Update the credentials periodically and deploy the new Lambda function.
- C. Use Lambda environment variables. Update the environment variables when new credentials are available.
- D. Store the database credentials in AWS Systems Manager [[SSM Parameter Store]]. Turn on rotation. Write code in the Lambda function to retrieve the credentials from Systems Manager Parameter Store.
### Condiciones
- 

### OPTS
a.

### Análisis
A, porque SM fue creado para éso
> [!note] Mi respuesta
> 
### Answer
A