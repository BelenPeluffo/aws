---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 111 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107028-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company has an image storage web application that runs on AWS. The company hosts the application on Amazon [[Elastic Compute Cloud|EC2]] instances in an [[AutoScaling Group]]. The Auto Scaling group acts as the target group for an Application Load Balancer ([[Elastic Load Balancer|ALB]]) and uses an Amazon [[Simple Storage Service|S3]] bucket to store the images for sale.  
  
The company wants to develop a feature to test system requests. The feature will direct requests to a separate target group that hosts a new beta version of the application.  
  
Which solution will meet this requirement with the LEAST effort?

- A. Create a new Auto Scaling group and target group for the beta version of the application. Update the ALB routing rule with a condition that looks for a cookie named version that has a value of beta. Update the test system code to use this cookie to test the beta version of the application. -- esta puede ser
- B. Create a new ALB, Auto Scaling group, and target group for the beta version of the application. Configure an alternate Amazon Route 53 record for the new ALB endpoint. Use the alternate Route 53 endpoint in the test system requests to test the beta version of the application. -- u lost me at the first phrase
- C. Create a new ALB, Auto Scaling group, and target group for the beta version of the application. Use Amazon CloudFront with Lambda@Edge to determine which specific request will go to the new ALB. Use the CloudFront endpoint to send the test system requests to test the beta version of the application. -- same
- D. Create a new Auto Scaling group and target group for the beta version of the application. Update the ALB routing rule with a condition that looks for a cookie named version that has a value of beta. Use Amazon CloudFront with Lambda@Edge to update the test system requests to add the required cookie when the requests go to the ALB. -- overkill de A
### Condiciones
- 

### OPTS
a.

### Análisis
A
> [!note] Mi respuesta
> 
### Answer
A