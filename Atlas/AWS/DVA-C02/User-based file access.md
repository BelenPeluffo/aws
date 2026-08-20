---
dudas:
tags:
  - security
aliases:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/#:~:text=28-,Question%20%233,-Topic%201
### Dudas
- [x] ¿Se puede asignar permisos IAM en base a las identidades de Cognito?
	Sí. Hacés uso de [[Identity and Access Management#^3d15c6|las dynamic policies de IAM]] para asignar una carpeta para cada user y luego se la adjuntás a la policy del pool de Cognito como inline policy.
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
App que usa user&ID pools de [[Amazon Cognito]]. Se implementará user-specific file up-down 2 [[Simple Storage Service|S3]].
### Condiciones
- users can only acc own files
- acc in a secure manner, highest level of security

### OPTS
a.
- [[Simple Storage Service|S3]] notifications

b. ^21e692
- [[Atlas/AWS/DynamoDB]] 2 save file metadata and use as ref in UI

c.
- [[API Gateway|API-GW]]
- [[Lambda]]

d. ^8b2a3b
- [[Identity and Access Management|IAM]] policy with cognito ID prefix 2 enforce access 2 own files

### Análisis
Si se puede hacer lo del prefijo => [[User-based file access#^8b2a3b|d]], si no => [[User-based file access#^21e692|b]].

> [!note] Mi respuesta
> D.
### Answer
D.