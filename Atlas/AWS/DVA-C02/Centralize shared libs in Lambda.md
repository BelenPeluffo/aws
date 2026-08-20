---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 108 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107010-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] A is a thing?
- [ ] Leer más sobre las layers
### Notas
- 
### Situación
A developer is updating several AWS [[Lambda]] functions and notices that all the Lambda functions share the same custom libraries. The developer wants to centralize all the libraries, **update the libraries in a convenient way, and keep the libraries versioned**.  
  
Which solution will meet these requirements with the **LEAST development effort**?

- A. Create an AWS CodeArtifact repository that contains all the custom libraries. -- ¿se puede?
- B. Create a custom container image for the Lambda functions to save all the custom libraries. -- me parece que el container img es un overkill
- C. Create a Lambda layer that contains all the custom libraries.
- D. Create an Amazon Elastic File System (Amazon EFS) file system to store all the custom libraries. -- definitivamente no
### Condiciones
- 

### OPTS
a.

### Análisis
Para mí es C.
> [!note] Mi respuesta
> 
### Answer
C