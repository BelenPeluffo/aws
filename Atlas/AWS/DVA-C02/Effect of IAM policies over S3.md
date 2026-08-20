---
dudas:
tags:
  - policies
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 49 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103919-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
[[Identity and Access Management|IAM]] policy 4 [[Simple Storage Service|S3]] acc:
```json
{
	"Version": "",
	"Statement": [
		{
			"Effect": "Allow",
			"Action": [
				"s3:GetObject",
				"s3:PutObject"
			],
			"Resource": "arn:...:bucket/*"
		},
		{
			"Effect": "Deny",
			"Action": "s3:*",
			"Resource": "arn:...:bucket/secrets*"
		}
	]
}
```
### Condiciones
- ¿qué hace la política?

### OPTS
a. acc todos los buckets menos `bucket`

b. acc todos los buckets que empiezan con `bucket` excepto el bucket que es `bucket/secrets`

c. acc todos los objs del `bucket` y acc a todas las acciones sobre objs que empiecen con `secrets`

d. acc todos los objs del `bucket` excepto aquellos que comienzan con `secrets` ^298555

### Análisis
Permite acceso a todo el bucket para hacer GET y PUT excepto a los objetos que empiecen en `secrets`, con los que no se puede realizar ninguna action.
> [!note] Mi respuesta
> [[Effect of IAM policies over S3#^298555|D]].
### Answer
D.