---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 30 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/102904-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] ¿eventos de Cognito que pueden usarse de disparadores de lambda?
	[[Amazon Cognito#^b533d2|Ver en nota]].
### Notas
- 
### Situación
[[Amazon Cognito]] user pools. MFA.
### Condiciones
- send notif every time login
- most op efficient

### OPTS
a. [[Lambda]] w [[Simple Email Service|SES]]. [[API Gateway|API-GW]] 2 invoke Lambda. call API when login confirmation received.

b. Lambda + SNS. Cognito post-auth lambda trigger. ^444e7f

c. Lambda + SNS. [[CloudWatch Logs]] filter 2 invoke based on login status.

d. (won't dignify that answer w a question)

### Análisis

> [!note] Mi respuesta
> [[Email notifications after login#^444e7f|B]].
### Answer
B.