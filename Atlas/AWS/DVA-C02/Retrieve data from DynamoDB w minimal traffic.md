---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 130 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/111831-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿qué diferencia hay entre A y C?
### Notas
- 
### Situación
A developer is working on a web application that uses Amazon [[DynamoDB]] as its data store. The application has two DynamoDB tables: one table that is named artists and one table that is named songs. The artists table has artistName as the partition key. The songs table has songName as the partition key and artistName as the sort key.  
  
The table usage patterns include the retrieval of multiple songs and artists in a single database operation from the webpage. The developer needs a way to retrieve this information with minimal network traffic and optimal application performance.  
  
Which solution will meet these requirements?

- A. Perform a BatchGetltem operation that returns items from the two tables. Use the list of songName/artistName keys for the songs table and the list of artistName key for the artists table.
- B. Create a local secondary index (LSI) on the songs table that uses artistName as the partition key. Perform a query operation for each artistName on the songs table that filters by the list of songName. Perform a query operation for each artistName on the artists table. -- mmm... me suena más cara, incluso aunque usa el LSI...
- C. Perform a BatchGetitem operation on the songs table that uses the songName/artistName keys. Perform a BatchGetltem operation on the artists table that uses artistName as the key.
- D. Perform a Scan operation on each table that filters by the list of songName/artistName for the songs table and the list of artistName in the artists table. -- una scan operation es la más cara porque tenés que leer 1 a 1 los registros
### Condiciones
- 

### OPTS
a.

### Análisis
No sé qué diferencia hay entre A y C, pero creo que voy por A porque hace una sola rq.
> [!note] Mi respuesta
> 
### Answer
A.