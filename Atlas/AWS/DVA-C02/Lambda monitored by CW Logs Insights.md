---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 556 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/303273-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿CW Logs Insights??
### Notas
- 
### Situación
A company’s developer needs to activate Amazon [[CloudWatch Logs#^3de2c6|CW Logs Insights]] for an application’s AWS [[Lambda]] functions. The company uses an AWS Serverless Application Model (AWS [[Serverless App Model|SAM]]) template to deploy the application. The SAM template includes a logical resource that is named CloudWatchLogGroup.  
  
How should the developer modify the SAM template to activate CloudWatch Logs Insights for the Lambda functions?

- A. Add an output named CloudWatchinsightRule that contains a value of the Amazon Resource Name (ARN) for the CloudWatchLogGroup resource.
- B. Add a parameter named CloudWatchLogGroupNamePrefix that contains a value of the application name. Reference the new parameter in the CloudWatchLogGroup resource.
- C. For each Lambda function, add the layer for the Lambda Insights extension and the `CloudWatchLambdaInsightsExecutionRolePolicy` AWS managed policy.
	Es la layer de Lambda Insight lo que permite la integración con Log Insights.
- D. For each Lambda function, set Tracing mode to Active and add the `CloudWatchLambdaInsightsExecutionRolePolicy` AWS managed policy.
	El Active tracing es una integración con X-Ray.
### Condiciones
- 

### OPTS
a.

### Análisis
Siento que es D, pero no se bien.
D no es porque el tracing del que habla es para integrar con X-Ray y tiene que ver con la latencia y el flujo de datos con otros servicios. Lo que queremos poder hacer es mandar métricas específicas a CW Logs. Por éso es C.
> [!note] Mi respuesta
> 
### Answer
C