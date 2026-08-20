---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 50 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103619-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] [[API Gateway|API-GW]] -- proxy integration?? ✅ 2026-08-06
	Creo que se refiere a [[API Gateway#^1e86da|ésto]].
- [ ] ¿rta typ en base a la rq?
### Notas
- 
### Situación
Mobile app calls BE on [[API Gateway|API-GW]].

A developer is creating a mobile app that calls a backend service by using an Amazon API Gateway REST API. For integration testing during the development phase, the developer wants to simulate different backend responses without invoking the backend service.  
Which solution will meet these requirements with the LEAST operational overhead?

- A. Create an AWS Lambda function. Use API Gateway proxy integration to return constant HTTP responses.
	~~Creo que ésta no haría absolutamente nada. Porque el proxy integration lo único que hace es hacer pasamanos de las rqs y las rtas. Y lo que queremos es mockear rtas del BE.~~
	Es overkill, porque estarías creando lambdas que devuelvan rtas fijas, cosa que podés hacer más simplemente con el mapping template.
- B. Create an Amazon EC2 instance that serves the backend REST API by using an AWS CloudFormation template.
	Overkill y encima te sale un fangote de guita.
- C. Customize the API Gateway stage to select a response type based on the request.
	¿Se puede hacer ésto?
- D. Use a request mapping template to select the mock integration response.
### Condiciones
- simulate != BE rtas
- no BE s invoke'
- least op overhead

### OPTS
a. [[Lambda]] that will b called by GW

b. [[Elastic Compute Cloud|EC2]] 2 run BE. Use [[CloudFormation]] 2 define instance.

c. custom' [[API Gateway|API-GW]] 2 sel rta type based on rq ^08b7bb

d. rq mapping template 2 sel ==mock integration== rta ^7bb26d

### Análisis
Yo creo que implementamos [[Mock rtas w API-GW#^08b7bb|C]], pero ¿es posible [[Mock rtas w API-GW#^7bb26d|D]]? [[API Gateway#^144d15|Sí, es posible]].
> [!note] Mi respuesta
> C.
### Answer
D.