---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 132 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/117336-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer creates an AWS [[Lambda]] function that retrieves and groups data from several public API endpoints. The Lambda function has been updated and configured to connect to the private subnet of a VPC. An internet gateway is attached to the VPC. The VPC uses the default network ACL and security group configurations.  
  
The developer finds that the Lambda function can no longer access the public API. The developer has ensured that the public API is accessible, but the Lambda function cannot connect to the API  
  
How should the developer fix the connection issue?

- A. Ensure that the network ACL allows outbound traffic to the public internet. -- puede que sea ésta, porque [[Network Access Control List|NACL]] tiene que tener explicitado el out tmb; pero al principio del problema explica que ya lo hacía y que dejó de funcionar al actualizarla.
- B. Ensure that the security group allows outbound traffic to the public internet. -- los [[security groups|security group]] por defecto ya tienen activado el outboung
- C. Ensure that outbound traffic from the private subnet is routed to a public NAT gateway. -- ésta puede ser
- D. Ensure that outbound traffic from the private subnet is routed to a new internet gateway. -- las subnets privadas sólo conectan a [[NATGW]]
### Condiciones
- 

### OPTS
a.

### Análisis
C?
> [!note] Mi respuesta
> 
### Answer
C