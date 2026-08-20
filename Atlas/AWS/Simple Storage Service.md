---
dudas:
tags:
  - DVA02-14
  - DVA02-13
  - DVA02-11
  - aws-SecureTransport
aliases:
  - S3
---
### Dudas
- S3 Security: Bucket policy — ~~ampliar~~
    
    - ¿qué diferencia hay entre una bucket policy y una bucket ACL?
        
        La ACL es legacy y es más una lista de permisos. La bucket policy es la versión moderna y permite usar criterios más granulares.
        
    - ¿qué es lo recomendado por AWS con respecto a la seguridad? ¿definir accesos a S3 a nivel de IAM policy, a nivel de bucket policy o en ambos?
        
        Sin tener en consideración los casos en que queremos definir acceso cross-account, ya que esos sí o sí se definen via bucket policy.
        
        Depende, pero por lo general ambos.
        
- S3 Website — ~~ampliar~~
    
    - ¿se puede hostear una app react?
        
        Técnicamente sí se puede, pero no como se sirve en GitHub, por ejemplo. Lo que se puede hacer es hacer build de la app y éso sí se puede subir al bucket y hostearse. Aunque hay que hacer un par de teaks más con respecto al ruteo.
        
        Tiene que ser una app de react pura, es decir: desacoplada del BE.
        
- En el contexto de la class type Glacier, cuando hablamos del tiempo mínimo ¿nos referimos al tiempo mínimo que debe permanecer en esa clase o al tiempo mínimo desde que se creó el objeto? — ~~ampliar~~
    
    Ninguna de las dos. Refiere al tiempo mínimo que se te va a cobrar por pasar el objeto a esa clase. Pero sobre el objeto podés realizar las acciones que quieras. Si quisieras, podrías pasar un objeto de standard a glacier deep archive y al minuto volverlo a pasar a standard, y se te va a cobrar el tiempo que estuvo en standard mas la tarifa mínima del deep archive.
- ¿Qué diferencia hay entre usar la clase Intelligent Tiering a usar Lifecycle Rules Transition Actions? — ~~Ver video~~
    
    IT tiene la ventaja de que realiza las transiciones de forma automática según el uso real. La lifecycle rule la tenés que definir a mano y puede contribuir a estrategias de transición ineficientes. Además, los restores son manuales y más costosos con la rule que usando IT.
    
- ¿Cómo funciona exactamente el Transfer Acceleration? — ~~Ver video~~
    
    Se transfiere el archivo a una Edge Location más cercana y de ahí se transfiere a la R target usando la red privada de AWS, que es más eficiente que el internet.
    
- S3 Event Notifications — los permisos para comunicarse con los targets del bucket source ([[Simple Queue Service|SQS]], SNS, Lambda) ¿sólo pueden definirse con IAM permissions sobre los target o pueden definirse también con bucket policies? — ~~Ampliar~~
    
    Inicialmente pareciera que no, o al menos sí o sí debemos definir los servicios en las access policies porque al querer crear el event desde el bucket devuelve error si no existe una policy.
    
    No pueden definirse con bucket policies porque como el bucket es quien emite, en realidad es sobre el target que debe definirse si lo acepta o no; y la bucket policy no controla hacia dónde se puede enviar datos.
    
    Tener en cuenta que las policies tanto de bucket como de access definen los permisos de ACCESO a cada recurso y no de EGRESO de éste. Ésto quiere decir que en las bucket policies definimos reglas de acceso al bucket pero no qué se hace con sus eventos (que son flujo OUTWARD); y en las access policies definimos DESDE qué servicios se puede recibir data.
    
- S3 Object Metadata & Tags — ¿cómo se crea el search index desde el bucket? ¿sólo se puede con dynamoDB o ésa es la opción más barata y sencilla? — ~~Ampliar~~
    
    No se crea de forma “nativa”. Sí o sí tenemos que basarnos en los eventos del bucket y crear una lambda que actualice la DB. Usar DynamoDB es la opción más común y barata, pero pueden usarse otros medios (más caros y/o ineficientes y/o complejos) como Amazon Athena o Amazon OpenSerach
    
