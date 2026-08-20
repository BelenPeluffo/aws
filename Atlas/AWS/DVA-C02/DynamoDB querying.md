---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#:~:text=13-,Question%20%2320,-Topic%201
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
Movie DB. Each movie has some shared props and some are not.
### Condiciones
Query cases
- x title & x release year => all details of movie with exact title & date
- x title => all details of all movies 2 that title
- x genre => all details of all movies 2 that genre

### OPTS
a. [[DynamoDB]]. Primary key = title (partition key) + year (sort key). GSI = genre (partition) + year (sort). ^6349db

b. Dynamo. Primary key = genre (partition) + year (sort). GSI = title (partition)

c. [[Relational DB Service|RDS]]. Columns 4 title, release y genre. Primary key = title ^6b140f

d. RDS. Primary key = title, rest of props is a JSON on another single column ^f8c2b0

### Análisis
Ya de por sí como hay propiedades que no se comparten por todos los registros, las opciones relacionadas a RDS ([[DynamoDB querying#^6b140f|c]] y [[DynamoDB querying#^f8c2b0|d]]) no van.
> [!note] Mi respuesta
> [[DynamoDB querying#^6349db|A]] porque tiene juntos los datos cuya query requiere que se traiga un único resultado que tenga ambos valores definidos para cada una.
### Answer
A.