---
dudas:
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 97 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106947-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
app -- JSON file -- > S3 -- notif as trigger -- > Lambda -- transform'd obj -- > DynamoDB
### Situación
A developer has designed an application to store incoming data as JSON files in Amazon [[Simple Storage Service|S3]] objects. Custom business logic in an AWS [[Lambda]] function then transforms the objects, and the Lambda function loads the data into an Amazon [[DynamoDB]] table. Recently, the workload has experienced sudden and significant changes in traffic. The flow of data to the **DynamoDB table is becoming throttled**.  
  
The developer needs to implement a solution to **eliminate the throttling** and load the data into the DynamoDB table more consistently.  
  
Which solution will meet these requirements?

- A. Refactor the Lambda function into two functions. Configure one function to transform the data and one function to load the data into the DynamoDB table. Create an Amazon [[Simple Queue Service]] (Amazon [[SQS]]) queue in between the functions to hold the items as messages and to invoke the second function.
	-- pero el problema no es el envío a Dynamo???
	Sí. Con [[Simple Queue Service|SQS]] solucionás el problema de Dinamo porque limitás la cantidad de rqs a enviar.
- B. Turn on auto scaling for the DynamoDB table. Use Amazon [[CloudWatch]] to monitor the table's read and write capacity metrics and to track consumed capacity.
	-- ¿sirve para resolver el throttling? me parece que no...
- C. Create an alias for the Lambda function. Configure provisioned concurrency for the application to use.
	Me parece que no tiene nada que ver con el problema de la tabla..
- D. Refactor the Lambda function into two functions. Configure one function to store the data in the DynamoDB table. Configure the second function to process the data and update the items after the data is stored in DynamoDB. Create a DynamoDB stream to invoke the second function after the data is stored.
	-- me parece que nada que ver
	Nada que ver justamente porque el problema es de throttling, lo que implica que se están haciendo muchas rqs a la DB. Lo que hay que reducir, entonces, es la CANTIDAD de rqs. En esta opción hacemos lo contrario: hacemos 2 rqs por objeto a la DB.
### Condiciones
- 

### OPTS
a.

### Análisis
Si la tabla está throttling es porque se le están mandando muchas rqs... Entonces lo que hay que hacer es a. reducir la cantidad de rqs ó b. gestionar las rqs de forma centralizada?
> [!note] Mi respuesta
> 
### Answer
A.