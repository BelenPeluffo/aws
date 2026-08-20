---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#:~:text=B%20(100%25)-,Question%20%2313,-Topic%201
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
Food orders. Micro-s app. [[API Gateway|API-GW]] + [[Lambda]] 4 processing orders. 1 partner = 1 API from GW.

### Condiciones
- notify partners after own orders are processed
- when adding a new partner, b able 2 make the least changes possible
- as scalable as possible

### OPTS
a. 1 partner = 1 [[SNS]] topic. Lambda 4 publishing sms in x topic -- no, porque tenés que crear un topic por cada nuevo partner

b. 1 partner = 1 Lambda. Lambda notifies partner EP. -- ídem anterior

c. 1 topic 4 all. Lambda config'd 2 publish w x attr. Subscribe partners 2 topic with x filter policy. ^5061ca

d. 1 topic 4 all. -- le llegarían a todos todas las notificaciones

### Análisis

> [!note] Mi respuesta
> [[Data process state notification#^5061ca|C]].
### Answer
C.