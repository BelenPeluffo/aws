---
dudas: true
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 128 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107066-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿diferencia entre C y D?
### Notas
- 
### Situación
A company has a front-end application that runs on four Amazon [[Elastic Compute Cloud|EC2]] instances behind an Elastic Load Balancer ([[Elastic Load Balancer|ELB]]) in a production environment that is provisioned by AWS [[Elastic Beanstalk]]. A developer needs to deploy and test new application code while updating the Elastic Beanstalk platform from the current version to a newer version of Node.js. The solution must result in zero downtime for the application.  
  
Which solution meets these requirements?

- A. Clone the production environment to a different platform version. Deploy the new application code, and test it. Swap the environment URLs upon verification. --mmm... no sé
- B. Deploy the new application code in an all-at-once deployment to the existing EC2 instances. Test the code. Redeploy the previous code if verification fails. -- no, porque no cumple con el zero downtime
- C. Perform an immutable update to deploy the new application code to new EC2 instances. Serve traffic to the new instances after they pass health checks. -- ésta me parece mejor
- D. Use a rolling deployment for the new application code. Apply the code to a subset of EC2 instances until the tests pass. Redeploy the previous code if the tests fail. -- ésta me parece aún mejor porque da lugar a que si las cosas salen mal, se puede rollback
### Condiciones
- 

### OPTS
a.

### Análisis
C o D.
> [!note] Mi respuesta
> 
### Answer
C