---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/#:~:text=56-,Question%20%238,-Topic%201
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
[[API Gateway|API-GW]] accede a on-prem Linux server. [[Atlas/AWS/X-Ray]] activado en entorno de test.
### Condiciones
¿Cómo activar X-Ray con la menor config posible?

### OPTS
a. usar el SDK de X-Ray en los servers y pasar la data al s -- es posible, pero más complejo porque tenés que modificar tu app para que gestione la captura y envío de esos datos

b. instalar el daemon para hacer lo mismo -- si bien tenés que usar el SDK es menos la gestión en código ya que la app sólo se encarga de pasarle las trazas al daemon y éste las eleva a X-Ray ^eeb930

c. capturar data on-prem y configurar [[Lambda]] para que use la API `PutTraceSegments` de X-Ray -- posible pero más complejo porque requiere mucha config de Lambda

d. ídem pero usando la API `PutTelemetryRecords` -- ídem

### Análisis

> [!note] Mi respuesta
> Para mí es la [[X-Ray w on-prem server#^eeb930|B]].
### Answer
B.