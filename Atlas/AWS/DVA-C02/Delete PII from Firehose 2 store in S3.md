---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: 
### Dudas
- [ ] ¿qué es un delivery stream y qué tiene de diferente con [[Kinesis Data Streams|KDS]]?
### Notas
- 
### Situación
[[Kinesis Data Firehose]] recibe data con PII. En base a patrones hay que eliminar esos datos y almacenarlos transformados en un [[Simple Storage Service|S3]].

### Condiciones
- How?

### OPTS
a. data trans con [[Lambda]]. S3 as stream target. ^98b005

b. (won't dignify that answer w a q)

c. [[OpenSearch Service]] as target, use search&replace. Export 2 bucket. -- is it possible?

d. [[Step Functions]] y que uno de los steps sea eliminar la PII. último paso: store in bucket.

### Análisis
Para mí es la [[Delete PII from Firehose 2 store in S3#^98b005|A]].
> [!note] Mi respuesta
> 
### Answer
A.