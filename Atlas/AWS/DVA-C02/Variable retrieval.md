---
dudas: false
tags:
aliases:
incorrecta:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/#:~:text=A%20(100%25)-,Question%20%2310,-Topic%201
### Dudas
- [x] ¿por qué hace referencia a lo de que esté disponible para las distintas versiones del código?
	Porque está apuntando a que no impacte de forma diferente entre los diferentes entornos. Que la solución implique el uso del mismo código en todos los ambientes.
### Notas
- 
### Situación
App in [[ECS]]. Needs env var storage. Vars = { auth info }

### Condiciones
- secure storage
- var data must b available for current/future app versions in all envs
- fewest app changes ==between envs==

### OPTS
a. vars en [[SSM Parameter Store]], creds en [[Secrets Manager]] -- me parece que es la más secure, ~~pero no sé si es a que implica menos cambios porque en la app vas a tener que implementar código para hacer las llamadas a las APIs (en este caso, 2)~~ permite la centralización de los valores para todos los entornos ^2ceaa3

b. vars en [[Key Management Service|KMS]] -- KMS es para encriptado, no guardado

c. var en encrypt'd file en app -- necesitarías implementar código para desencriptarlo, o no? (correcto)

d. vars en env vars de task -- no sé qué tanto hay que modificar el código para que tome las variables según el .env de la task...  (debería settearse para cada ambiente, que es lo que no se quiere) ^afdc54

### Análisis

> [!note] Mi respuesta
> Para mí está entre [[Variable retrieval#^afdc54|D]] y [[Variable retrieval#^2ceaa3|A]]...
### Answer
A.