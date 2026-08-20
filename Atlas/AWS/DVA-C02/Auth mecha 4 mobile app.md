---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 546 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/154507-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is building the **authentication** mechanism for a new **mobile app**. Users need to be able to sign up, sign in, and access secured backend AWS resources.  
  
Which solution will meet these requirements?

- A. Use AWS Identity and Access Management Access Analyzer to generate [[Identity and Access Management|IAM]] policies. Create an IAM role. Attach the policies to the role. Integrate the IAM role with an identity provider that the mobile app uses.
- B. Create an IAM policy that grants access to the backend resources. Create an IAM role. Attach the policy to the role. Create an Amazon API Gateway endpoint. Attach the role to the endpoint. Integrate the endpoint with the mobile app.
- C. Create an Amazon [[Amazon Cognito]] identity pool. Configure permissions by choosing a default IAM role for authenticated users or guest users in the identity pool. Associate the identity pool with an identity provider. Integrate the identity pool with the mobile app.
- D. Create an Amazon Cognito user pool. Configure the security requirements by choosing a password policy, multi-factor authentication (MFA) requirements, and user account recovery options. Create an app client. Integrate the app client with the mobile app.
### Condiciones
- 

### OPTS
a.

### Análisis
D, porque [[Amazon Cognito#^CUP]] es para login.
> [!note] Mi respuesta
> 
### Answer
D