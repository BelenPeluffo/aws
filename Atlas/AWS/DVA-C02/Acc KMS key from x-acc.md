---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 554 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/157446-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer has an application that runs in AWS Account A. The application must retrieve an AWS [[Secrets Manager]] secret that is encrypted by an AWS Key Management Service (AWS [[Key Management Service|KMS]]) key from AWS Account B. The application’s role **has permissions to access the secret** in Account B.  
  
The developer must add a statement to the KMS key’s key policy to allow the role in Account A to **use the KMS key** in Account B. The permissions must grant least privilege access to the role.  
  
Which permissions will meet these requirements?

- A. kms:Decrypt and kms:DescribeKey
- B. secretsmanager:DescribeSecret and secretsmanager:GetSecretValue -- dice que ya tiene permisos para acceder al secreto
- C. kms:* -- no es least privilege
- D. secretsmanager:* -- ya tenemos esos permisos y además ésto no es least-privilege
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