---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 520 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156676-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
An application that is running on Amazon [[Elastic Compute Cloud|EC2]] instances stores data in an Amazon [[Simple Storage Service|S3]] bucket. All the data must be encrypted in transit.  
  
How can a developer ensure that all traffic to the S3 bucket is encrypted?

- A. Install certificates on the EC2 instances.
	Is that even a thing??
- B. Create a private VPC endpoint.
	Éso es para conectar rr privados a rr públicos.
- C. Configure the S3 bucket with server-side encryption with AWS KMS managed encryption keys (SSE-KMS).
	SSE no me sirve porque éso está relacionado a la encrypt' at rest.
- D. Create an S3 bucket policy that denies traffic when the value for the aws:SecureTransport condition key is false.
	Es ésta.
### Condiciones
- 

### OPTS
a.

### Análisis
D
> [!note] Mi respuesta
> 
### Answer
D