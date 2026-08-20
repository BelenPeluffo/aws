---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 142 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/117798-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿por qué C es mejor que A?
### Notas
ACTUAL: API-GW --> Lambda --> DynamoDB
WANTED: API-GW --> Lambda --> S3
### Situación
An online food company provides an Amazon [[API Gateway]] HTTP API to receive orders for partners. The API is integrated with an AWS [[Lambda]] function. The Lambda function stores the orders in an Amazon [[DynamoDB]] table.  
  
The company expects to onboard additional partners. Some of the partners require additional Lambda functions to receive orders. The company has created an Amazon [[Simple Storage Service|S3]] bucket. The company needs to store all orders and updates in the S3 bucket for future analysis.  
  
How can the developer ensure that all orders and updates are stored to Amazon S3 with the **LEAST development effort**?

- A. Create a new Lambda function and a new API Gateway API endpoint. Configure the new Lambda function to write to the S3 bucket. Modify the original Lambda function to post updates to the new API endpoint. -- creo que es ésta
- B. Use Amazon [[Kinesis Data Streams]]s to create a new data stream. Modify the Lambda function to publish orders to the data stream. Configure the data stream to write to the S3 bucket. -- me parece que es overkill
	Quedaría así: API-GW --> Lambda --> KDS --> S3
	Too much.
- C. Enable DynamoDB Streams on the DynamoDB table. Create a new Lambda function. Associate the stream’s Amazon Resource Name (ARN) with the Lambda function. Configure the Lambda function to write to the S3 bucket as records appear in the table's stream.
	Quedaría: API-GW --> Lambda --> DynamoDB -- stream --> Lambda 2 --> S3
- D. Modify the Lambda function to publish to a new Amazon Simple Notification Service (Amazon SNS) topic as the Lambda function receives orders. Subscribe a new Lambda function to the topic. Configure the new Lambda function to write to the S3 bucket as updates come through the topic.
	Quedaría: API-GW --> Lambda --> SNS --> Lambda 2 --> S3
### Condiciones
- 

### OPTS
a.

### Análisis
A
> [!note] Mi respuesta
> 
### Answer
C