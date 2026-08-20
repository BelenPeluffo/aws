---
dudas: false
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 36 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103521-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] ¿[[CloudFormation]] stack set??
	[[CloudFormation#^88b804|Conjunto de stacks que se gestionan de forma centralizada]].
### Notas
- 
### Situación
one [[CloudFormation]] template 4 app & db. template used 2 deploy into != stgs

### Condiciones
- app deploy must not cause db 2 b dropped n' recreated
- avoid accidental db ==deletion==
- two options

### OPTS
a. CForm [[CloudFormation#^53e920|DeletionPolicy = Retain]] 4 the db ^359ce8

b. update CForm stack policy ^a916fc

c. modify db 2 use mAZ deploy -- ésta no porque no está pidiendo evitar accidental DATA LOSS sino accidental DELEITION ^118400

d. ??

e. CForm DeletionPolicy = Retain value 4 the stack -- no se puede aplicar directamente al stack, tenés que definirlo en cada recurso individual

### Análisis

> [!note] Mi respuesta
> [[CloudFormation r deletion protection#^359ce8|A]] y [[CloudFormation r deletion protection#^118400|C]]? 
### Answer
A y [[CloudFormation r deletion protection#^a916fc|B]].