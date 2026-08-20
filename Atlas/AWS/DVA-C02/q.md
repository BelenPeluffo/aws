---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 517 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/157450-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company has an application that processes audio files for different departments. When audio files are saved to an Amazon [[Simple Storage Service|S3]] bucket, an AWS [[Lambda]] function receives an event notification and processes the audio input.  
  
A developer needs to update the solution so that the application can process the audio files for each department independently. The application must publish the audio file location for each department to each department's existing Amazon Simple Queue Service (Amazon [[Simple Queue Service|SQS]]) queue.  
  
Which solution will meet these requirements with no changes to the Lambda function code?

- A. Configure the S3 bucket to send the event notifications to an Amazon Simple Notification Service (Amazon SNS) topic. Subscribe each department’s SQS queue to the SNS topic. Configure subscription filter policies.
	Yo creo que podría ir por acá.
- B. Update the Lambda function to write the file location to a single shared SQS queue. Configure the shared SQS queue to send the file reference to each department’s SQS queue.
	Justamente, acá está haciendo lo contrario a lo que te pide la consigna.
- C. Update the Lambda function to send the file location to each department’s SQS queue.
	Hace lo contrario a lo que te pide la consigna.
- D. Configure the S3 bucket to send the event notifications to each department’s SQS queue.
	Si ésto se pudiera hacer, iría por acá. Pero me parece que no se puede.
### Condiciones
- 

### OPTS
a.

### Análisis
A
> [!note] Mi respuesta
> 
### Answer