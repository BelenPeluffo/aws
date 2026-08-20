---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 137 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/117331-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿qué diferencia hay entre A y B?
### Notas
- 
### Situación
A company is developing a **serverless** multi-tier application on AWS. The company will build the serverless logic tier by using Amazon [[API Gateway]]and AWS [[Lambda]].  
While the company builds the logic tier, a developer who works on the frontend of the application must develop integration tests. The tests must cover both positive and negative scenarios, depending on success and error HTTP status codes.  
  
Which solution will meet these requirements with the **LEAST effort**?

- A. Set up a mock integration for API methods in API Gateway. In the integration request from Method Execution, add simple logic to return either a success or error based on HTTP status code. In the integration response, add messages that correspond to the HTTP status codes.
- B. Create two mock integration resources for API methods in API Gateway. In the integration request, return a success HTTP status code for one resource and an error HTTP status code for the other resource. In the integration response, add messages that correspond to the HTTP status codes. -- creo que con un solo mock integration está bien
- C. Create Lambda functions to perform tests. Add simple logic to return either success or error, based on the HTTP status codes. Build an API Gateway Lambda integration. Select appropriate Lambda functions that correspond to the HTTP status codes.
- D. Create a Lambda function to perform tests. Add simple logic to return either success or error-based HTTP status codes. Create a mock integration in API Gateway. Select the Lambda function that corresponds to the HTTP status codes.
### Condiciones
- 

### OPTS
a.

### Análisis
A?
> [!note] Mi respuesta
> 
### Answer
A