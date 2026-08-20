---
dudas: true
tags:
aliases:
incorrecta: true
---
Pregunta: UDEMY
### Dudas
- [ ] CW -- Cómo definir custom metrics y pushearlas
### Notas
- 
### Situación
A serverless application built on AWS processes customer orders 24/7 using an AWS Lambda function and communicates with an external vendor's HTTP API for payment processing. The development team wants to notify the support team in near real-time using an existing Amazon Simple Notification Service (Amazon SNS) topic, but only when the external API error rate exceeds 5% of the total transactions processed in an hour.

As an AWS Certified Developer Associate, which option will you suggest as the most efficient solution?

- A. Configure CloudWatch metrics with detailed monitoring for the external payment processing API calls. Create a CloudWatch alarm that sends a notification via the existing SNS topic when the error rate exceeds the specified rate
	No, porque necesitás CUSTOM metrics y recordá que las metricas que ofrece CloudWatch tienen más que ver con la performance y la operabilidad.
- B. Configure and push high-resolution custom metrics to CloudWatch that record the failures of the external payment processing API calls. Create a CloudWatch alarm that sends a notification via the existing SNS topic when the error rate exceeds the specified rate
	Keyword: CUSTOM METRICS. "Configure n push" significa que vos creás la lógica en tu app para calcular ese valor y ese valor es el que pusheás a CW y en base al que vas a triggerear la alarma.
- C. Log the results of payment processing API calls to Amazon CloudWatch. Leverage Amazon CloudWatch Metric Filter to look at the CloudWatch logs. Set up the Lambda function to check the output from CloudWatch Metric Filter on a schedule and send notification via the existing SNS topic when the error rate exceeds the specified rate
	- 
- D. Log the results of payment processing API calls to Amazon CloudWatch. Leverage Amazon CloudWatch Logs Insights to query the CloudWatch logs. Set up the Lambda function to check the output from CloudWatch Logs Insights on a schedule and send notification via the existing SNS topic when the error rate exceeds the specified rate
	- 
### Condiciones
- 

### OPTS
a.

### Análisis
A
> [!note] Mi respuesta
> 
### Answer
B