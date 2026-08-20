---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 85 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/108738-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] Lambda proxy intergration -- ??
- [ ] ¿qué diferencia hay entre C y D?
### Notas
- Quiero probar los cambios
- Quiero garantizar que durante los tests NO se deploye nada al env
### Situación
A company has a web application that is deployed on AWS. The application uses an Amazon [[API Gateway]] API and an AWS [[Lambda]] function as its backend.  
  
The application recently demonstrated **unexpected behavior**. A developer examines the Lambda function code, finds an error, and modifies the code to **resolve the problem**. Before deploying the change to production, the developer **needs to run tests** to validate that the application operates properly.  
  
The application has **only a production environment** available. The developer **must create a new development environment** to test the code changes. The developer must also prevent other developers from overwriting these changes during the test cycle.  
  
Which combination of steps will meet these requirements with the **LEAST development effort**? (Choose two.)

- A. Create a new resource in the current stage. Create a new method with Lambda proxy integration. Select the Lambda function. Add the hotfix alias. Redeploy the current stage. Test the backend.
	Entiendo que esta no, porque si nos está pidiendo que creemos un entorno de desarrollo, entonces ésto no se puede hacer.
- B. Update the Lambda function in the API Gateway API integration request to use the hotfix alias. Deploy the API Gateway API to a new stage named hotfix. Test the backend.
	Me da la sensación de que quizás ésta es una, ~~pero el phrasing me hace dudar...
	Aunque creo que lo que está queriendo decir es que a la misma lambda que hay que fixear la nombremos "hotfix". Y me parece que éso está mal...~~
- C. Modify the Lambda function by fixing the code. Test the Lambda function. Create the alias hotfix. Point the alias to the $LATEST version.
	~~Creo que ésta es la correcta.~~
	No es ésta porque al apuntar el alias a LATEST significa que si alguien más deploya a éste podría cambiar el código. Y la consigna nos pide que no permitamos que éso pase.
- D. Modify the Lambda function by fixing the code. Test the Lambda function. When the Lambda function is working as expected, publish the Lambda function as a new version. Create the alias hotfix. Point the alias to the new version.
	~~Necesitamos testearlo con users en un entorno que no sea local.~~
	¿O es ésta? ==publish as new version, create alias==
	Ésto hace lo mismo que la C, pero overkill.
- E. Create a new API Gateway API for the development environment. Add a resource and method with Lambda integration. Choose the Lambda function and the hotfix alias. Deploy to a new stage. Test the backend.
	==deploy 2 a new stage
	~~Ésta es una de las opciones. Porque CREÁS un nuevo entorno. Siempre que quieras tener versiones paralelas, tenés que crear un entorno distinto.~~
	~~Overkill. No es necesario crear una NUEVA API.~~
### Condiciones
- 

### OPTS
a.

### Análisis
D y E
> [!note] Mi respuesta
> 
### Answer
~~D y E~~
B y D