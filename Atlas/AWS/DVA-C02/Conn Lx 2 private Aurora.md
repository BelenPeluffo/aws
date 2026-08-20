---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 537 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156697-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] 
### Notas
- 
### Situación
A developer is deploying a new Node.js AWS [[Lambda]] function that is **not connected to a VPC**. The Lambda function needs to connect to and query an Amazon [[Amazon Aurora|Aurora]] database that is **not publicly accessible**. The developer is expecting unpredictable surges in database traffic.  
  
What should the developer do to give the Lambda function access to the database?

- A. Configure the Lambda function to use an Amazon RDS proxy.
	Para mí es ésta pero porque todas las demás me dejan como ????
- B. Configure a NAT gateway. Attach the NAT gateway to the Lambda function.
	Instintivamente pensaría ésta pero 1. los servicios no se "attachean" al NAT GW (???) y 2. el NAT GW es para conectar al internet público, no para conectar a ss de AWS a través del internet público. Yo creo que lo que nos funcionaría sería el VPC EP...
- C. Enable public access on the Aurora database. Configure a security group on the database to allow outbound access for the database engine’s port.
	me parece que este no es porque si está en la subnet privada es porque queremos que no sea accesible.
- D. Enable VPC access for the Lambda function. Attach the Lambda function to a new security group that does not have rules.
	- Ésta se acerca más al ideal: VPC EP. PERO que el security group no tenga reglas me suena raro...
### Condiciones
- 

### OPTS
a.

### Análisis
A
> [!note] Mi respuesta
> 
### Answer
D