- S3 Event Notifications — ¿cómo interactúa con una lambda?
    
    La forma en que se dirije la notificación a Lambda es a través de la config del evento. Ahí se define el target.
- ¿Qué diferencia hay entre usar KMS y C? — ~~ampliar~~
    
    En KMS las claves están gestionadas por AWS. En C, no.
    
    Además, por estar gestionadas por AWS hay algunas features disponibles como login y demás, que con C no con ese servicio la encriptación y demás sucede antes de ingresar a la nube de AWS.
    
- ¿Por qué los errores de CORS no se pueden arreglar con bucket policies? ¿Cuál es el alcance o dominio de las bucket policies que provoca que no puedan controlar ese tipo de aspectos? — ~~ampliar~~
    
    Porque son validaciones de seguridad en distintos niveles. CORS es a nivel del cliente y la bucket policy es a nivel del server. Si bien el `allowedOrigins` se define a nivel del bucket, su configuración se define POR SEPARADO de las bucket policies.
    
- ¿Por qué el SSE-C requiere el uso de HTTPS solamente? — ~~ampliar~~
    
    Porque como se está enviando la key posta entre los headers, es necesario cifrar in-transit los datos para que nadie pueda acceder a ella.
    
- ¿Qué significa que un user sea “federated”? — ~~ampliar~~
    
    Que se loggea desde otra app que no es de AWS pero en quien éste confía. Es lo mismo que loggearte en una app usando el login de Google, por ejemplo.
    
- S3 Encryption — cuando se indica que debo settear el header `x-amz-server-side-encryption: "AES256"` se refiere a que este header debe ir en la request que se haga al bucket? — ~~ampliar~~
    
    Sí, efectivamente. En el header de request de upload debe ir ese header.
    
- S3 Encryption — en el caso de SSE-KMS, ¿qué significa que Amazon “manages” la key si en realidad el user puede crearlas y eliminarlas? ¿qué diferencia hay entre “manage” a key y “own” a key? — ~~ampliar~~
    
    Quien “owns” toma las decisiones sobre el uso de las keys y su ciclo de vida. Quien “manages” se encarga de la infra y de cómo se usa esa key.
    
    En el caso de KMS, AWS se hace cargo de la puesta en uso de las keys del usario controlando el proceso de encriptación. El user lo que puede hacer es crear/eliminar keys y decidir sobre su ciclo de rotación.
    
- S3 Encryption — en el caso de SSE-KMS, la key se envía en un header aparte o se envía en el mismo header en que se éspecifica el método de encriptado? ídem sobre el SSE-C— ~~ampliar~~
    
    No se envía la key, se envía el ID/ARN que refiere a la key de KMS. Y, sí, se envía en un header aparte.
    
- ¿Cómo funciona el SSE? ¿Cómo se generan/obtienen las keys y cómo se usan en el encriptado? ¿Cómo es el proceso de encriptación?
    
    Las keys las genera tanto AWS como el user (Customer-Managed Keys, CMK).
    
    KMS contiene todas las keys generadas por AWS y el user. Y cuando se define el SSE desde ahí obtiene las keys que usa de referencia para empezar el encriptado.
    
    El proceso es:
    
    1. Llega request de upload a S3 con header que indicar SSE
    2. KMS busca la key (llamada master key) que coincide con la referencia del header
    3. KMS crea un objeto-data key con dos propiedades: la versión plain y la versión encripted; le devuelve ésto a S3
    4. S3 encripta el objeto con la versión plain, que luego se desecha.
    5. S3 almacena el objeto junto con la versión encripted de la data key.
    6. Llega request de download a S3
    7. S3 busca el objeto y obtiene de metadata.data-key la encripted data key y se la pasa a KMS
    8. KMS lee la encripted dk y obtiene en su metadata la master key
    9. KMS desencripta la dk usando la master key
    10. KMS le pasa la dk plain a S3
    11. S3 desencripta el objeto y lo disponibiliza.
    
    La diferencia con SSE-S3 y SSE-C es en los pasos 2 y 3. En el caso de SSE-S3, la data key se crea de forma interna; en el de -C, llega en el header de la request de upload.
    
