---
dudas: true
tags:
aliases:
incorrecta: true
---
Pregunta: UDEMY
### Dudas
- [ ] env promotion -- ???
	Por lo general, se hace simplemente realizando un deploy con los cambios hacia el entorno de producción. Pero también puede hacerse a través de las variables de entorno.
### Notas
- 
### Situación
A development team has deployed a REST API in Amazon [[API Gateway]] to two different stages - a test stage and a prod stage. The test stage is used as a test build and the prod stage as a stable build. After the updates have passed the test, the team wishes to promote the test stage to the prod stage.

Which of the following represents the optimal solution for this use-case?

- A. Deploy the API without choosing a stage. This way, the working deployment will be updated in all stages
- B. Delete the existing prod stage. Create a new stage with the same name (prod) and deploy the tested version on this stage
- C. Update stage variable value from the stage name of test to that of prod
- D. API performance is optimized in a different way for prod environments. Hence, promoting test to prod is not correct. The promotion should be done by redeploying the API to the prod stage
### Condiciones
- 

### OPTS
a.

### Análisis
D
> [!note] Mi respuesta
> 
### Answer
C