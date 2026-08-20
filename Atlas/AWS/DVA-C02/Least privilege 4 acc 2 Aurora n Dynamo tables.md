---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 518 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156675-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
Two containerized microservices are hosted on Amazon [[Elastic Compute Cloud|EC2]] [[Elastic Container Service|ECS]]. The first microservice reads an Amazon RDS [[Amazon Aurora|Aurora]] database instance, and the second microservice reads an Amazon [[DynamoDB]] table.  
  
How can each microservice be granted the minimum privileges?

- A. Set ECS_ENABLE_TASK_IAM_ROLE to false on EC2 instance boot in ECS agent configuration file. Run the first microservice with an IAM role for ECS tasks with read-only access for the Aurora database. Run the second microservice with an IAM role for ECS tasks with read-only access to DynamoDB.
- B. Set ECS_ENABLE_TASK_IAM ROLE to false on EC2 instance boot in the ECS agent configuration file. Grant the instance profile role read-only access to the Aurora database and DynamoDB.
- C. Set ECS_ENABLE_TASK_IAM ROLE to true on EC2 instance boot in the ECS agent configuration file. Run the first microservice with an IAM role for ECS tasks with read-only access for the Aurora database. Run the second microservice with an IAM role for ECS tasks with read-only access to DynamoDB.
- D. Set ECS_ENABLE_TASK_IAM_ROLE to true on EC2 instance boot in the ECS agent configuration file. Grant the instance profile role read-only access to the Aurora database and DynamoDB.
### Condiciones
- 

### OPTS
a.

### Análisis
C porque necesita el IAM role y los mínimos permisos son read-only.
> [!note] Mi respuesta
> 
### Answer
C