---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 529 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156680-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is building an image-processing application that includes an AWS [[Lambda]] function. The Lambda function moves images from one AWS service to another AWS service for image processing. For images that are larger than 2 MB, the Lambda function returns the following error: “Task timed out after 3.01 seconds.”  
  
The developer needs to resolve the error without modifying the Lambda function code.  
  
Which solution will meet these requirements?

- A. Increase the Lambda function’s timeout value.
	Es ésta. 
- B. Configure the Lambda function to not move images that are larger than 2 MB.
- C. Request a concurrency quota increase for the Lambda function.
	El concurrency tiene que ver con el tiempo de procesamiento disponible para una lambda, no con el timeout.
- D. Configure provisioned concurrency for the Lambda function.
	Ésto tiene que ver con tener ya preparadas y andando algunas funciones, pero no soluciona el error de timeout.
### Condiciones
- 

### OPTS
a.

### Análisis
A
> [!note] Mi respuesta
> 
### Answer
A