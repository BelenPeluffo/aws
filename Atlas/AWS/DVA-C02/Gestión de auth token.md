---
dudas:
tags:
  - security
  - secrets-storage
aliases:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/#:~:text=1%20%2D%20Exam%20A-,Question%20%231,-Topic%201
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- Tenemos que recordar que KMS es para encriptado, no para guardar secretos.
### Palabras clave
[[Elastic Compute Cloud|EC2]], procesamiento de transacciones. ¿Invalid transa? => Chat sms 2 supp team. Needs acc token 4 auth with chat API.
- Token must be stored & encrypt'd at-rest & in-transit
- accessible from other AWS accs.
- Solution with LEAST mgmt overhead.

### OPTS
a. ^daf020
- [[SSM Parameter Store]]
- [[Key Management Service|KMS]] AWS mg'd key
- r-based policy 4 parameter 4 x-acc accss
- upd EC2 [[Identity and Access Management|IAM]] 4 accss 2 parameter

b. 
- KMS custom key
- [[Atlas/AWS/DynamoDB]] 4 token storage
- upd EC2 IAM 4 accss 2 table & KMS

c. ^8b6da1
- [[Secrets Manager]]
- KMS custom
- r-based 4 secret 4 x-acc
- upd EC2 IAM 4 acc 2 secret

d. ^54ee82
- KMS AWS mg'd
- [[Simple Storage Service|S3]] 4 token storage
- bucket policy 4 x-acc
- upd EC2 IAM 4 acc 2 bucket & KMS

### Análisis
least mgmt overhead => mg'd keys => [[Gestión de auth token#^daf020|a]] ó [[Gestión de auth token#^54ee82|d]]
(porque usar custom keys implica gestionarlas => mgmt overhead)
s3 @-rest encrypt' [[Simple Storage Service#^c09d75|E IN-TRANSIT]] => d

> [!note] Mi respuesta
> D.

### Answer
En examtopics eligieron la [[Gestión de auth token#^8b6da1|c]], pero a mí me parece que por la custom key le agregás overhead innecesario. Y, por lo que ví, S3 tiene opciones para encriptado @-rest e in-transit.

Yo creo que hubiera elegido la c si la key hubiera sido mg'd.