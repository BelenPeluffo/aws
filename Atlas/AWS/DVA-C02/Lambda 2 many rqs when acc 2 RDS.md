---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 66 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107437-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
app -> API-GW -> Lambda
### Situación
A company has a **critical** application on AWS. The application exposes an HTTP API by using Amazon [[API Gateway]]. The API is integrated with an AWS [[Lambda]] function. The application stores data in an Amazon [[Relational DB Service|RDS]] for MySQL DB instance with 2 virtual CPUs (vCPUs) and 64 GB of RAM.  
  
Customers have reported that **some** of the API calls return HTTP **500 Internal Server Error** responses. Amazon [[CloudWatch Logs]] shows errors for “**too many connections**.” The errors occur during **peak usage times that are unpredictable**.  
  
The company needs to make the application **resilient**. **The database cannot be down outside of scheduled maintenance hours**.  
  
Which solution will meet these requirements?

- A. Decrease the number of vCPUs for the DB instance. Increase the max_connections setting.
- B. Use Amazon RDS Proxy to create a proxy that connects to the DB instance. Update the Lambda function to connect to the proxy.
	-- [[Lambda#^6822c1]] y [[RDS Proxy]] ^b8db2b
- C. Add a CloudWatch alarm that changes the DB instance class when the number of connections increases to more than 1,000.
- D. Add an Amazon EventBridge rule that increases the max_connections setting of the DB instance when CPU utilization is above 75%. ^60212c
	Cambiar el max_connections implica reiniciar la instancia. No can do.
### Condiciones
- 

### OPTS
a.

### Análisis
Yo creo que sería la [[Lambda 2 many rqs when acc 2 RDS#^60212c|D]], porque éso permitiría gestionar de forma automática en función del tráfico
> [!note] Mi respuesta
> 
### Answer
[[Lambda 2 many rqs when acc 2 RDS#^b8db2b|B]].