---
dudas:
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 26 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103656-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿cómo se gestiona la duplicidad con Dynamo?
- [ ] ¿por qué la opción C es incorrecta pero la B es correcta?
### Notas
IoT device -> Lambda as API
### Situación
App 4 IoT devices. Send data 2 [[Lambda]] functioning as API REST. Each API has unique ID. Rq can increase randomly.

A developer is creating an application that will be deployed on IoT devices. The application will send data to a RESTful API that is deployed as an AWS Lambda function. The application will assign **each API request a unique identifier**. The volume of API requests from the application can randomly increase at any given time of day.  
During periods of request throttling, the application might need to **retry requests**. The API must be able to **handle duplicate requests without inconsistencies or data loss**.  
Which solution will meet these requirements?

- A. Create an Amazon RDS for MySQL DB instance. Store the unique identifier for each request in a database table. Modify the Lambda function to check the table for the identifier before processing the request.
	Es demasiado estructurada esta opción. No.
- B. Create an Amazon DynamoDB table. Store the unique identifier for each request in the table. Modify the Lambda function to check the table for the identifier before processing the request.
- C. Create an Amazon DynamoDB table. Store the unique identifier for each request in the table. Modify the Lambda function to return a client error response when the function receives a duplicate request.
	Ésto no nos sirve. Responder con un error de cliente no es lo correcto porque 1. debemos poder gestionarlo y 2. no es un error de cliente, sería un error de servidor por encontrar un duplicado.
- D. Create an Amazon ElastiCache for Memcached instance. Store the unique identifier for each request in the cache. Modify the Lambda function to check the cache for the identifier before processing the request.
	Ésta me parece que no porque necesito que se persista la data just in case.
### Condiciones
- throtle period => retry rq
- handle duplicate rq w/o inconsistencies/data loss
### OPTS
a. RDS 2 store rq ID. upd Lambda code 2 use ID as condition 2 process rq.

b. [[DynamoDB]] 2 store ID. ídem

c. Dynamo. upd Lambda 2 return error when duplicate ID. -- no porque no tiene que devolver error, creo

d. [[ElastiCache]] Memcached 2 store rq ID. upd Lamda 2 look 4 ID. -- creo que es ésta porque ¿por qué guardaría permanentemente el ID? ^a5d044

### Análisis

> [!note] Mi respuesta
> [[Retry handling 4 Lambda 4 IoT#^a5d044|D]] porque me parece que usar storages permanentes no tiene lógica.
### Answer
B. Justamente necesitás poder guardar los datos para garantizar idempotencia.