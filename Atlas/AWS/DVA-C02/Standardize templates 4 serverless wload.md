---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 535 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156695-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer needs to automate deployments for a **serverless, event-based** workload. The developer needs to create **standardized templates to define the infrastructure** and to test the functionality of the workload locally before deployment  
  
The developer already uses a pipeline in AWS [[Atlas/AWS/CodePipeline]]. The developer needs to incorporate any other infrastructure changes into the existing pipeline.  
  
Which solution will meet these requirements?

- A. Create an AWS Serverless Application Model (AWS [[Serverless App Model|SAM]]) template. Configure the pipeline stages in CodePipeline to run the necessary AWS SAM CLI commands to deploy the serverless workload.
	Para mí, es ésta.
- B. Create an AWS Step Functions workflow template based on the infrastructure by using the Amazon States Language. Start the Step Functions state machine from the existing pipeline.
	Not gonna dignify that answer w a q.
- C. Create an AWS CloudFormation template. Use the existing pipeline workflow to build a pipeline for AWS CloudFormation stacks.
	Se podría hacer, pero como dice lo de *serverless*, conviene más SAM que está pensado para éso.
- D. Create an AWS Serverless Application Model (AWS SAM) template. Use an automated script to deploy the serverless workload by using the AWS SAM CLI deploy command.
	Ésta me parece que es overkill y para éso está CPipeline, ¿o no?
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