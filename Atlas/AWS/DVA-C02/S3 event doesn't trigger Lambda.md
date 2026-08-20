---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 83 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/109005-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer has created an AWS [[Lambda]] function to provide notification through Amazon Simple Notification Service (Amazon [[SNS]]) whenever a file is uploaded to Amazon [[Simple Storage Service|S3]] that is larger than 50 MB. The developer has deployed and tested the Lambda function by using the CLI. However, when the event notification is added to the S3 bucket and a 3,000 MB file is uploaded, the Lambda function does not launch.  
  
Which of the following is a possible reason for the Lambda function's inability to launch?

- A. The S3 event notification does not activate for files that are larger than 1,000 MB. -- ¿por qué sería así?
- B. The resource-based policy for the Lambda function does not have the required permissions to be invoked by Amazon S3. -- puede ser
- C. Lambda functions cannot be invoked directly from an S3 event. -- falso, ¿no existe para éso el event notification?
- D. The S3 bucket needs to be made public.
### Condiciones
- 

### OPTS
a.

### Análisis
Para mí, es B.
> [!note] Mi respuesta
> 
### Answer