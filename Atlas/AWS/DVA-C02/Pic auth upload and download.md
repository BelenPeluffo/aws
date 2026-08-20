---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#:~:text=15-,Question%20%2312,-Topic%201
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
App stores pics from cellphones 2 cloud. 10k users. [[API Gateway|API-GW]] REST API conn 2 [[Lambda]] 4 pic processing. Details about pics stored in [[DynamoDB]].

### Condiciones
- users must use acc 2 acc app
- must up & down pics
- pic size: 300kb-5mb
- LEAST op overhead

### OPTS
a. [[Amazon Cognito]] 4 user auth & control acc 2 API. Lambda 2 store pic&details in Dynamo. -- no, porque sólo llega a [[DynamoDB#^24ad5b|400kb]] ^516fa4

b. Cognito 4 user auth & acc 2 API. Lambda 4 pic storage in [[Simple Storage Service|S3]]. Object key + details stored in Dynamo. ^8ce974

c. [[Identity and Access Management|IAM]] 4 each user in app during sign-up. IAM auth 4 API acc. Lambda 4 storing pics in S3. Object key + details stored in Dynamo. -- ¿para qué implementar lógica para crear un user IAM si ya tenemos todo eso resuelto con Cognito?

d. users table in Dynamo.

### Análisis
Para mí es la [[Pic auth upload and download#^8ce974|b]] y no la [[Pic auth upload and download#^516fa4|a]] porque Dynamo no llega a 5mb, me parece. Si sí llegara, sería la a.
> [!note] Mi respuesta
> [[Pic auth upload and download#^8ce974|B]].
### Answer
B.