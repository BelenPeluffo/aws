---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#:~:text=C%20(100%25)-,Question%20%2315,-Topic%201
### Dudas
- [ ] OpsWorks -- ??
### Notas
- 
### Situación
[[Lambda]].

A developer is deploying an AWS Lambda function The developer wants the ability to return to older versions of the function quickly and seamlessly.  
How can the developer achieve this goal with the LEAST operational overhead?

- A. Use AWS OpsWorks to perform blue/green deployments.
- B. Use a function alias with different versions.
- C. Maintain deployment packages for older versions in Amazon S3.
- D. Use AWS CodePipeline for deployments and rollbacks.
### Condiciones
- needs 2 b able 2 return 2 older versions of fx
- least op overhead

### OPTS
a. [[OpsWorks]] 4 blue/green deploy -- ?

b. fx alias 4 different versions ^41d422

c. Store older vers in [[Simple Storage Service|S3]] -- tenés que cambiar la referencia a mano

d. [[Atlas/AWS/CodePipeline]] 4 deploy & rollback -- tenés que configurar la pipeline y correrla

### Análisis

> [!note] Mi respuesta
> [[Lambda version handling#^41d422|B]].
### Answer
B