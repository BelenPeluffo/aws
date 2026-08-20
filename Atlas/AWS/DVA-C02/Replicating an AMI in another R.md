---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 107 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107007-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿qué diferencia hay entre *copy* y *build*?
### Notas
- 
### Situación
A company has a web application that runs on Amazon [[Elastic Compute Cloud|EC2]] instances with a custom Amazon Machine Image ([[Amazon Machine Image|AMI]]). The company uses AWS [[CloudFormation]] to provision the application. The application runs in the us-east-1 Region, and the company needs to deploy the application to the us-west-1 Region.  
  
An attempt to create the AWS CloudFormation stack in us-west-1 fails. An error message states that the AMI ID does not exist. A developer must resolve this error with a solution that uses the **least amount of operational overhead**.  
  
Which solution meets these requirements?

- A. Change the AWS CloudFormation templates for us-east-1 and us-west-1 to use an AWS AMI. Relaunch the stack for both Regions.
- B. Copy the custom AMI from us-east-1 to us-west-1. Update the AWS CloudFormation template for us-west-1 to refer to AMI ID for the copied AMI. Relaunch the stack.
- C. Build the custom AMI in us-west-1. Create a new AWS CloudFormation template to launch the stack in us-west-1 with the new AMI ID.
- D. Manually deploy the application outside AWS CloudFormation in us-west-1.
### Condiciones
- 

### OPTS
a.

### Análisis
Para mí es B, pero ¿qué diferencia hay entre *copy* y *build*?
> [!note] Mi respuesta
> 
### Answer
B