---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 539 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/157497-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company uses two AWS accounts: production and development. The company stores data in an Amazon [[Simple Storage Service|S3]] bucket that is in the production account. The data is encrypted with an AWS Key Management Service (AWS [[Key Management Service|KMS]]) customer managed key. The company plans to copy the data to another S3 bucket that is in the development account.  
  
A developer needs to use a KMS key to encrypt the data in the S3 bucket that is in the development account. The KMS key in the development account must be accessible from the production account,  
  
Which solution will meet these requirements?

- A. Replicate the customer managed KMS key from the production account to the development account. Specify the production account in the key policy.
- B. Create a new customer managed KMS key in the development account. Specify the production account in the key policy.
- C. Create a new AWS managed KMS key for Amazon S3 in the development account. Specify the production account in the key policy.
- D. Replicate the default AWS managed KMS key for Amazon S3 from the production account to the development account. Specify the production account in the key policy.
### Condiciones
- 

### OPTS
a.

### Análisis
Supongo que querrán que sea customer mg'd? En ese caso, A o B, clearly. A, porque replica.
> [!note] Mi respuesta
> 
### Answer
B.