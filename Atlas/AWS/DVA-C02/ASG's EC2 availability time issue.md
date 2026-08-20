---
dudas: true
tags:
  - auto-scaling
aliases:
incorrecta: true
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 47 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103721-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] [[Elastic Compute Cloud|EC2]] Image Builder -- ??
### Notas
- 
### Situación
[[Elastic Compute Cloud|EC2]]'s [[AutoScaling Group]] where EC2s load when scaling delayed by [[Elastic Compute Cloud#^14430b|User Data]].
### Condiciones
- decrease load time ^c1cf6e
- most recent app version available at all times ^f93431
- apply all available sec upd ^073123
- minimum # imgs ^c3ecd4
- imgs must b valid'd ^a22899
- two options

### OPTS
a. [[EC2 Image Builder]] 2 create [[Amazon Machine Image|AMI]]. install n upd. upd [[AutoScaling Group|ASG]] 2 use that AMI. -- al crear una AMI a partir de una imagen de EC2 se evita tener que descargar cosas a la hora de dar de alta una instancia en base a esa AMI ^63a217

b. ídem. install app, upd patches. ASG ídem. -- no, hacer ésto no cumpliría con el requisito del [[ASG's EC2 availability time issue#^c3ecd4|# de imgs]], porque deberías crear una imagen por cada nueva ver de la app... ^d30ad5

c. [[CodeDeploy]] 2 deploy latest app ver ^979c5f

d. [[Atlas/AWS/CodePipeline]] ídem ^b14408

e. Remove commands 4 OS patching in [[Elastic Compute Cloud#^14430b|UserData]] ^46ab53

### Análisis
Para mí son [[ASG's EC2 availability time issue#^d30ad5|B]] y [[ASG's EC2 availability time issue#^46ab53|E]]... Pero el tema es que no sé. Estoy re segura de E porque necesitamos [[ASG's EC2 availability time issue#^c1cf6e|reducir load time]], pero de B no tanto... El tema es que si no es B, lo que se me ocurre es [[ASG's EC2 availability time issue#^63a217|A]] y [[ASG's EC2 availability time issue#^979c5f|C]] para suplir por el tema de [[ASG's EC2 availability time issue#^f93431|latest app ver]] y [[ASG's EC2 availability time issue#^073123|sec upds]]... Pero el tema de la [[ASG's EC2 availability time issue#^a22899|validación de las imgs]] me confunde y me hace pensar en [[ASG's EC2 availability time issue#^b14408|D]]...
> [!note] Mi respuesta
> 
### Answer
A y C.