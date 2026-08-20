---
dudas:
tags:
  - security
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 100 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/109246-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- No queremos que se envíen notifs de un entorno a Lambdas de otro
### Situación
A company uses AWS [[Lambda]] functions and an Amazon [[Simple Storage Service|S3]] trigger to process images into an S3 bucket. A development team set up multiple environments in a single AWS account.  
  
After a recent production deployment, the development team observed that the development S3 buckets invoked the production environment Lambda functions. These invocations caused unwanted execution of development S3 files by using production Lambda functions. The development team must prevent these invocations. The team must follow security best practices.  
  
Which solution will meet these requirements?

- A. Update the Lambda execution role for the production Lambda function to add a policy that allows the execution role to read from only the production environment S3 bucket. -- ésta puede ser
- B. Move the development and production environments into separate AWS accounts. Add a resource policy to each Lambda function to allow only S3 buckets that are within the same account to invoke the function. -- no
- C. Add a resource policy to the production Lambda function to allow only the production environment S3 bucket to invoke the function. -- ésta
- D. Move the development and production environments into separate AWS accounts. Update the Lambda execution role for each function to add a policy that allows the execution role to read from the S3 bucket that is within the same account. -- no
### Condiciones
- 

### OPTS
a.

### Análisis
C.
> [!note] Mi respuesta
> 
### Answer
C