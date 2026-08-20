---
dudas: false
tags:
  - security
  - DVA02-29
aliases:
  - IAM
---
### Dudas
- [x] dynamic policies -- `${aws:username}` -- ¿entonces ésto podría usarse para crear policies para users con los que querés acceder a [[Relational DB Service|RDS]] usando [[SQL DB security integrations#IAM DB auth|el auth de IAM]], ¿cierto?
	Sí, correcto. Pero no debemos olvidar que éso resuelve sólo el tema de reutilización de credenciales, pero del lado de RDS es necesario ejecutar sentencia de creación de users, una por cada user. ^3d15c6
- [x] `iam:PassRole` -- ¿en `Resource` se puede definir un array de roles para que no tenga que crear tantos statements como roles pueda el user pasar?
	No. Sí o sí 1 rol pasable = 1 statement. ^509640
- [x] `sts:AssumeRole` -- ¿están definidos por defecto o el user tiene/debe definirlos? ^ba7269
	Por defecto, los roles no tienen ningún statement para ser asumido, el user los tiene que definir y es responsable de ellos. Por suerte, no necesitás un `Statement` por principal que pueda asumirlo sino que simplemente podés agregar un array en `Principals.AWS` para el mismo `Actions`, que en este caso es AssumeRole.
- [x] ídem -- ¿puede ser el mismo permiso que se le otorga a un user para usar [[Security Token Service|STS]] para acceder x-acc? ^d33663
	Sí, correcto.
- [x] Acceso a metadata de instancias — sabemos que EC2 tiene su propia IP pero ¿cómo se accede a estos datos para otros RR? ¿se puede usar la CLI, como con EC2? — ~~ampliar~~
    
    Acá hay que diferenciar en el medio por el que se puede acceder a la metadata de los RR.
    
    EC2 como es una ~computadora con su SO, tiene disponible una URL [localhost](http://localhost) a través de la que se puede acceder a esta metadata. Por esta razón, sólo es necesario conectarse a la instancia y correr el comando CURL a la EP definida. Acceder a la instancia y obtener la metadata NO requiere del uso de la AWS CLI.
    
    Para los demás RR es necesario usar específicamente la AWS CLI porque es un comando especial y porque no se puede “ingresar” a las instancias de los RR como se puede con una EC2.
    
- [x] ¿Por qué no se puede asignar un IAM Role a una app en un servidor on-premises pero sí se le puede asignar un IAM User? — ~~ampliar~~
    
    Porque en un servidor externo AWS no tiene acceso a la identidad del r para permitir que asuma el Role. El bypass de ésto es asignándole un User, porque entonces AWS no mira la identidad del r sino que espera las claves de acceso.
    
- [x] ¿Diferencia entre IAM Users y Roles? — ~~ampliar~~
    
    El lifespan de las credenciales y, por consiguiente, nivel de seguridad que cada una conlleva. Los Roles tienen creds temporales y los Users, permanentes.
### Notas
### Palabras clave
- Roles — provides creds & permissions to RR, `describe-instance` API, canNOT b attached 2 on-premises RR, TEMPORARY creds
	- [[Elastic Compute Cloud|EC2]] instance profile -- es una entidad-wrapper que se crea por defecto junto con los roles y que al asignársela a una instancia permite que ésta adquiera los permisos definidos por el rol, "una instancia usa un rol" = la instancia está usando un instance profile ^cfdbcd
- Users — CAN b attachaed 2 on-premises RR
- AWS Policy Simulator — access 2 permission state 4 user based on all identity policies applied 2 it ⇒ use case: c y AccessError/PermissionError, policy sandbox!
- Signature — ID & Auth creds, sign must b sent in almost every API call, manual: via Auth header or URL query string, se calcula en base a las creds de la identity/security token
- policies
	- eval of policies
		- general rule -- eplicit `DENY` ? `DENY` : explicit `ALLOW` ? `ALLOW` : `DENY`, explicit `DENY` >> explicit `ALLOW`
		- vs [[Simple Storage Service|S3]] -- all rules are joined => IAM policy + bucket policy = total de policies
	- dynamic policies -- usa vars ([[Identity and Access Management#^3d15c6|duda]])
	- ownership
		- AWS managed -- power users/admin
		- customer managed -- reusable, version control, 
		- inline -- principal-bound => del principal -> del policy
- permissions
	- `iam:PassRole` -- es la que permite que un user pueda permitir que un s tome un role, se puede limitar en `Statement.x.Resource` el rol específico que se puede pasar ([[Identity and Access Management#^509640|duda]])
	- `iam:GetRole` -- obtener los datos del rol
	- `sts:AssumeRole` -- para asignar qué servicios/users (*principals*) pueden asumir ese rol, 15m < asump' time < 1h,  ([[Identity and Access Management#^ba7269|duda 1]], [[Identity and Access Management#^d33663|duda 2]])
		- ubicación -- se define en la [[trust policy]] del rol asumible