---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 78 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107444-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿Está correcta mi razón por la que la otra opción de ALB es incorrecta?
### Notas
- 
### Situación
A company is planning to deploy an application on AWS behind an [[Elastic Load Balancer]]. The application uses an HTTP/HTTPS listener and must access the client IP addresses.  
  
Which load-balancing solution meets these requirements?

- A. Use an Application Load Balancer and the X-Forwarded-For headers. ^2f3e9c
- B. Use a Network Load Balancer (NLB). Enable proxy protocol support on the NLB and the target application.
- C. Use an Application Load Balancer. Register the targets by the instance ID.
- D. Use a Network Load Balancer and the X-Forwarded-For headers.
### Condiciones
- 

### OPTS
a.

### Análisis
Es definitivamente un [[Elastic Load Balancer|ALB]] (porque [[Elastic Load Balancer|NLB]] implica TCP). Creo que debería ser [[Acc client IP addresses#^2f3e9c|A]] por una cuestión de que no queremos el ID de la instancia, queremos el IP...
> [!note] Mi respuesta
> 
### Answer