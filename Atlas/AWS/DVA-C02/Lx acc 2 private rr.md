---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 534 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156684-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
### Notas
- 
### Situación
A developer is creating an AWS [[Lambda]] function that needs network access to private resources in a VPC.  
  
Which solution will provide this access with the LEAST operational overhead?

- A. Attach the Lambda function to the VPC through private subnets. Create a security group that allows network access to the private resources. Associate the security group with the Lambda function.
	~~No me parece.~~ Es ésta, sino que le da vueltas con el *through private subnets*. Pero literalmente ésta lo que hace es deployar la lambda en la VPC...
- B. Configure the Lambda function to route traffic through a VPN connection. Create a security group that allows network access to the private resources. Associate the security group with the Lambda function.
	E?
- C. Configure a VPC endpoint connection for the Lambda function. Set up the VPC endpoint to route traffic through a NAT gateway.
	Creo que es ésta.
- D. Configure an AWS PrivateLink endpoint for the private resources. Configure the Lambda function to reference the PrivateLink endpoint.
	Is this even a thing?
### Condiciones
- 

### OPTS
a.

### Análisis
C
> [!note] Mi respuesta
> 
### Answer
A