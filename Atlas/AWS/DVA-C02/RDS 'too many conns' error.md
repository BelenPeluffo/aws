---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 103 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106984-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
An ecommerce website uses an AWS [[Lambda]] function and an Amazon [[Relational DB Service|RDS]] for MySQL database for an order fulfillment service. The service needs to return order confirmation immediately.  
  
During a marketing campaign that caused an increase in the number of orders, the website's operations team noticed errors for “**too many connections**” from Amazon RDS. However, the RDS DB cluster metrics are healthy. CPU and memory capacity are still available.  
  
What should a developer do to resolve the errors?

- A. Initialize the database connection outside the handler function. Increase the max_user_connections value on the parameter group of the DB cluster. Restart the DB cluster.
- B. Initialize the database connection outside the handler function. Use RDS Proxy instead of connecting directly to the DB cluster.
- C. Use Amazon [[Simple Queue Service]] (Amazon [[SQS]]) FIFO queues to queue the orders. Ingest the orders into the database. Set the Lambda function's concurrency to a value that equals the number of available database connections.
- D. Use Amazon [[Simple Queue Service]] (Amazon [[Simple Queue Service|SQS]]) FIFO queues to queue the orders. Ingest the orders into the database. Set the Lambda function's concurrency to a value that is less than the number of available database connections.
### Condiciones
- 

### OPTS
a.

### Análisis
Para mí es B porque para éso existe [[RDS Proxy]].
> [!note] Mi respuesta
> 
### Answer
B