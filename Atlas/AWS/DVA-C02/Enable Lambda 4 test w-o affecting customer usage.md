---
dudas: false
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 99 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/109229-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
API-GW -- alias --> Lambda
### Situación
A company has an AWS [[Lambda]] function that processes incoming requests from an Amazon [[API Gateway]] API. The API calls the Lambda function by using a Lambda alias. A developer updated the Lambda function code to handle more details related to the incoming requests. The developer wants to deploy the new Lambda function for more testing by other developers with **no impact to customers** that use the API.  
  
Which solution will meet these requirements with the **LEAST operational overhead**?

- A. Create a new version of the Lambda function. Create a new stage on API Gateway with integration to the new Lambda version. Use the new API Gateway stage to test the Lambda function.
	- Es ésta.
- B. Update the existing Lambda alias used by API Gateway to a weighted alias. Add the new Lambda version as an additional Lambda function with a weight of 10%. Use the existing API Gateway stage for testing.
	¿pero ésto no generaría que los users un 10% de las veces sean redirigidos a la lambda de testeo? 
	Sí, pero la idea es que los users de prod entren e interactúen y observar cómo se comporta la lambda. No afecta EL CÓDIGO de producción, éso es lo que importa.
- C. Create a new version of the Lambda function. Create and deploy a second Lambda function to filter incoming requests from API Gateway. If the filtering Lambda function detects a test request, the filtering Lambda function will invoke the new Lambda version of the code. For other requests, the filtering Lambda function will invoke the old Lambda version. Update the API Gateway API to use the filtering Lambda function.
	ésto es lo contrario de lo que piden
- D. Create a new version of the Lambda function. Create a new API Gateway API for testing purposes. Update the integration of the new API with the new Lambda version. Use the new API for testing.
	creo que ésto es innecesario porque existen STAGES en API-GW, right?
### Condiciones
- 

### OPTS
a.

### Análisis
La A me parece la más razonable...
> [!note] Mi respuesta
> 
### Answer
B