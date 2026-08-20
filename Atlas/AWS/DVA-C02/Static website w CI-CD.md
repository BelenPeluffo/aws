---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 24 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103646-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- UAT = user acceptance testing
### Situación
Static websiteS. ==Src code of each in different repo tools==.

### Condiciones
- phased release
- different stages
- CI/CD
- HTTPS ^2b9f04
- non-continuous server run ^448ae6
- least op overhead

### OPTS
a. [[Amplify]] w serverless BE. each repo 2 each env. trigger deploy when merging code 2 branch. -- ¿que no diga con qué se triggerea el deployment quiere decir que deberíamos implementar código para triggearearlo manualmente?

b. [[Elastic Beanstalk]] 4 each site, with multiple envs. [[Elastic Beanstalk CLI]] 2 conn each branch. [[Atlas/AWS/CodePipeline]] 4 CI/CD. -- me parece que ésto es un overkill porque es static... y además porque tiene los servidores corriendo todo el tiempo (por las underlying instancias de EC2)

c. [[Simple Storage Service|S3]] 4 each site & env. CPipeline 4 pulling src. [[CodeBuild]] stage 2 copy src 2 bucket. -- ~~creo que this might b the 1, porque S3 está bueno para static websites, no sé, tho, si complies con [[Static website w CI-CD#^2b9f04|HTTPS]]~~ no es ésta porque no permite linkeo entre env y branch, hay mucha config que tenés que hacer (CPipeline, CBuild, CFront para el HTTPS) ^42d8ad

d. [[Elastic Compute Cloud|EC2]] 4 each site. custom deploy script. -- no, es la más costosa de todas; además, pide [[Static website w CI-CD#^448ae6|que no esté corriendo todo el tiempo]]

### Análisis

> [!note] Mi respuesta
> Creo que la [[Static website w CI-CD#^42d8ad|C]] es la más adecuada.
### Answer
A.