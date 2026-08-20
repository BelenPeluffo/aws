---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 69 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107440-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is configuring an application's deployment environment in AWS [[Atlas/AWS/CodePipeline]]. The application code is stored in a GitHub repository. The developer wants to ensure that the repository package's unit tests run in the new deployment environment. The developer has already set the pipeline's source provider to GitHub and has specified the repository and branch to use in the deployment.  
  
Which combination of steps should the developer take next to meet these requirements with the **LEAST overhead**? (Choose **two**.)

- A. Create an AWS CodeCommit project. Add the repository package's build and test commands to the project's buildspec.
- B. Create an AWS CodeBuild project. Add the repository package's build and test commands to the project's buildspec. ^8635a1
- C. Create an AWS CodeDeploy project. Add the repository package's build and test commands to the project's buildspec. ^7f33f8
- D. Add an action to the source stage. Specify the newly created project as the action provider. Specify the build artifact as the action's input artifact.
- E. Add a new stage to the pipeline after the source stage. Add an action to the new stage. Specify the newly created project as the action provider. Specify the source artifact as the action's input artifact. ^59eb80

### Condiciones
- 

### OPTS
a.

### Análisis
Para mí son [[Using CodePipeline#^8635a1|B]] y [[Using CodePipeline#^7f33f8|C]].
> [!note] Mi respuesta
> 
### Answer
B y [[Using CodePipeline#^59eb80|E]].