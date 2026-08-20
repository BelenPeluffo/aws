---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 117 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107051-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] Leer más sobre DynamoDB streams
### Notas
- 
### Situación
A developer maintains a critical business application that uses Amazon [[DynamoDB]] as the primary data store. The DynamoDB table contains millions of documents and receives 30-60 requests each minute. The developer needs to perform processing in near-real time on the documents when they are added or updated in the DynamoDB table.  
  
How can the developer implement this feature with the LEAST amount of change to the existing application code?

- A. Set up a cron job on an Amazon EC2 instance. Run a script every hour to query the table for changes and process the documents.
- B. Enable a DynamoDB stream on the table. Invoke an AWS Lambda function to process the documents.
- C. Update the application to send a PutEvents request to Amazon EventBridge. Create an EventBridge rule to invoke an AWS Lambda function to process the documents.
- D. Update the application to synchronously process the documents directly after the DynamoDB write.
### Condiciones
- 

### OPTS
a.

### Análisis
B
> [!note] Mi respuesta
> 
### Answer
B