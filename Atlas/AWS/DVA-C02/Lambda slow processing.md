---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 56 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103932-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] iterator age metric -- ??
### Notas
KDS -- process --> Lambda
### Situación
A company is using an AWS [[Lambda]] function to process records from an  [[Kinesis Data Streams]]. The company recently observed slow processing of the records. A developer notices that the [[Kinesis Data Streams#^e8a40e|iterator age metric]] for the function is increasing and that the Lambda run duration is constantly above normal.  
### Condiciones
- Which actions should the developer take to increase the processing speed? (Choose two.)

### OPTS
- A. Increase the number of shards of the Kinesis data stream.
	-- para paralelizar los jobs
- B. Decrease the timeout of the Lambda function.
	-- no, porque no ayuda en nada a acelerar el proceso
- C. Increase the memory that is allocated to the Lambda function.
	-- aumentar capacidad de procesamiento
- D. Decrease the number of shards of the Kinesis data stream.
- E. Increase the timeout of the Lambda function.

### Análisis
B y C.
> [!note] Mi respuesta
> 
### Answer
A y C.