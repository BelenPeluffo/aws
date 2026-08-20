---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#:~:text=11%25-,Question%20%2318,-Topic%201
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
[[Lambda]] running 24/7 4 processing customer orders. Fx uses 3rd party API 2 process payments. 3rd party API returns errors sometimes.
### Condiciones
- error rate > 5% -> send notif 2 support team ==near real time==
- use [[SNS]] topic already created 4 support team

### OPTS
a. send all responses 2 [[CloudWatch]]. use [[CloudWatch Logs|CW Logs]] Insights 2 query logs. have fx check logs and notify topic.

b. custom metrics in CWatch. config [[CW Alarms]] 2 notify topic. -- creo que sería esta, porque es la más straight forward; pero sólo si se pueden definir custom metrics en CWatch... Aunque creo que las métricas pueden ser sólo relacionadas a la performance, o no...? ^19699b

c. publish results directly in new topic -- no, porque tenemos que reutilizar el existente

d. send rtas a [[Simple Storage Service|S3]]. schedule [[Amazon Athena]] 2 query and publish in topic -- ~~si la [[Publish on SNS topic on API error#^19699b|opción b]] no corresponde, es ésta~~ en realidad esta no va porque tenemos que recordar el criterio de *near real time* cosa que S3 y Athena no hacen, al contrario: agregan latencia ^c8ea1d

### Análisis

> [!note] Mi respuesta
> La [[Publish on SNS topic on API error#^19699b|B]] o la [[Publish on SNS topic on API error#^c8ea1d|D]].
### Answer
B.