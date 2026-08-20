---
dudas: true
tags:
  - storage
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 23 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/102900-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] EBS & Instance Store -- ¿cómo harías para compartir las files?
	Se anexa el volumen a la instancia y a la instancia se le tiene que instalar un sys de archivos compartido. Por ejemplo, para Windows existe SMB.
	- ¿cómo se usa ese sys y en qué consiste?
- [ ] Cost comparison entre todas las opciones de almacenamiento
- [x] micro-instancia -- ??
	Es una instancia con menores capacidades.
	- ¿cómo se configura?
		Al dar de alta la instancia, cuando elegís cualquier instancia que pertenezca a la clase `*.micro`.
- [x] montaje local de S3 -- ??
	Implica conectar S3 con el OS de forma que se pueda acceder a él como a un sistema de archivos normal. Entiendo que se puede con instancias con Linux... O al menos para poder usar la herramienta S3FS
	- ¿sólo se puede con instancias con Linux?
		S3FS, sí. Para Windows tenés otras herramientas.
### Notas
- 
### Situación
Multi-node Windows server on-prem. Network folder for .xml config files. Migration of app 2 [[Elastic Compute Cloud|EC2]].

### Condiciones
- How 2 make repo highly available?
- most cost-efficient

### OPTS
a. [[Elastic Block Store|EBS]] 2 one of the EC2s w file sys. share folder. upd app 2 read/write files in this folder. -- ésta creo que no es highly-available porque es AZ-bound...

b. EC2 w [[EC2 Instance Storage]]. share this folder. ídem. -- me parece que ésta es la más barata, porque el instance storage viene por defecto; PERO creo que no es highly-available porque [[EC2 Instance Storage#^6f9836|es volátil]] ^131e94

c. [[Simple Storage Service|S3]] 4 repo of files. upd app 2 read/write in bucket. -- ésta me parece la más highly-available pero no sé si la más cost-efficient... ^83a923

d. Create an Amazon S3 bucket to host the repository. Migrate the existing .xml files to the S3 bucket. Mount the S3 bucket to the EC2 instances as a local volume. Update the application code to read and write configuration files from the disk. -- is this even possible?

### Análisis
Para mí estamos entre la [[Migración de on-prem a cloud filesys#^83a923|C]] y la [[Migración de on-prem a cloud filesys#^131e94|B]]. Pero siento que
> [!note] Mi respuesta
> C.
### Answer
C.