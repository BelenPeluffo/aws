---
dudas:
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 68 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106484-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company is building a **serverless** application that uses AWS [[Lambda]] functions. The company needs to create a set of **test events** to test Lambda functions in a development environment. The test events will be **created once** and then will be **used by all** the developers in an [[Identity and Access Management|IAM]] developer group. The test events must be **editable** by any of the IAM users in the IAM developer group.  
  
Which solution will meet these requirements?

- A. Create and store the test events in Amazon [[Simple Storage Service|S3]] as JSON objects. Allow S3 bucket access to all IAM users.
	-- allows 4 version control if needed ^83c1c7
	Acá lo que entra en juego es el tema de la EDITABILIDAD.
- B. Create the test events. Configure the event sharing settings to make the test events shareable. ^6cc0ad
	No especifica cómo implementarlo, que es el quid de la cuestión.
- C. Create and store the test events in Amazon [[DynamoDB]]. Allow access to DynamoDB by using IAM roles.
	-- faster than S3, but more expensive; use case: patterns 4 acc data
	Además, la config para habilitar la edición con least-privilege es más complicada.
- D. Create the test events. Configure the event sharing settings to make the test events private. ^05f24e
### Condiciones
- 

### OPTS
a.

### Análisis
O sea, me da la sensación de que [[Handling test events w Lambda#^6cc0ad|B]] y [[Handling test events w Lambda#^05f24e|D]] son total nonsense. Se me ocurre que almacenarlos en Dynamo sería lo mejor, porque se accedería rápido a la data. Pero el uso de roles vs el uso de Users de la opción [[Handling test events w Lambda#^83c1c7|A]] me confunde...
> [!note] Mi respuesta
> 
### Answer
[[Handling test events w Lambda#^83c1c7|A]].