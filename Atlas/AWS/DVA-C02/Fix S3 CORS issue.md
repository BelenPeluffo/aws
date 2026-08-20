---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 28 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/102902-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] ¿cómo se aplica el CORS al bucket?
	Según [[Simple Storage Service#^d01b3a|ésto]] es simplemente una propiedad del bucket. Bucket > Permissions > CORS config > insertás un JSON que defina los métodos y las URLs permitidas, entre otras cosas.
### Notas
- 
### Situación
A web app in [[Simple Storage Service|S3]] served via [[Atlas/AWS/CloudFront]]. Client wants 2 serve 3 more apps in different buckets each. Dev moves common JS and fonts 2 central bucket. The browser blocks this assets when trying 2 acc them.

### Condiciones
what should b done 2 fix it?

### OPTS
a. create 1 [[Simple Storage Service#^d640c2|acc point]] 4 each bucket 2 central bucket. -- no, porque tiene que ver con el acceso desde otros orígenes que se bloquea **a nivel de navegador** y no el acceso a los datos en sí

b. bucket policy 4 central bucket acc -- ídem, ésto gestiona el acceso a nivel de bucket, pero el bloqueo del problema es a nivel de navegador

c. CORS config 4 acc 2 central bucket -- hay algo anotado al respecto en [[Simple Storage Service#^d01b3a|S3]] ^fd2d35

d. (won't dignify that answer w a question)

### Análisis

> [!note] Mi respuesta
> [[Fix S3 CORS issue#^fd2d35|C]].
### Answer
C.