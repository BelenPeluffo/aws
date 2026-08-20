---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 74 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106711-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] VPC EP -- ¿dónde entra en juego en su conexión con Lambda? Lambda en VPC usa [[NAT]] para conectarse al [[IGW]] y la ENI para conectarse a los rr de la [[private subnet]]. ¿Y el VPC EP?
	Se usa para conn Lambda en VPC a ss de AWS que no están deployados en VPC y con los cuales necesita conn de forma privada.
- [ ] ¿Qué diferencia hay entre las cuatro opciones?
### Notas
- 
### Situación
A developer created an AWS [[Lambda]] function that accesses resources in a VPC. The Lambda function polls an Amazon [[Simple Queue Service]] (Amazon [[SQS]]) queue for new messages through a [[VPC EP]]. Then the function calculates a rolling average[^1] of the numeric values that are contained in the messages. After initial tests of the Lambda function, the developer found that the value of the rolling average that the function returned was not accurate.  

How can the developer ensure that the function calculates an accurate rolling average?

- A. Set the function's [[Lambda#^e1d0bb|reserved concurrency]] to 1. Calculate the rolling average in the function. Store the calculated rolling average in Amazon ElastiCache.
	Disminuyendo la reserva no solucionás el problema y además generás un cuello de botella.
- B. Modify the function to store the values in Amazon ElastiCache. When the function initializes, use the previous values from the cache to calculate the rolling average.
	- Ésta es la mejor manera.
- C. Set the function's [[Lambda#^a2f1fb|provisioned concurrency]] to 1. Calculate the rolling average in the function. Store the calculated rolling average in Amazon ElastiCache.
	Provisioned no tiene uso en este caso, porque es el número de instancias que querés tener listas para correr.
- D. Modify the function to store the values in the function's layers. When the function initializes, use the previously stored values to calculate the rolling average.
	Las layers no persisten datos entre invocaciones. Además, no es un buen método de almacenamiento para este caso de uso.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer
B.

[^1]: *Rolling average* es el promedio entre los mensajes más actuales. Suponete que es el promedio calculado siempre entre los últimos tres mensajes más nuevos, por ejemplo.