- CORS — ~~ver el hands-on & ampliar~~
    
- S3 Pre-Signed URL — ~~ampliar~~
    
    Es una URL que otorga permisos temporales. Los permisos temporales son iguales a los del IAM User/Role que haya generado la URL. S3 los deduce en función de la policy de IAM asociada al user/rol.
    
- S3 Access Points — ~~ampliar~~
    
    - ¿cómo se definen?
        
        Dentro de la consola de S3 tenés un apartado de Access Points. Ahí definís nombre, bucket y policy.
        
    - ¿cómo se distingue un flujo público de uno privado? (es decir, entre el acceso a un bucket público y otro privado)?
        
        Es en función de que el bucket sea privado o público. Que sea privado significa que el client debe autenticarse para acceder.
        
        Con respecto al flujo de acceso con AP, no influye el que el bucket sea o uno o lo otro. Lo que lo define es si en su configuración se definió algún valor de VPC. Si es así, ese AP sólo permitiría acceder a RR dentro de esa VPC en particular.
        
        El wiring para este tipo de casos es VPC = { r → VPC EP -}→ AP(VPC) → bucket.
### Notas
### Palabras clave
- quid -- Simple ==Storage== Service, R-service, object storage
- elements
	- object
	    - key — full file path=prefix+object name
	    - properties
	        - value — the binary of the file itself
	        - metadata
	        - tags
	        - version ID
	    - multi-part upload — when uploading files > 100mb
	- class types/access tiers
		- Standard
			- General Purpose (GP) — by default, frequently accessed, use cases: analytics, apps, content, retrieval NOT charged
			- Infrequent Access (IA) — less frequently but fast access, pay 4 GB retrieved, use cases: data recovery
				- 1AZ-IA — use cases: 4 recreatable data, pay 4 GB retrieved
		- Glacier — use cases: archive & backup, low cost: 4 storage & retrieval
			- Instant Retrieval — seconds, constraint: > 90 days storaged, pay 4 GB retrieved
			- Flexible — constraint: > 90 days
				- retrieval modes
					- Expedited — minutes
					- Standard — up to a few hours
					- Bulk — up to 12 hours, free
			- Deep Archive — constraint: > 180 days, lowest cost, pay 4 GB retrieved
				- retrieval modes
					- Standard — 12hs
					- Bulk — 48hs
		- Intelligent Tiering — va mutando la clase del bucket dependiendo del patrón de acceso a éste, NO retrieval charges
			- tiering config
				- Frequent A — default
				- IA — not accessed > 30d
				- Archive Instant A — not accessed > 90d
				- Archive A — 700d+ > not accessed > 90d
				- Deep Archive A — 700d+ > not accessed > 180d
	- bucket
		- naming conventions — GLOBALLY unique name
		- security — DENY policies > ALLOW policies > undefined policies, recomended: IAM policies + bucket policies
			- user-based — IAM policies, ==condition: `aws:SecureTransport` = enforce SSL rq==
			- r-based
				- bucket policies — allows for granular control
					- use cases
						- public access to bucket
						- object encription @ upload
						- grant cross-account ^919721
				- object ACL
				- bucket ACL — legacy, permission list
		- website hosting
			- constraints — must be configd as public (ELSE: `403`)
		- versioning — upload object with existing key in bucket? → bucket understands it’s a new VERSION of object
			- constraints
				- must be configd
				- when you turn bucket into versionable, if there were files there, they won’t have version defined
				- when you turn it off, the file versions will remain
		- replication — async
			- constraints
				- most be configd as versioning enabled
				- replicates only NEW objects
				- DIRECT source → replica & source → replica and not source → replica → replica
				- replica is done over EXISTING bucket
				- surce bucket policy to read/write in target
			- types
				- Cross-R (CRR) — use cases: lower latency, cross-account replica, compliance
				- Same-R (SRR) — use cases: env replica 2 have ≠ envs with same data
				- S3 Batch Replication — replicates already existing objects
