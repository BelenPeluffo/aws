---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 123 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107059-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company must deploy all its Amazon [[Relational DB Service|RDS]] DB instances by using AWS [[CloudFormation]] templates as part of AWS [[Using CodePipeline]] continuous integration and continuous delivery (CI/CD) automation. The primary ==password for the DB== instance must be automatically generated as part of the deployment process.  
  
Which solution will meet these requirements with the **LEAST development effort**?

- A. Create an AWS [[Lambda]]-backed CloudFormation custom resource. Write Lambda code that generates a secure string. Return the value of the secure string as a data field of the custom resource response object. Use the CloudFormation Fn::GetAtt intrinsic function to get the value of the secure string. Use the value to create the DB instance. -- requiere codear la Lambda
- B. Use the AWS [[CodeBuild]] action of CodePipeline to generate a secure string by using the following AWS CLI command: `aws secretsmanager get-random-password`. Pass the generated secure string as a CloudFormation parameter with the NoEcho attribute set to true. Use the parameter reference to create the DB instance. -- ésta me convence más
- C. Create an AWS Lambda-backed CloudFormation custom resource. Write Lambda code that generates a secure string. Return the value of the secure string as a data field of the custom resource response object. Use the CloudFormation Fn::GetAtt intrinsic function to get a value of the secure string. Create secrets in AWS Secrets Manager. Use the secretsmanager dynamic reference to use the value stored in the secret to create the DB instance. -- ???
- D. Use the AWS::[[Secrets Manager]]::Secret resource to generate a secure string. Store the secure string as a secret in AWS Secrets Manager. Use the secretsmanager dynamic reference to use the value stored in the secret to create the DB instance. -- pero el tema es que no es random. Mentira. No importa que no sea random, lo que importa es que sea distinta every time que se deploye el stack.
### Condiciones
- 

### OPTS
a.

### Análisis
Si me decís DB pass, pienso [[Secrets Manager]] y, por lo tanto, D.
> [!note] Mi respuesta
> 
### Answer
D