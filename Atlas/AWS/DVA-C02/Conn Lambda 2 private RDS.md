---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 106 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106992-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] cuando una lambda se ejecuta simultáneamente múltiples veces, ¿el ARN sigue siendo el mismo?
- [x] ¿qué diferencia hay entre los dos permisos de Lambda que se mencionan?
	- [[Lambda#^e74b7b|AWSLambdaBasicExecutionRole]]
	- [[Lambda#^NIDLsJFh|AWSLambdaVPCAccessExecutionRole]]
### Notas
- 
### Situación
A company is updating an application to move the backend of the application from Amazon [[Elastic Compute Cloud|EC2]] instances to a serverless model. The application uses an Amazon [[Relational DB Service|RDS]] for MySQL DB instance and runs in a single VPC on AWS. The application and the DB instance are deployed in a **private subnet** in the VPC.  
  
The company needs to connect AWS [[Lambda]] functions to the DB instance.  
  
Which solution will meet these requirements?

- A. Create Lambda functions inside the VPC with the AWSLambdaBasicExecutionRole policy attached to the Lambda execution role. Modify the RDS security group to allow inbound access from the Lambda security group.
	No es ésta porque ese permiso sólo activa los logs para CW Logs.
- B. Create Lambda functions inside the VPC with the AWSLambdaVPCAccessExecutionRole policy attached to the Lambda execution role. Modify the RDS security group to allow inbound access from the Lambda security group.
	Es ésta misma.
- C. Create Lambda functions with the AWSLambdaBasicExecutionRole policy attached to the Lambda execution role. Create an interface [[VPC EP]] for the Lambda functions. Configure the interface endpoint policy to allow the lambda:InvokeFunclion action for each Lambda function's Amazon Resource Name (ARN).
	- El execution role sólo habilita los logs -> no
	- el VPC EP es lo que usa Lx cuando está deployada en una VPC para acceder a otros ss de AWS que no se encuentra dentro de la VPC.
	- la action permite invocar la Lx y es la que se define en las policies de los TRIGGERS de Lx.
- D. Create Lambda functions with the AWSLambdaVPCAccessExecutionRole policy attached to the Lambda execution role. Create an interface VPC endpoint for the Lambda functions. Configure the interface endpoint policy to allow the lambda:InvokeFunction action for each Lambda function's Amazon Resource Name (ARN).
	Lo mismo que la opción anterior, excepto que esta vez el execution role es correcto.
### Condiciones
- 

### OPTS
a.

### Análisis
Me parece que las opciones del ARN no sirven, porque las instancias tienen ARNs distintos (fijate que dice *each Lambda function*), o no? Pero el tema es que en ninguna de las opciones se dice de deployar la Lambda DENTRO de la subnet privada, por lo que sí o sí necesita un VPC EP, ¿o no?

Creo que es A o B, pero ni idea.
> [!note] Mi respuesta
> 
### Answer
B.