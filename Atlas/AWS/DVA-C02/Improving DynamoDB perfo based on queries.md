---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 71 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/106490-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] is "Scan ops" a thing??
- [ ] diferencias entre GSI y LSI -- conceptualmente y específicamente para este caso
### Notas
- 
### Situación
A developer is working on an existing application that uses Amazon [[DynamoDB]] as its data store. The DynamoDB table has the following attributes: partNumber (partition key), vendor (sort key), description, productFamily, and productType. When the developer analyzes the usage patterns, the developer notices that there are application modules that **frequently look** for a list of products **based on the productFamily and productType** attributes.  
  
The developer wants to make changes to the application to **improve performance** of the query operations.  
  
Which solution will meet these requirements?

- A. Create a global secondary index (GSI) with productFamily as the partition key and productType as the sort key. ^7300e5
- B. Create a local secondary index (LSI) with productFamily as the partition key and productType as the sort key.
- C. Recreate the table. Add partNumber as the partition key and vendor as the sort key. During table creation, add a local secondary index (LSI) with productFamily as the partition key and productType as the sort key.
- D. Update the queries to use Scan operations with productFamily as the partition key and productType as the sort key.
### Condiciones
- 

### OPTS
a.

### Análisis
Para mí es [[Improving DynamoDB perfo based on queries#^7300e5|A]].
> [!note] Mi respuesta
> 
### Answer