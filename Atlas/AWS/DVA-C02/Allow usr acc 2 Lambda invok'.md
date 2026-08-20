---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 116 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107050-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] No entiendo bien la diferencia entre A y C
### Notas
IAM group { QA --}--URL--> Lambda
### Situación
A company has **hundreds** of AWS [[Lambda]] functions that the company's QA team needs to test by using the Lambda function URLs. A developer needs to **configure the authentication** of the Lambda functions to allow access so that the QA [[Identity and Access Management|IAM]] group can invoke the Lambda functions by using the public URLs.  
  
Which solution will meet these requirements?

- A. Create a CLI script that loops on the Lambda functions to add a Lambda function URL with the `AWS_IAM` auth type. Run another script to create an IAM identity-based policy that allows the `lambda:InvokeFunctionUrl` action to all the Lambda function Amazon Resource Names (ARNs). Attach the policy to the QA IAM group.
- B. Create a CLI script that loops on the Lambda functions to add a Lambda function URL with the `NONE` auth type. Run another script to create an IAM resource-based policy that allows the lambda:InvokeFunctionUrl action to all the Lambda function Amazon Resource Names (ARNs). Attach the policy to the QA IAM group.
	-- incorrecto, porque debe permitir auth sólo al group del QA
- C. Create a CLI script that loops on the Lambda functions to add a Lambda function URL with the `AWS_IAM` auth type. Run another script to loop on the Lambda functions to create an IAM identity-based policy that allows the `lambda:InvokeFunctionUrl` action from the QA IAM group's Amazon Resource Name (ARN).
- D. Create a CLI script that loops on the Lambda functions to add a Lambda function URL with the `NONE` auth type. Run another script to loop on the Lambda functions to create an IAM resource-based policy that allows the lambda:InvokeFunctionUrl action from the QA IAM group's Amazon Resource Name (ARN).
	-- incorrecto bis
### Condiciones
- 

### OPTS
a.

### Análisis
Es C, porque el permiso para invocar las lambdas debe tenerlo el grupo
> [!note] Mi respuesta
> 
### Answer
A