- Event Notifications — notify when an action is performed within a bucket
    - criteria — actions, obj attr
    - targets — SNS, [[Simple Queue Service|SQS]], Lambda, Amazon EventBridge (u set rules 2 send notifs 2 ≠ SS, better filtering)
    - permissions — resource access policy on targets (SNS, [[Simple Queue Service|SQS]], Lambda)
- Lifecycle Rules — based on object AGE #test-question 
    - Target — bucket, path within bucket, object tags
    - Expiration Actions — automate deletion of objects (old/unfinished)
        - old versions — constraint: must have versioning ON
    - Transition Actions — automate transition between tiers
- Storage Class Analysis — recomienda cuándo mover objetos desde buckets S y S-IA, report updated daily,
- Versioning — los objetos versionados que son eliminados lo son de forma LÓGICA no física
- better performance
    - Byte Range Fetch — read files in the MOST efficient way, works for downloads, use cases: speed up download, retrieve partial data
    - Multi-part Upload — parallel uploads ⇒ faster transfer
    - Transfer Acceleration — transfer data 2 Edge Location and then AWS internal infra transfers that to target R, compatible with m-p upload, works for up/download
- object — 2 filter based on metadata/tags u must export data 2 DB
    - metadata — must hace prefix `x-amz-meta-`, cannot b used 2 filter
    - tags — used for setting permissions, analytics, cannot b used 2 filter
- encrypt' — tres niveles de relación con la key: handle, manage, own (h, m, o) ^c09d75
    - [[at rest encryption#server side|Server side encrypt']] w Customer-provided keys (SSE-C) — AWS h & user mo, mandatory HTTPS & key header, key is not storaged in AWS ⇒ deleted from cloud after usage
    - [[at rest encryption#client side|Client-Side Encrypt']] — user hmo & encrypt cycle, encription happens before sending data 2 AWS
    - SSE w/ S3-managed keys (SSE-S3) — default, auto encrypt of new objects, AWS hmo, `x-amz-server-side-encryption="AES256"`, can b enforced via bucket policy ^16a8e2
    - SSE [[Key Management Service|KMS]] — AWS hm & user o, key usage audit thru [[Atlas/AWS/CloudTrail]], `x-amz-server-side-encryption="aws:kms"`, bucket API calls KMS ⇒ consumes s quota, can b enforced via bucket policy
    - SSL/TLS — in-transit, S3 exposes 2 EPs: HTTP & HTTPS, can b enforced by bucket-policy.`aws:SecureTransport=true`
- Cross-Origin Resource Sharing (CORS) — bucket property (NOT bucket policy), allows apps from one domain 2 connect with RR in a different one ^d01b3a
- MFA-Delete — 2 delete an object user must MFA, requires versioning ON, root can set MFA ON/OFF, vigila: permanent delete, setting version OFF
- S3-Access Logs — logs all reqs authorized or not made 2 buckets, logs must b saved in ANOTHER bucket in same R
- S3 Pre-signed URL — allow access 2 object in PRIVATE bucket, create via S3 console | AWS CLI | SDK, use case: access 2 x file for x amount of time, URL holds same permissions as creator
- S3 Access Points — access point (x URL) que permite acceso sobre ciertos prefijos (ciertos archivos o directorios) a ciertos user, configd via access point policy, simplifica gestión de seguridad al no tener que definirlo en la bucket policy (lo que lo vuelve poco escalable y mantenible) ^d640c2
    - types
        - Public
        - Private — accessed only from specific/s VPC/s
        - Object Lambda — tipo de AP que ejecuta una lambda sobre datos de un bucket para devolver datos en formato requerido ^5fab14
    - properties — bucket, policy, name, VPC