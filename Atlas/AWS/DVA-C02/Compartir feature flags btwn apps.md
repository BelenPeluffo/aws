---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 531 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/157496-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] Ver el video de [[AppConfig]]
### Notas
- 
### Situación
A company has an application that runs on Amazon [[Elastic Compute Cloud|EC2]] instances. The application needs to use dynamic feature flags that will be shared with other applications. The application must poll on an interval for new feature flag values. The values must be cached when they are retrieved.  
  
Which solution will meet these requirements in the MOST operationally efficient way?

- A. Store the feature flag values in AWS Secrets Manager. Configure an Amazon [[ElastiCache]] node to cache the values by using a lazy loading strategy in the application. Update the application to poll for the values on an interval from ElastiCache.
	No. [[Secrets Manager]] está hecho para creds y demás cosas. Sale más caro que usar [[SSM Parameter Store]], y usarlo no es eficiente.
- B. Store the feature flag values in an Amazon DynamoDB table. Configure [[DynamoDB]] Accelerator (DAX) to cache the values by using a lazy loading strategy in the application. Update the application to poll for the values on an interval from DynamoDB.
	No es eficiente. Existen ss que pueden gestionar mejor la funcionalidad deseada.
- C. Store the feature flag values in AWS [[AppConfig]]. Configure AWS AppConfig Agent on the EC2 instances to poll for the values on an interval. Update the application to retrieve the values from the AppConfig Agent localhost endpoint.
	Es ésta. Key words: dynamic feature flag n' poll on intervals
- D. Store the feature flag values in AWS Systems Manager Parameter Store. Configure the application to poll on an interval. Configure the application to use the AWS SDK to retrieve the values from Parameter Store and to store the values in memory.
	SSM PS está hecho justamente para ésto.
### Condiciones
- 

### OPTS
a.

### Análisis
D
> [!note] Mi respuesta
> 
### Answer
C