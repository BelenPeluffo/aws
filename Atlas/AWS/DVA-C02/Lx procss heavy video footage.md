---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 542 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/156699-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] ENA -- ??
	Es un recurso que usa EC2 para mejorar la performance y velocidad de su conexión.
- [x] EBS está pensado para interactuar sólo con EC2?
	Sí.
- [x] ephemeral storage -- ??
	Es una prop de la config de Lambda. Se puede definir at create/upd time. Define el storage disponible en /temp.
### Notas
### Situación
A cloud-based video surveillance company is developing an application that analyzes video files. After the application analyzes the files, the company can discard the files.  
  
The company stores the files in an Amazon [[Simple Storage Service|S3]] bucket. The files are 1 GB in size on average. No file is larger than 2 GB. An AWS [[Lambda]] function will run one time for each video file that is processed. The processing is very I/O intensive, and the application must read each file multiple times.  
  
Which solution will meet these requirements in the MOST performance-optimized way?

- A. Attach an Amazon Elastic Block Store (Amazon [[Elastic Block Store|EBS]]) volume that is larger than 1 GB to the Lambda function. Copy the files from the S3 bucket to the EBS volume.
	¿Qué diferencia implicaría?
	Lambda no está hecha para interactuar con EBS :O
- B. Attach an Elastic Network Adapter (ENA) to the Lambda function. Use the ENA to read the video files from the S3 bucket.
	What
	Sirve para mejorar la performance pero de [[Elastic Compute Cloud|EC2]].
- C. Increase the ephemeral storage size to 2 GB. Copy the files from the S3 bucket to the /tmp directory of the Lambda function.
- D. Configure the Lambda function code to read the video files directly from the S3 bucket.
	Es probablemente lo que ya hace, ¿oder?
### Condiciones
- 

### OPTS
a.

### Análisis
B o D, pero no sé muy bien qué tiene que ver el tamaño de los archivos...
 - Lo que está pasando es que tenerlo en S3 quizás no es lo más performante.
- para mí, porque dice que se pueden desechar las imágenes, pienso que quizás en /tmp bastaría. Pero no recuerdo haber leído nada sobre ephemeral storage...
> [!note] Mi respuesta
> 
### Answer
C