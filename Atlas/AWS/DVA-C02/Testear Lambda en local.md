---
dudas: false
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 86 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106939-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] qué es el CDK SYNTH??? ✅ 2026-08-06
	Transforma el IaC en [[CloudFormation]] template.
- [x] CDK DEPLOY??? ✅ 2026-08-06
	Deploy stack.
	- [x] ¿diferencia con `sam deploy`? ✅ 2026-08-06
		CDK es para INFRA as Code. SAM es para serverless apps.
- [x] `sam local invoke` vs. `sam local start-lambda`?? ✅ 2026-08-06
	`invoke` ejecuta una sola vez la lambda y requiere payload mockeado.
	`start-lambda` levanta un EP para que puedas hacer cuantas rqs quieras, simulando pegarle al EP de la Lambda posta.
- [x] fx construct identifier? ✅ 2026-08-06
	No es más que el nombre con que definís a la función en el código.
### Notas
- 
### Situación
A developer is implementing an AWS Cloud Development Kit (AWS [[Cloud Development Kit|CDK]]) serverless application. The developer will provision several AWS [[Lambda]] functions and Amazon [[API Gateway]] APIs during AWS [[CloudFormation]] stack creation. The developer's workstation has the AWS Serverless Application Model (AWS [[Serverless App Model|SAM]]) and the AWS CDK installed locally.  
  
How can the developer **test a specific Lambda function locally**?

- A. Run the sam package and sam deploy commands. Create a Lambda test event from the AWS Management Console. Test the Lambda function.
	No, creo que `sam package` es para otra cosa. Y `sam deploy` es para deployar el stack.
- B. Run the cdk synth and cdk deploy commands. Create a Lambda test event from the AWS Management Console. Test the Lambda function.
	Falta `sam`.
- C. Run the cdk synth and sam local invoke commands with the function construct identifier and the path to the synthesized CloudFormation template.
- D. Run the cdk synth and sam local start-lambda commands with the function construct identifier and the path to the synthesized CloudFormation template.
### Condiciones
- 

### OPTS
a.

### Análisis
Is either A o D, pero creo que es más D, por el local start-lambda...
> [!note] Mi respuesta
> 
### Answer
C.