---
dudas: false
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 519 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/152780-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] [[Amazon Cognito]] -- diferencia entre web ID fed' y SAML-based ID fed'? ✅ 2026-08-11
	SAML es para envs empresariales.
### Notas
- 
### Situación
A developer is writing a mobile application that allows users to view images from an [[Simple Storage Service|S3]] bucket. The users must be able to log in with their Amazon login, as well as supported social media accounts.  
  
How can the developer provide this authentication functionality?

- A. Use Amazon Cognito with web identity federation.
	Es ésta.
- B. Use Amazon Cognito with SAML-based identity federation
	Is this a thing??
- C. Use IAM access keys and secret keys in the application code to allow Get* on the S3 bucket.
	Ya de por sí es mala práctica hardcodear keys.
- D. Use AWS STS AssumeRole in the application code and assume a role with Get* permissions on the S3 bucket.
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