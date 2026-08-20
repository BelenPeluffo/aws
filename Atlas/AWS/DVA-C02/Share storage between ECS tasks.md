---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 533 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156683-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is deploying an application on an Amazon [[Elastic Container Service]] (Amazon [[ECS]]) cluster that uses AWS [[Atlas/AWS/Fargate]]. The developer is using a Docker container with an Ubuntu image.  
  
The developer needs to implement a solution to store application data that is available from multiple [[Elastic Container Service|ECS]] tasks. The application data must remain accessible after the container is terminated.  
  
Which solution will meet these requirements?

- A. Attach an Amazon FSx for Windows File Server volume to the container definition.
	No, porque dijo *ubuntu*.
- B. Specify the DockerVolumeConfiguration parameter in the [[Elastic Container Service|ECS]] task definition to attach a Docker volume.
	~~Mmm... ésta podría ser... ?~~ No, porque el storage en este caso es volátil.
- C. Create an Amazon Elastic File System (Amazon [[Elastic File System|EFS]]) file system. Specify the mountPoints attribute and the efsVolumeConfiguration attribute in the [[Elastic Container Service|ECS]] task definition.
	Me parece que es mucho, o no?
- D. Create an Amazon Elastic Block Store (Amazon [[Elastic Block Store|EBS]]) volume. Specify the mount point configuration in the [[Elastic Container Service|ECS]] task definition.
	~~Yo creo que es ésta.~~ Como es Fargate y el EBS está más naturalmente asociado a [[Elastic Compute Cloud|EC2]], no conviene. Los volúmenes no podrán ser asociados a otras tasks y the will b rendered inaccessible when underlying EC2 es dada de baja.
### Condiciones
- 

### OPTS
a.

### Análisis
D
> [!note] Mi respuesta
> 
### Answer
C