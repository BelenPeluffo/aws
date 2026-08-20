---
dudas:
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 64 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103687-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is migrating some features from a legacy monolithic application to use AWS [[Lambda]] functions instead. The application currently stores data in an Amazon [[Amazon Aurora|Aurora]] DB cluster that runs in [[private subnet]]s in a VPC. The AWS account has one VPC deployed. The Lambda functions and the DB cluster are deployed in the same AWS Region in the same AWS account.  
The developer needs to ensure that the Lambda functions can **securely access the DB cluster without crossing the public internet**.  
Which solution will meet these requirements?

- A. Configure the DB cluster's public access setting to Yes.
	-- no sé si existe éso, pero incluso así: se supone que se debe acceder a ella desde el internet privado
- B. Configure an Amazon RDS database proxy for he Lambda functions.
	-- un proxy no es otra cosa que una capa de redirección?
- C. Configure a NAT gateway and a security group for the Lambda functions.
	-- ~~o sea, creo que va por acá, porque es el [[NATGW]] el que gestiona quién accede a una subnet privada y lo recomendado es siempre definir [[security groups|security group]]~~ no, porque sigue conectándose desde la internet pública ^6b26de
- D. Configure the VPC, subnets, and a security group for the Lambda functions.
	-- algo al respecto en [[Lambda#^dd0a4a|esta nota]]. ^22920f
### Condiciones
- 

### OPTS
a.

### Análisis
Para mí es la del NATGW, [[Grant Lambda private acc 2 private r#^6b26de|C]].
> [!note] Mi respuesta
> 
### Answer
[[Grant Lambda private acc 2 private r#^22920f|D]].