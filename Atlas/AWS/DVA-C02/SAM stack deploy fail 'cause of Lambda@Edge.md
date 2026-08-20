---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 125 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107062-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is creating an AWS Serverless Application Model (AWS [[Serverless App Model|SAM]]) template. The AWS SAM template contains the definition of multiple AWS [[Lambda]] functions, an Amazon [[Simple Storage Service|S3]] bucket, and an Amazon [[CloudFront]] distribution. One of the Lambda functions runs on [[Lambda#^8f52e7|Lambda@Edge]] in the CloudFront distribution. The S3 bucket is configured as an origin for the CloudFront distribution.  
  
When the developer deploys the AWS SAM template in the eu-west-1 Region, the creation of the stack fails.  
  
Which of the following could be the reason for this issue?

- A. CloudFront distributions can be created only in the us-east-1 Region.
- B. Lambda@Edge functions can be created only in the us-east-1 Region.
- C. A single AWS SAM template cannot contain multiple Lambda functions.
- D. The CloudFront distribution and the S3 bucket cannot be created in the same Region.
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