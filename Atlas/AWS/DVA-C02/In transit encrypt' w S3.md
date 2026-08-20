---
dudas:
tags:
  - security
  - aws-SecureTransport
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 110 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107013-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company is providing read access to objects in an Amazon [[Simple Storage Service|S3]] bucket for different customers. The company uses [[Identity and Access Management|IAM]] permissions to restrict access to the S3 bucket. The customers can access only their own files.  
  
Due to a regulation requirement, the company needs to enforce encryption in transit for interactions with Amazon S3.  
  
Which solution will meet these requirements?

- A. Add a bucket policy to the S3 bucket to deny S3 actions when the aws:SecureTransport condition is equal to false.
- B. Add a bucket policy to the S3 bucket to deny S3 actions when the s3:x-amz-acl condition is equal to public-read.
- C. Add an IAM policy to the IAM users to enforce the usage of the AWS SDK.
- D. Add an IAM policy to the IAM users that allows S3 actions when the s3:x-amz-acl condition is equal to bucket-owner-read.
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