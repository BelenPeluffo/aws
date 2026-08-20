---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 526 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/153619-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is building an application that will process messages from an Amazon [[Simple Queue Service]] (Amazon [[SQS]]) standard queue. The application needs to process the messages in an Amazon [[Elastic Container Service]] (Amazon [[ECS]]) task.  
  
Which actions will result in the MOST cost-effective processing of the messages? (Choose two.)

- A. Use long polling to query the queue for new messages.
	Ésta es más eficiente, pero me parece que es más costosa. Pero no sé si es más costosa que ElastiCache, por ejemplo...
- B. Use short polling to query the queue for new messages.
	Ésto generaría más llamadas, ¿o no?
- C. Use message batching to retrieve messages from the queue.
	Si existe ésta, quizás sea ésta.
- D. Use Amazon ElastiCache to cache messages in the queue.
	No sé si ésto agregará en costos...
- E. Use an [[Simple Queue Service|SQS]] FIFO queue to manage the messages.
	Creo que ésto no es necesario, porque no dice nada sobre FIFO. Además, ya en la consigna dice *standard q*.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer
A y C.
Era las dos en las que yo más creía, pero en comparación a ElastiCache no sé qué tan cost-effective era el long-polling. Y no sabía si C era a thing.