---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 65 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103686-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is building a new application on AWS. The application uses an AWS [[Lambda]] function that retrieves information from an Amazon [[DynamoDB]] table. The developer hard coded the DynamoDB table name into the Lambda function code. The table name might change over time. The developer does not want to modify the Lambda code if the table name changes.  
Which solution will meet these requirements MOST efficiently?

- A. Create a Lambda environment variable to store the table name. Use the standard method for the programming language to retrieve the variable. ^8732c6
- B. Store the table name in a file. Store the file in the /tmp folder. Use the SDK for the programming language to retrieve the table name.
- C. Create a file to store the table name. Zip the file and upload the file to the Lambda layer. Use the SDK for the programming language to retrieve the table name.
- D. Create a global variable that is outside the handler in the Lambda function to store the table name.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> [[Set Lambda var w changing code#^8732c6|A]].
### Answer