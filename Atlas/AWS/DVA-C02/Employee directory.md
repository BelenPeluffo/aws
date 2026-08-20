---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#:~:text=Questions%20%26%20Answers%20Included-,Question%20%2311,-Topic%201
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
Company wants to rewrite employee directory 2 use AWS ss.
### Condiciones
- directory consists of personal data & high-res photo
- search & retrieval func needed

### OPTS
a. encode data and store in [[DynamoDB]] using a sort key

b. store data in DynamoDB and photo in [[Simple Storage Service|S3]] ^33fb54

c. use [[Amazon Cognito]]'s user pool -- no, es para gestión de ID y auth, no para store user data^a708f1

d. store data in [[Relational DB Service|RDS]] and photos in [[Elastic File System|EFS]] -- no es tan escalable como [[Employee directory#^33fb54|b]]

### Análisis

> [!note] Mi respuesta
> [[Employee directory#^a708f1|C]].
### Answer
[[Employee directory#^33fb54|B]].