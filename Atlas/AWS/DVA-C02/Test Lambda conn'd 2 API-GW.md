---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 131 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/111832-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company is developing an ecommerce application that uses Amazon [[API Gateway]] APIs. The application uses AWS [[Lambda]] as a backend. The company needs to test the code in a dedicated, monitored test environment before the company releases the code to the production environment.  
  
Which solution will meet these requirements?

- A. Use a single stage in API Gateway. Create a Lambda function for each environment. Configure API clients to send a query parameter that indicates the environment and the specific Lambda function.
- B. Use multiple stages in API Gateway. Create a single Lambda function for all environments. Add different code blocks for different environments in the Lambda function based on Lambda environment variables.
- C. Use multiple stages in API Gateway. Create a Lambda function for each environment. Configure API Gateway stage variables to route traffic to the Lambda function in different environments.
- D. Use a single stage in API Gateway. Configure API clients to send a query parameter that indicates the environment. Add different code blocks for different environments in the Lambda function to match the value of the query parameter.
### Condiciones
- 

### OPTS
a.

### Análisis
Son sí o sí B o C, por los multiple-stages. C, porque no vamos a usa una y agregarle blocks dependiendo del ambiente.
> [!note] Mi respuesta
> 
### Answer
C