---
dudas: true
tags:
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 145 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/122563-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] ¿qué diferencia hay entre que una prop sea partition key o sort key? ¿cómo éso encaja con GSI y LSI? ¿qué casos de usos tiene cada uno?
- [ ] qué significa que no quiera recrear la tabla? ¿que no quiere crear una nueva en que el customer_type sea la partition key?
### Notas
`email_addres` YA es partition key
### Situación
A developer is creating an AWS [[Lambda]] function that searches for items from an Amazon [[DynamoDB]] table that contains customer contact information. The DynamoDB table items have the customer’s email_address as the partition key and additional properties such as customer_type, name and job_title.  
  
The Lambda function runs whenever a user types a new character into the customer_type text input. The developer wants the search to return partial matches of all the email_address property of a particular customer_type. The developer does not want to recreate the DynamoDB table.  
  
What should the developer do to meet these requirements?

- A. Add a global secondary index (GSI) to the DynamoDB table with customer_type as the partition key and email_address as the sort key. Perform a query operation on the GSI by using the begins_with key condition expression with the email_address property.
- B. Add a global secondary index (GSI) to the DynamoDB table with email_address as the partition key and customer_type as the sort key. Perform a query operation on the GSI by using the begins_with key condition expression with the email_address property.
- C. Add a local secondary index (LSI) to the DynamoDB table with customer_type as the partition key and email_address as the sort key. Perform a query operation on the LSI by using the begins_with key condition expression with the email_address property.
- D. Add a local secondary index (LSI) to the DynamoDB table with job_title as the partition key and email_address as the sort key. Perform a query operation on the LSI by using the begins_with key condition expression with the email_address property.
### Condiciones
- 

### OPTS
a.

### Análisis
Supongo que debería ser GSI porque es lo que se espera de la app y siempre tendrá ese comportamiento en base a customer_type. Por lo que we're down 2 A or B. Y como ya naturalmente la tabla tiene a email_address como primary key, entonces queremos que el GSI tenga a customer_type como primary y por lo tanto debería ser A.
> [!note] Mi respuesta
> 
### Answer
A