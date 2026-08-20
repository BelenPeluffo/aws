---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 72 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106491-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿Qué diferencia hay entre el approach de B y de C?
### Notas
- 
### Situación
A developer creates a VPC named VPC-A that has public and private subnets. The developer also creates an Amazon [[Relational DB Service|RDS]] database inside the private subnet of VPC-A. To perform some queries, the developer creates an AWS [[Lambda]] function in the default VPC. The Lambda function has code to access the RDS database. When the Lambda function runs, an error message indicates that the function cannot connect to the RDS database.  
  
How can the developer solve this problem?

- A. Modify the RDS security group. Add a rule to allow traffic from all the ports from the VPC CIDR block. ^78c149
- B. Redeploy the Lambda function in the same subnet as the RDS instance. Ensure that the RDS security group allows traffic from the Lambda function. ^66506d
- C. Create a security group for the Lambda function. Add a new rule in the RDS security group to allow traffic from the new Lambda security group. ^341a63
- D. Create an IAM role. Attach a policy that allows access to the RDS database. Attach the role to the Lambda function.
### Condiciones
- 

### OPTS
a.

### Análisis
Mis respuestas serían [[Acc 2 a private instance of RDS#^66506d|B]], porque me parece que lo ideal sería tenerla en la subnet privada; pero luego pienso que quizás con agregarle un security group y permitirle acceso a la RDS es suficiente, por éso: [[Acc 2 a private instance of RDS#^341a63|C]].
> [!note] Mi respuesta
> 
### Answer
B.