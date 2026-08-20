---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 552 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/157448-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] Object Lock -- is this a thing??
- [ ] con la bucket policy se podría lograr ésto?
### Notas
- 
### Situación
A company stores data in an Amazon [[Simple Storage Service|S3]] bucket. The **data is updated multiple times every day** from an application that runs on a server in the company’s on-premises data center.  
  
The company enables S3 Versioning on the S3 bucket. After some time, the company observes multiple versions of the same objects in the S3 bucket.  
  
The company needs the S3 bucket to keep the current version of each object and the version immediately previous to the current version.  
  
Which solution will meet these requirements?

- A. Configure an S3 bucket policy to retain one newer noncurrent version of the objects.
- B. Configure an S3 Lifecycle rule to retain one newer noncurrent version of the objects.
- C. Enable S3 Object Lock. Configure an S3 Object Lock policy to retain one newer noncurrent version of the objects. -- is this a thing??
- D. Suspend S3 Versioning. Modify the application code to check the number of object versions before updating the objects. -- no
### Condiciones
- 

### OPTS
a.

### Análisis
B
> [!note] Mi respuesta
> 
### Answer
B