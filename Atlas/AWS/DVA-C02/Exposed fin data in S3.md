---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 104 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106987-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] Macie -- SensitiveData:S3Object/Financial finding type. -- is that a thing?
### Notas
- 
### Situación
A company stores its data in data tables in a series of Amazon [[Simple Storage Service|S3]] buckets. The company received an alert that customer credit card information might have been exposed in a data table on one of the company's public applications. A developer needs to identify all potential exposures within the application environment.  
  
Which solution will meet these requirements?

- A. Use Amazon [[Amazon Athena]] to run a job on the S3 buckets that contain the affected data. Filter the findings by using the SensitiveData:S3Object/Personal finding type.
- B. Use Amazon Macie to run a job on the S3 buckets that contain the affected data. Filter the findings by using the SensitiveData:S3Object/Financial finding type. -- is that a thing?
- C. Use Amazon Macie to run a job on the S3 buckets that contain the affected data. Filter the findings by using the SensitiveData:S3Object/Personal finding type.
- D. Use Amazon Athena to run a job on the S3 buckets that contain the affected data. Filter the findings by using the SensitiveData:S3Object/Financial finding type.
### Condiciones
- 

### OPTS
a.

### Análisis
Definitivamente es [[Amazon Macie|Macie]], porque se trata de PII y S3. Si B is a thing, then B; otherwise, C.
> [!note] Mi respuesta
> 
### Answer
B