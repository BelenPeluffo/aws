---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 62 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/104016-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company has deployed an application on AWS [[Elastic Beanstalk]]. The company has configured the [[AutoScaling Group]] that is associated with the Elastic Beanstalk environment to have five Amazon [[Elastic Compute Cloud|EC2]] instances. If the capacity is fewer than four EC2 instances during the deployment, application performance degrades. The company is using the all-at-once deployment policy.  
What is the MOST **cost-effective** way to solve the deployment issue?

- A. Change the Auto Scaling group to six desired instances. -- no, porque igual cuando haga all@1 van a bajarse todas
- B. Change the deployment policy to traffic splitting. Specify an evaluation time of 1 hour. ^43e064
- C. Change the deployment policy to rolling with additional batch. Specify a batch size of 1. -- porque el *batch size* especifica la cantidad de instancias que se darán de baja al realizar el rolling => si son 5, se dará de baja 1 sola y poir lo tanto quedarán 4 (que es el mínimo que necesita la app para que esté alles gut) ^255ed9
- D. Change the deployment policy to rolling. Specify a batch size of 2. -- acá no sirve porque al dar de baja 2 instancias, de 5 quedan 3, y la app empieza a andar mal porque necesita como mínimo 4 para no autodestruirse ^304091
### Condiciones
- 

### OPTS
a.

### Análisis
Para mí es o [[ASG deployment strategy#^43e064|B]] o [[ASG deployment strategy#^304091|D]].
> [!note] Mi respuesta
> 
### Answer
C. El `batch` refiere al porcentaje de duplicación del grupo que queramos hacer a la hora de ejecutar el deploy rolling. Si el batch es de `1`, entonces se crearán 5 instancias nuevas hacia las que se dirigirá el tránsito y luego se darán de baja las 5 originales.