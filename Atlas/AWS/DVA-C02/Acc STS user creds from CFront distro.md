---
dudas: false
tags:
  - security
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 102 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106981-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] CFront fx -- is that a thing??? ✅ 2026-08-07
	It is.
### Notas
- 
### Situación
A social media application uses the AWS [[Atlas/AWS/SDK]] for JavaScript on the frontend to get user credentials from AWS Security Token Service (AWS [[Security Token Service|STS]]). The application stores its assets in an Amazon [[Simple Storage Service|S3]] bucket. The application serves its content by using an Amazon [[CloudFront]] distribution with the origin set to the S3 bucket.  
  
The credentials for the role that the application assumes to make the SDK calls are stored in plaintext in a JSON file within the application code. The developer needs to implement a solution that will allow the application to get ==user credentials== **without having any credentials hardcoded** in the application code.  
  
Which solution will meet these requirements?

- A. Add a [[Lambda#^8f52e7|Lambda@Edge]] function to the distribution. Invoke the function on viewer request. Add permissions to the function's execution role to allow the function to access AWS STS. Move all SDK calls from the frontend into the function.
- B. Add a CloudFront function to the distribution. Invoke the function on viewer request. Add permissions to the function's execution role to allow the function to access AWS STS. Move all SDK calls from the frontend into the function.
	O sea, para mí ésta es una posibilidad. Más que nada porque me parece que es un proceso no muy complejo de codificar. Es usar el SDK para hacer las llamadas a STS y listo; pero creo que las funciones de CF no pueden hacer éso... ==No, no pueden==.
- C. Add a Lambda@Edge function to the distribution. Invoke the function on viewer request. Move the credentials from the JSON file into the function. Move all SDK calls from the frontend into the function.
	- -- ésto es lo mismo: sigue hardcodeada
- D. Add a CloudFront function to the distribution. Invoke the function on viewer request. Move the credentials from the JSON file into the function. Move all SDK calls from the frontend into the function.
	- -- ídem
### Condiciones
- 

### OPTS
a.

### Análisis
Es A o B, pero no tengo ni idea...
> [!note] Mi respuesta
> 
### Answer
A