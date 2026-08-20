---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 61 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103904-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] [[Relational DB Service|RDS]] -- ¿se podrían guardar los reportes que pesen más de 1mb?
### Notas
- 
### Situación
A company is building a web application on AWS. When a customer sends a request, the application will generate reports and then make the reports available to the customer within one hour. Reports should be accessible to the customer for 8 hours. Some reports are larger than 1 MB. Each report is unique to the customer. The application should delete all reports that are older than 2 days.  
Which solution will meet these requirements with the LEAST operational overhead?

- A. Generate the reports and then store the reports as Amazon DynamoDB items that have a specified TTL. Generate a URL that retrieves the reports from DynamoDB. Provide the URL to customers through the web application. -- no porque [[DynamoDB]] acepta hasta 400kb
- B. Generate the reports and then store the reports in an Amazon [[Simple Storage Service|S3]] bucket that uses server-side encryption. Attach the reports to an [[SNS]]. Subscribe the customer to email notifications from Amazon SNS. -- no porque le falta la gestión de eliminación, además no sería menos ovearhead usar directamente [[Simple Email Service|SES]]?
- C. Generate the reports and then store the reports in an Amazon S3 bucket that uses server-side encryption. Generate a presigned URL that contains an expiration date Provide the URL to customers through the web application. Add S3 Lifecycle configuration rules to the S3 bucket to delete old reports. ^d15054
- D. Generate the reports and then store the reports in an Amazon RDS database with a date stamp. Generate an URL that retrieves the reports from the RDS database. Provide the URL to customers through the web application. Schedule an hourly AWS [[Lambda]] function to delete database records that have expired date stamps. -- no, porque probablemente requiere código importante en la Lambda; y correrla hourly costs $ $ $; y guardarlo en RDS es un overhead
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> [[Store objects w x TTL and expose them 2 usrs#^d15054|C]].
### Answer