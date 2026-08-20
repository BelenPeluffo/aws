- security groups -- 2 control net acc
	- [[Key Management Service|KMS]] -- @ rest vol encrypt'
		- new instances -- must b set @ launch or else replicas won't b able 2 b encrypt'd
		- existing instances -- must backup & restore as encrypt'd => 1. snapshot -> 2. enable encrypt' in snapshot -> 3. restore DB from snapshot
	- [[Atlas/AWS/Identity and Access Manager]] -- IAM DB Auth = 2 conn 2 db w/o handling auth urself, ==works only with Postgres y MySQL==
	- [[CloudWatch Logs]] -- audit logs enablable
	- [[RDS Proxy]] -- helps with refering 2 multiple instances
### IAM DB auth
Hay dos capas que interactúan entre sí pero que no están automáticamente relacionadas: la capa de users de la DB y la capa de users de IAM.

El user de la DB es lo que nos permitirá interactuar con ésta.

Normalmente, se crearía una password para éste en la misma DB. Pero podemos usar IAM para evitar esa gestión.

**Por cada user** que tendrá acceso a la DB:
- ejecutamos `CREATE USER <nombre> IDENTIFIED WITH awsAuthenticationPlugin`, donde le decimos que IAM se encargará de la auth
- creamos una política IAM que habilite el acceso a la DB usando el user que creamos en la DB
- asociamos la política al user IAM que corresponda

> [!tip] Sobre las buenas prácticas
> Como es sí o sí **1 política IAM por user de DB**, si quisiéramos seguir las buenas prácticas deberíamos crear 1 user de DB por cada user IAM que vaya a trabajar con la DB y por lo tanto 1 política por ese user. Si tenemos 5 devs que trabajan con esa DB, deberíamos tener 5 users de DB distintos y 5 policies distintas.
>
> De lo contrario (y yendo en contra de las recomendaciones de AWS), podríamos crear 1 solo user de DB y una sola política IAM, y asociar esa política a todos los devs que queramos. INCLUSO podemos asociar la policy a un group, directamente.
