---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 530 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156681-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer has an application container, an AWS [[Lambda]] function, and an Amazon [[Simple Queue Service]] (Amazon [[SQS]]) queue. The Lambda function uses the [[Simple Queue Service|SQS]] queue as an event source. The Lambda function makes a call to a third-party machine learning API when the function is invoked. The response from the third-party API can take up to 60 seconds to return.  
  
The Lambda function's timeout value is currently 65 seconds. The developer has noticed that the Lambda function sometimes processes duplicate messages from the [[Simple Queue Service|SQS]] queue.  
  
What should the developer do to ensure that the Lambda function does not process duplicate messages?

- A. Configure the Lambda function with a larger amount of memory.
	Si bien ésto podría acelerar los tiempos de procesamiento de los mensajes y acortar el tiempo entre el procesado de uno y otro, no necesariamente soluciona el error de que se vuelva visible el mensaje.
- B. Configure an increase in the Lambda function’s timeout value.
	Es que no tiene que ver con el timeout value sino con [[Simple Queue Service|SQS]].
- C. Configure the [[Simple Queue Service|SQS]] queue’s delivery delay value to be greater than the maximum time it takes to call the third-party API.
	Éste no, porque... no jaja
- D. Configure the [[Simple Queue Service|SQS]] queue’s visibility timeout value to be greater than the maximum time it takes to call the third-party API.
	Es éste. La visibility lo que hace es esconder el mensaje mientras todavía está siendo procesado. Se le settea un período de gracia. Pasado ese período, se vuelve visible y 
### Condiciones
- 

### OPTS
a.

### Análisis
D
> [!note] Mi respuesta
> 
### Answer
D