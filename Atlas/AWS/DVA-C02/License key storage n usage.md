---
dudas: false
tags:
  - secrets-storage
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 39 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103913-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] [[CloudFormation]] -- `NoEcho` param -- ???
	[[CloudFormation#^22071e|Parameters.NoEcho]].
### Notas
- 
### Situación
1-time fixed license keys 2 mange in AWS.
### Condiciones
- acc key from [[Elastic Compute Cloud|EC2]] and [[CloudFormation]] stacks
- most cost-effective

### OPTS
a. [[Simple Storage Service|S3]] w config encrypt'd files -- me parece que es más caro de lo necesario

b. [[Secrets Manager]] w `SecretString` tag -- ídem y además es over-kill, creo, porque tenés toda la otra funcionalidad de rotación y demás que no lo vas a usar

c. [[SSM Parameter Store]] `SecureString` param -- me parece la más tranqui y además con [[SSM Parameter Store#^f64ae1|SecureString se habilita el cifrado]] ^0c7854

d. CForm `NoEcho` param -- creo que no va porque también necesito acceder a las keys desde EC2 que no sé si están definidas en el stack

### Análisis
Creo que porque dice 1-time, yo iría por [[License key storage n usage#^0c7854|C]] porque no necesito rotar ni nada.
> [!note] Mi respuesta
> 
### Answer