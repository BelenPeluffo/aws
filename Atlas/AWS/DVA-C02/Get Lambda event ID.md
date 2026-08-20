---
dudas:
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 45 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103708-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
[[Lambda]]. Fx has params `event` y `context`.

A developer is writing an AWS Lambda function. The developer wants to log key events that occur while the Lambda function runs. The developer wants to include a unique identifier to associate the events with a specific function invocation. The developer adds the following code to the Lambda function:  
![](https://img.examtopics.com/aws-certified-developer-associate-dva-c02/image2.png "image2")  
Which solution will meet this requirement?

- A. Obtain the request identifier from the AWS request ID field in the context object. Configure the application to write logs to standard output.
- B. Obtain the request identifier from the AWS request ID field in the event object. Configure the application to write logs to a file.
- C. Obtain the request identifier from the AWS request ID field in the event object. Configure the application to write logs to standard output.
- D. Obtain the request identifier from the AWS request ID field in the context object. Configure the application to write logs to a file.

### Condiciones
- log key events during process
- include event ID

### OPTS
a. get rq ID from `context`. config app 2 write logs 2 standard output ^d05f50

b. get rq ID from `event`. config app 2 log into file. ^03ea74

c. get rq ID from `event`. config 2 log standard. ^61c8da

d. get rq ID from `context`. config 2 log into file.

### Análisis
Acá lo que me da duda es para qué quiere los logs. Si es sólo mientras corre, yo iría por el standard output y por lo tanto elegiría [[Get Lambda event ID#^61c8da|C]]. De lo contrario, [[Get Lambda event ID#^03ea74|B]].
> [!note] Mi respuesta
> 
### Answer
[[Get Lambda event ID#^d05f50|A]].