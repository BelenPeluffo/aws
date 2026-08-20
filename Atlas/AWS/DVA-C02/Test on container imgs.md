---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 57 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/104013-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company needs to harden its container images before the images are in a running state. The company's application uses [[ECR]] as an image registry. [[EKS]] for compute, and an [[Atlas/AWS/CodePipeline]] pipeline that orchestrates a continuous integration and continuous delivery (CI/CD) workflow.  
Dynamic application security testing occurs in the final stage of the pipeline after a new image is deployed to a development namespace in the EKS cluster. A developer needs to place an analysis stage before this deployment to analyze the container image earlier in the CI/CD pipeline.  
Which solution will meet these requirements with the MOST operational efficiency?

- A. Build the container image and run the docker scan command locally. Mitigate any findings before pushing changes to the source code repository. Write a pre-commit hook that enforces the use of this workflow before commit. -- no porque hacerlo manual no es operativamente eficiente ^a878ad
- B. Create a new CodePipeline stage that occurs after the container image is built. Configure ECR basic image scanning to scan on image push. Use an AWS Lambda function as the action provider. Configure the Lambda function to check the scan results and to fail the pipeline if there are findings.
- C. Create a new CodePipeline stage that occurs after source code has been retrieved from its repository. Run a security scanner on the latest revision of the source code. Fail the pipeline if there are findings. -- no me sirve, el test debe ser sobre imgs ^f3a483
- D. Add an action to the deployment stage of the pipeline so that the action occurs before the deployment to the EKS cluster. Configure ECR basic image scanning to scan on image push. Use an AWS Lambda function as the action provider. Configure the Lambda function to check the scan results and to fail the pipeline if there are findings.

### Condiciones
- 

### OPTS
a.

### Análisis
~~Yo creo que iría con [[Test on container imgs#^f3a483|C]] por una cuestión de que realiza ese test de inmediato y se ahorra correr otras etapas y aplazar el error. Si no, es either B or D.~~ [[Test on container imgs#^a878ad|A]].
> [!note] Mi respuesta
> 
### Answer
B.