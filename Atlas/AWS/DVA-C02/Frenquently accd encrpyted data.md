---
dudas: false
tags:
aliases:
incorrecta:
---
Pregunta: 22
### Dudas
- [x] ¿Qué diferencia hay entre Redis y Memcached?
	Memcached tiene menos funcionalidad a la hora de sort y rank.
### Notas
- FAdata = frequently accessed data
### Situación
App 2 store personal health information. Encrypt'd [[Relational DB Service|RDS]] is storage.
### Condiciones
- PHI must b encrypt'd
- increase performance by caching FAdata
- sort & rank datasets

### OPTS
a. [[ElastiCache]] (Redis) 4 caching FAdata. Encrypt' @-rest & in-transit. ^2de664

b. ElastiCache (Memcached) 4 FAdata. ídem -- éste no porque tiene funcionalidades más reducidas para sort y rank ^50783a

c. RDS read-replica.

d. [[DynamoDB]] 4 FAdata and DAX.

### Análisis
Es una de las opciones con ElastiCache. Pero no sé cuál de las dos, supongo que el tema del sort y rank datasets es un giveaway, pero no sé la diferencia entre Redis y Memcached...
> [!note] Mi respuesta
> [[Frenquently accd encrpyted data#^2de664|A]] o [[Frenquently accd encrpyted data#^50783a|B]].
### Answer
A.