---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 98 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/109646-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] se puede montar un EFS en una Lambda??
### Notas
- 
### Situación
A developer is creating an AWS [[Lambda]] function in VPC mode. An Amazon [[Simple Storage Service|S3]] event will invoke the Lambda function when an object is uploaded into an S3 bucket. The Lambda function will process the object and produce some analytic results that will be recorded into a file. Each processed object will also generate a log entry that will be recorded into a file.  
  
Other Lambda functions, AWS services, and on-premises resources **must have access to the result files and log file**. Each log entry must also be appended to the same shared log file. The developer needs a solution that can **share files and append results into an existing file**.  
  
Which solution should the developer use to meet these requirements?

- A. Create an Amazon Elastic File System (Amazon [[Elastic File System|EFS]]) file system. Mount the EFS file system in Lambda. Store the result files and log file in the mount point. Append the log entries to the log file.
- B. Create an Amazon Elastic Block Store (Amazon [[Elastic Block Store|EBS]]) Multi-Attach enabled volume. Attach the EBS volume to all Lambda functions. Update the Lambda function code to download the log file, append the log entries, and upload the modified log file to Amazon EBS. -- mmm... me parece que esta es ficticia...
- C. Create a reference to the /tmp local directory. Store the result files and log file by using the directory reference. Append the log entry to the log file. -- éste es temporal, pero me da la sensación de que necesitamos algo que persista...
- D. Create a reference to the /opt storage directory. Store the result files and log file by using the directory reference. Append the log entry to the log file. -- ????
### Condiciones
- 

### OPTS
a.

### Análisis
Me parece que es A.
> [!note] Mi respuesta
> 
### Answer
A