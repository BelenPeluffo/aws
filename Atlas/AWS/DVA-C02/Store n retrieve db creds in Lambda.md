---
dudas: false
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 549 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/157490-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] ¿por qué es más seguro acceder at runtime que tener una env var ~~que refiera a la ARN del secreto~~? ¿qué diferencia habría a nivel de código?
	Con [[Secrets Manager]] NO se usan env vars. Se obtienen los secretos haciendo una llamada con el SDK.
- [x] ¿qué diferencia tiene que se acceda a través de env o at runtime? ¿at runtime no tiene igual que acceder a través de envs?
	Las variables de entorno que usan las app por lo general son cosas como `DB_PASSWORD` y demás. Justamente los valores de esas variables son los datos que se almacenan en SM. En el código, nosotrxs normalmente traemos ese valor desde la variable de entorno. Como ahora lo hacemos desde SM, lo que cambia es el código: en vez de retrieve desde el env, retrieves desde SM at runtime.
### Notas
- 
### Situación
A developer is building an application that consists of many AWS [[Lambda]] functions. The Lambda functions connect to a single Amazon [[Relational DB Service|RDS]] database.  
  
The developer needs to implement a solution to store the **database credentials securely**. When the credentials are updated, the Lambda functions must be able to use the new credentials without requiring a code update or a configuration update.  
  
Which solution will meet these requirements?

- A. Store the credentials as a secret in AWS [[Secrets Manager]]. Access the secret at runtime from within the Lambda functions.
- B. Store the credentials as a secret in AWS Secrets Manager. Access the credentials in environment variables by using the `containerDefinitions` and `valueFrom` elements in reference to the secret value.
	Que me diga que hay que hacer referencia al containerDef y el valueFrom me da duda... Porque me da la sensación de que entonces tengo que actualizar el código...
	Agrega más complejidad.
	Además: `containerDefinitions` es de[[ECS]], no de Lambda.
	Además, exponer el ARN no sería lo más safe.
- C. Store the credentials as a `SecureString` parameter in AWS Systems Manager [[SSM Parameter Store]]. Add a trigger to pass the credentials to the Lambda functions when the Lambda functions run.
	No se pueden obtener vars de esta forma en Lambda.
- D. Store the credentials as a `SecureString` parameter in AWS Systems Manager Parameter Store. Add a reference to the parameter in an environment variable in the Lambda functions.
	Ésto sí se puede hacer. Porque en definitiva tenés que implementar el código del SDK como en A PERO entre SM y PS cuando se trata de secrets, gana SM.
### Condiciones
- 

### OPTS
a.

### Análisis
Es either A o B. Creo que B, porque hay más capas intermedias...
> [!note] Mi respuesta
> 
### Answer
A