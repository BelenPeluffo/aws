---
dudas: false
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 29 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/102903-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] ¿qué es KCL?
	[[Kinesis Data Streams#^KCL|Ver en nota]].
- [x] ¿cómo se controlan los volúmenes de rqs?
	Las requests de `PutRecords` las ejecuta la app producer que envía datos a KDS. La forma de controlar el tamaño/la cantidad de rqs es:
	- tamaño -- que en cada call vaya 1mb de data en vez de menos
	- cantidad -- podés bufferearlas o implementar código para que se emitan con un tiempo de diferencia
- [x] ¿lo del número de consumidores es viable?
	El número de consumidores se puede modificar, sí, pero no corresponde porque el problema es con `PutRecords`, una API consumida por los producers, no los consumers.
### Notas
- 
### Situación
Clickstream app usando [[Kinesis Data Stream]]. Hay períodos en los que el uso es muy alto de la nada, y en esos casos algunas llamadas con `PutRecords` fallan con el error code: `ProvisionedThroughputExceededException`.
### Condiciones
¿qué 2 técnicas ayudarían a resolver el error?

### OPTS
a. exponential backoff ^36196d

b. usar PutRecord en vez de PutRecords -- ésto sería peor, porque estamos usando `PutRecords` para poder enviar varios registros y así disminuir la cantidad de rqs. Usar `PutRecord` sería hacer lo contrario y empeorar el problema.

c. reducir freq/# de rqs ^79f371

d. usar [[SNS]] en vez de [[Kinesis Data Stream]]

e. reducir # de consumidores KCL -- no tiene injerencia sobre el error. `PutRecords` es una API que usa el producer, no el consumer ^159228

### Análisis

> [!note] Mi respuesta
> Para mí es definitivamente [[Fix KDSs ProvisionedThroughputErrorException#^36196d|A]] porque tiene que ver con que le están haciendo muchas requests. Y en esa línea, la segunda opción que se me viene es [[Fix KDSs ProvisionedThroughputErrorException#^79f371|C]] PERO ¿puede controlarse éso? Esa duda me lleva a considerar quizás [[Fix KDSs ProvisionedThroughputErrorException#^159228|E]] pero tengo la misma pregunta y, además, wtf is KCL???
### Answer
AC.