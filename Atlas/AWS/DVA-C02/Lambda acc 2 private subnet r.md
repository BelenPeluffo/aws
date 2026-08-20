---
dudas: false
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 40 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103523-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] [[security groups]] -- ¿qué onda lo in-bound y out-bound? hay alguno que es por defecto?
	[[security groups#^5d828e|Los out-bound]].
- [x] ídem -- ¿pueden pertenecer al mismo grupo recursos que están entre una subnet privada y pública? ¿cuáles son las constraints?
	Sí, porque son a nivel de instancia y VPC-bound los SG.
### Notas
- 
### Situación
[[Lambda]] 2 retrieve data from [[Amazon Aurora|Aurora]] in a [[private subnet]].
### Condiciones
- acc data securely

### OPTS
a. create Lambda. [[security groups|security group]] 4 both the lambda and the db. in-out TCP at 3306 -- ¿pueden estar dentro del mismo grupo si están en subnets distintas? Sí. ^3df049

b. Lambda in new public [[VPC]]. Peering between both VPCs. -- mucha config wtf

c. Lambda in same VPC. SG1 4 Lambda, SG2 4 db. in TCP 2 SG1 thru 3306 -- me parece que no porque las rq a la db serían inbound traffic hacia SG2, ¿o no? Correcto

d. (I won't dignify this answer with a question)

### Análisis
Instintivamente mi respuesta es [[Lambda acc 2 private subnet r#^3df049|A]], pero no estoy segura.
> [!note] Mi respuesta
> 
### Answer
A.