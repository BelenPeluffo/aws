---
dudas: true
tags:
aliases:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/#:~:text=8%25-,Question%20%232,-Topic%201
### Dudas
- [x] ¿Se puede configurar EC2 para mandar eventos a un lugar específico? ^83efa5
	No se puede. Sí o sí necesitás de un servicio que capture los eventos.
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
[[Elastic Compute Cloud|EC2]] en m-acc. Dev needs 2 collect lifecycle data from ALL instances.

### Condiciones
- events stored in main-acc [[SQS]] q

### OPTS
a. ^d1c509
- config EC2 2 deliver lifecycle evs 2 [[EventBridge]] in main-acc
- [[EventBridge]] rule 4 targeting main-acc q 2 send said events

b.
- [[Simple Queue Service|SQS]] r-policy 2 allow all acc 2 send events 2 it
- EventBridge in each acc, main-acc q as target

c.
- [[Lambda]] 4 scanning 4 said events
- Lambda sends notif 2 main-acc q
- EventBridge 4 scheduling the fx

d. ^cb7b83
- config permit 4 main-acc EventBridge 2 receive from all acc
- EventBridge in each acc 2 target lifecycle evs 2 main-acc EB
- main-acc EB target 2 main-acc q

### Análisis
Tendría directamente [[EventBridge]] en main-acc y apuntaría a todas las instancias a este nodo, que sería el que se encargaría de enviar al q.

Si [[Centralized queueing#^83efa5|la duda]] es sí => [[Centralized queueing#^d1c509|a]]. Si no => [[Centralized queueing#^cb7b83|d]].

> [!note] Mi respuesta
> D.
### Answer