---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: UDEMY
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A development team at a social media company uses AWS [[Lambda]] functions for its serverless stack on AWS Cloud. For a new deployment, the Team Lead wants to send only a certain portion of the traffic to a new version of a Lambda function. In case the deployment goes wrong, the solution should also support the ability to roll back to a previous version of the Lambda function, with MIMINUM downtime for the application.

As a Developer Associate, which of the following options would you recommend to address this use-case?

- A. Set up the application to use an alias that points to the current version. Deploy the new version of the code and configure alias to send all users to this new version. If the deployment goes wrong, reset the alias to point to the current version
	- 
- B. Set up the application to directly deploy the new Lambda version. If the deployment goes wrong, reset the application back to the current version using the version number in the ARN
	- 
- C. Set up the application to have multiple alias of the Lambda function. Deploy the new version of the code. Configure a new alias that points to the current alias of the Lambda function for handling 10% of the traffic. If the deployment goes wrong, reset the new alias to point all traffic to the most recent working alias of the Lambda function
	Hay que leer con atención. Fijate que dice *configura a NEW ALIAS that points to the current ALIAS*. Un alias no puede apuntar a otro. Ahí está el issue.
- D. Set up the application to use an alias that points to the current version. Deploy the new version of the code and configure the alias to send 10% of the users to this new version. If the deployment goes wrong, reset the alias to point all traffic to the current version
	Ésta es más simple que la C. Lo que se hace es deployar la nueva versión pero no crear un alias. Y lo que hacés es crear un alias que apunte sólo a la más estable versión y lo modificás para que apunte también a esta nueva versión sólo en un 10%.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer