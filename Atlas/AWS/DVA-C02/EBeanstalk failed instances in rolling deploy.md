---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: UDEMY
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
When running a Rolling deployment in [[Elastic Beanstalk]] environment, only two batches completed the deployment successfully, while rest of the batches failed to deploy the updated version. Following this, the development team terminated the instances from the failed deployment.

What will be the status of these failed instances post termination?

- a. Elastic Beanstalk will replace the failed instances with instances running the application version from the oldest successful deployment
	No, porque éso implicaría levantar instancias con la primera versión ever defined, por ejemplo. That is what *the oldest* means.
- b. Elastic Beanstalk will not replace the failed instances
	It must fill the capacity defined.
- c. Elastic Beanstalk will replace the failed instances with instances running the application version from the most recent successful deployment
	This is the one.
- d. Elastic Beanstalk will replace the failed instances after the application version to be installed is manually chosen from AWS Console
	- 
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer
C