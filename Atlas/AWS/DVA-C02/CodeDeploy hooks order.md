---
dudas: false
tags:
aliases:
incorrecta: true
---
> [!note]
> Ni sabía la respuesta y [[CodeDeploy|en mis notas]] no tenía nada.

Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#:~:text=17-,Question%20%2317,-Topic%201
### Dudas
- [x] in-place deployments -- ?? existe otro tipo de deploy?? qué diferencia existe??
	A grandes rasgos, los tipos de deployments son **in-place** y **blue/green**. El **in-place** implica que para actualizar el código directamente se detiene la aplicación y se la reinicia una vez actualizado. Ésto significa que existirá un tiempo de inactividad. El **blue/green** permite tener dos entornos corriendo, uno con la versión anterior y otro con la nueva, para que mientras que la nueva se levanta la app siga estando disponible para los users.
### Notas
- 
### Situación
[[CodeDeploy]].
### Condiciones
- 

### OPTS
a. BeforeInstall -> AppStop -> AppStart -> AfterInstall -- AppStop es la primera

b. AppStop -> BeforeInstall -> AfterInstall -> AppStart ^7029c5

c. BeforeInstall -> AppStop -> ValidateService -> AppStart -- AppStop es la primera

d. AppStop -> BeforeInstall -> ValidateService -> AppStart -- AppStart va antes de ValidateService

### Análisis

> [!note] Mi respuesta
> [[CodeDeploy hooks order#^7029c5|B]].
### Answer
B.