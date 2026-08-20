---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 144 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/122562-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿de qué sirven las pre-signed URLs?
### Notas
- 
### Situación
A company has an Amazon [[Simple Storage Service|S3]] bucket containing premier content that it intends to make available to only paid subscribers of its website. The S3 bucket currently has default permissions of all objects being private to prevent inadvertent exposure of the premier content to non-paying website visitors.  
  
How can the company limit the ability to download a premier content file in the S3 bucket to paid subscribers only?

- A. Apply a bucket policy that allows anonymous users to download the content from the S3 bucket. -- justo lo contrario
- B. Generate a pre-signed object URL for the premier content file when a paid subscriber requests a download. -- creo que va por acá
- C. Add a bucket policy that requires multi-factor authentication for requests to access the S3 bucket objects. -- no es necesario, porque los unauth no tienen MFA
- D. Enable server-side encryption on the S3 bucket for data protection against the non-paying website visitors. -- no se trata de encriptación
### Condiciones
- 

### OPTS
a.

### Análisis
B
> [!note] Mi respuesta
> 
### Answer