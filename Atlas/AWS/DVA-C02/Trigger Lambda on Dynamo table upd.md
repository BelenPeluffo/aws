---
dudas: false
tags:
  - database
  - serverless
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 46 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103917-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] [[DynamoDB]] streams??
	[[DynamoDB#^9aa407|Ver nota]].
	Se habilita a través de un campo de la tabla en la consola de AWS. Y se define como source en las configs de la [[Lambda]].
	Sobre el [[event mapping]] de [[Lambda]]: [[Lambda#^c87943|Ver nota]].
### Notas
- 
### Situación
[[Lambda]] 2 process any changes in [[DynamoDB]] table
### Condiciones
- what Lambda config 2 detect Dynamo changes?

### OPTS
a. [[Kinesis Data Streams]] attached 2 Dynamo. trigger 2 conn stream 2 Lambda.

b. [[EventBridge]] rule 2 invoke Lambda regularly

c. enable Dynamo streams and conn 2 Lambda. -- creo que ésta es la más lógica ^ca3cb9

d. [[Kinesis Data Firehose]] stream att 2 table  and destiny=Lambda

### Análisis
Creo que la [[Trigger Lambda on Dynamo table upd#^ca3cb9|C]] es la más lógica porque las de streams son overkill y la de cronjob con EB me parece que no. El tema es que no sé si existe éso de Dynamo Streams...
> [!note] Mi respuesta
> 
### Answer