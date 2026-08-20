---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 545 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156701-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] sam local generate-event -- is this a thing?
### Notas
- 
### Situación
A company is using the AWS Serverless Application Model (AWS [[Serverless App Model|SAM]]) to develop a social media application. A developer needs a quick way to test AWS [[Lambda]] functions locally by using test event payloads. The developer needs the structure of these test event payloads to match the actual events that AWS services create.  
  
Which solution will meet these requirements with the LEAST development effort?

- A. Create shareable test Lambda events. Use these test Lambda events for local testing.
- B. Store manually created test event payloads locally. Use the sam local invoke command with the file path to the payloads.
- C. Store manually created test event payloads in an Amazon S3 bucket. Use the sam local invoke command with the S3 path to the payloads.
- D. Use the sam local generate-event command to create test payloads for local testing. -- is this our thing now??
### Condiciones
- 

### OPTS
a.

### Análisis
D
> [!note] Mi respuesta
> 
### Answer
D