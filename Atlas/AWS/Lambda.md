---
dudas:
tags:
  - DVA02-8
aliases:
---
### Dudas
- ¿es necesario que se defina el execution role? ¿es un campo obligatorio en el alta de la función? — ~~ampliar~~
    
    Sí, es obligatorio.
    
- ¿el envío de logs a CW logs se hace de forma automática o hay que settear algo en el alta de la función? ¿si no se le define el permiso, igual intenta enviar logs a CW o sólo los comienza a enviar si se define el permiso? — ~~ampliar~~
    
    Viene de forma automática si al crear la función elegís que se cree el execution role por defecto.
    
    Pero, sí, hay que settear los permisos para que Lambda pueda comunicarse con CW. Si no tiene los permisos, no enviará nada.
    
- ¿qué determina la cantidad de RAM a definir para la función? — ~~ampliar~~
    
    Depende del interés en la performance de la app. A más RAM, menos tiempo de ejecución. PERO a más RAM, más $$$$.
    
- ¿las policies de la lambda se van actualizando automáticamente al ir asociado recursos como trigger de ella? — ~~ampliar~~
    
    Prácticamente, no. Debe actualizarse a mano. Incluso aunque lo hagas desde la consola, muchas veces en el alta se te va a advertir si lambda no tiene los permisos necesarios.
    
- ¿qué diferencia hay entre definir la cadena S3 → EventBridge → Lambda a hacer directamente S3 → Lambda? ¿o en qué casos se usaría EventBridge como trigger de Lambda? — ~~ampliar~~
    
    La cadena directa S3 → Lambda se usa cuando no se requiere mucha cumplejidad de filtrado de eventos. EventBridge sirve en ese caso.
    
- ¿siempre que se invoque la función desde la CLI la invocación será asíncrona? ¿o depende del comando que se use para invocarla? — ~~ampliar~~
    
    No. Depende del parámetro que se le pase al comando.
    
    - `--invokcation-type RequestResponse` — síncrona
    - `--invokcation-type Event` — asíncrona
- destination — necesito entender mejor la gestión de mensajes de error en los async y event map, event map sobre todo, el tema de los batches de error
    
- env vars — ¿sólo pueden definirse a través de la consola o pueden definirse a través de la CLI o el SDK? ¿cuál es el patrón más común? ¿con CloudFormation se puede definir también? — ~~ampliar~~
    
    Se puede definir mediante cualquier medio. El medio más común es con IaC.
    
- provisioned concurrency — ¿dónde se settea y cómo se gestiona para que el cold start no afecte el tiempo de performance de lambda? — ~~ampliar~~
    
    Se settea desde la consola de Lambda, en la sección de Concurrency.
     ^4d5976
- dependencias externas — ¿por qué las dependencias externas tenemos que guardarlas en un zip junto con la aplicación si existen las layers? ¿node_modules no podría guardarse como un zip en una layer y listo? — ~~ampliar~~
    
    No es necesario guardarlas en un zip. Lo recomendable es guardarlas en una layer. A no ser que quiera deployarse todo junto.
    
- ¿tendría sentido tener un SPA en una lambda? no, ¿no? porque el tiempo de ejecución máximo de las lambdas es de 15m, ¿cierto? — ~~ampliar~~
    
    Correcto. Puede usarse más como la contraparte BE de la app.
    
    Tener en cuenta que cada interacción que el user tenga con el sitio generará una nueva invocación.
    
- ¿qué diferencias hay entre deployar lambda en un contenedor a hacerlo sin contenedor? — ~~ampliar~~
    
    Uno de los usos, es cargar fx muy pesadas. Con contenedores, se puede hasta 10gb. Habría que ver cuál es el máximo en el deploy comunacho ⇒ 250mb con EFS.
    
    Los contenedores permiten más configuración pero a su vez ésta es más compleja en comparación al deploy del zip.
    
- aliases — no termino de entender el Canary deployment. además ¿cuáles serían casos de uso?
    
    Pasaje progresivo de una versión a otra del código.
    
- fx URL — ¿cuál sería el uso si el AuthType= AWS_IAM?
    
- event source map — wtf is it??
    
    Es un instrumento que vincula a Lambda con sources que requieren que se les haga pull de data porque ellos no hacen push.
    
    Es el medio que permite automatizar la ejecución de lambda como consecuencia de eventos de stream y q. Además, tiene funcionalidades para gestión de errores y demás.
### Notas
- Se pueden correr contenedores con Lambda → Lambda Container Image; de cualquier forma, AWS recomienda hacerlo en [[Elastic Container Service|ECS]]/Fargate
- casos de uso: efecto secundario de acciones sobre RR, cron jobs
- Se puede seguir los logs en CW Logs → se debe definir el permiso para hacer PUT a CW Logs
- En el momento de crear la función, sólo se define el código a correrse pero NO el trigger. Éso se define una vez creada la función.
- Lambda retries 3 veces, todas las veces que retries se loggean en CW Logs
- Cuando hablamos de *deploy en VPC* nos referimos a que a la hora de configurar la lambda se le van a asignar valores de subnet y demás. De lo contrario, por defecto esos datos no están definidos. ^Mw7cn5Kk
### Palabras clave
- elementos
    - definition location
        - locally — zip file
            - max zipped size — 50m
            - max unzipped size — 250mb
        - [[Simple Storage Service|S3]] bucket
        - [[ECR]] image — 10gb, props: `Properties.PackageType=Image` & `Properties.Code.ImageUri`
        - [[CloudFormation]] template
    - trigger
    - destination — target de mensajes, permissions created at ALTA
        - async — de éxito y error de lambda, [[SQS]] | [[SNS]] | EB | Lambda, AWS recommen’d over [[Simple Queue Service|SQS]] #test-question  ^c7a378
        - event map — de error, [[Simple Queue Service|SQS]] | SNS
    - f(x) params
        - event object — mensaje proveniente de [[EventBridge]]/S3EventNotifs/s trigger, data 2 b process’d
        - context object — objecto que detalla ctx de lambda, 1 invocation → 1 specific context
            - request ID — uno de los params de CWLogs
    - env vars — 4Kb limit 4 the entire set of variables, definible desde cualquier medio, props: `Properties.Environment.Variables`
    - performance configs — no se puede tweakear CPU core count ^5292b6
        - RAM — memory 128Mb MIN, CPU-related, + speed? ⇒ + memory → + CPU ⇒ $ $ $ $ ^52ccbb
        - timeout — T de runtime hasta devolver error ⇒ si lógica tarda más → subirlo, default: 3s, max: 15m
        - ctx — temp runtime env, lógica que se ejecuta en la raíz del archivo en que se define la función lambda, can b reused by M invokations
    - layers — storage common 4 al invocations, use case: custom runtimes | decouple dependencies | separation of concerns (update of one is not slowed down by conjunct deploy of the other), up 2 5 layers, up 2 250mb in total (50mb per layer) #test-question 
    - concurrency — # de invocaciones con distintas finalidades
        - reserved — use case: a correr al mismo tiempo en caso de scaling, if need b > 1000 → ticket, el máximo de 1000 es compartido entre todas las fx de la acc, superado el límite? → throttling → ThrotleError 429 (sync)/DLQ (async) ^e1d0bb
        - provisioned — use case: pre-inicializadas para disminuir el impacto del cold start y que la espera sea lo menor posible, $ $ $ ^a2f1fb
        - maximum — definido a nivel de trigger
    - dependencias externas — stored = size > 50mb ? bucket : lambda
    - version — actions > publish new version ^68d556
    - alias — punto inmutable de acceso a una versión de la fx, para evitar problemas cuando las versiones de referencia cambian ^3d5a17
        - weighted alias — versión alternativa a la que apuntar cuando se accede al alias
    - fx URL — 2 access lambda from **public** internet, creates EP w/o having 2 use [[API Gateway|API-GW]], applicable 2 [[Lambda#^3d5a17|ALIAS]] not [[Lambda#^68d556|VERS]] #test-question 
	    - r-based policy 4 CIDR | IP | [[Identity and Access Management|IAM]]
		    - `AuthType=NONE` -- unauth acc
		    - `AuthType=AWS_IAM` -- auth acc, x-acc ? need ID-based permissions 2
    - `/temp` — store temp files, max: 10Gb n' can b upd in config > ephemeral storage, use cases: storing data used 4 processing #test-question ^gH2iSJqA
- permisos — by default: Lambda deployed in AWS VC
    - execution role — para permitir acceso de lambda a distintos SS
        - destinations
        - triggers que requieren pull
	        - `AWSLambdaSQSQueueExecutionRole` -- [[SQS]]
	        - `AWSLambdaKinesisExecutionRole` -- [[Kinesis Data Streams]]
        - monitoreo
	        - `AWSLambdaBasicExecutionRole` -- [[CloudWatch Logs]] ^e74b7b
	        - `AWSXRayDaemonWriteAccess` -- [[X-Ray]]
        - acceder a RR de VPC — `AWSLambdaENIManagementAccess` contenido dentro del `AWSLambdaVPCAccessExecutionRole`) ^NIDLsJFh
    - r-based policy — para allow a los distintos triggers a invocar a lambda | x-acc access
- deployment en VPC #test-question  ^dd0a4a
    - a través de Elastic Network Interface accede a los RR de la VPC
    - acceso a internet — no nativo, private subnet { Lambda →}→ { NAT → I-GW } public subnet
    - acceso a RR en public subnet — { lambda → } → { VPC EP → public r }, por lo general no es necesario conectarla a internet
- invocación — runtime MAX 15m
    - síncrona — se espera el resultado, error gestionado por cliente, EBL | API-G | CloudFront | Cognito | Step F(x), pushed 2 lamda, `--invokation-type RequestResponse`
        - event source mapping — elemento que auto sms poll & error resolution, [[Kinesis Data Streams|KDS]] | [[SQS]]/[[SNS]] FIFO | [[DynamoDB#^9aa407|DynamoDB Streams]], auto polls 4 lambda #test-question ^c87943
            - streams — 1 shard ⇒ 1 iterator, can b batched or process’d via multi-batches ⇒ 1 shard ≤ 10 batches
            - queue
    - asíncrona — S3 | SNS | CW Events | EventBridge | CCommit | CPipeline, use case: procesamiento que no necesita ser real-time, pushed 2 lamda, `--invokation-type Event`
- integraciones
    - trigger:[[Elastic Load Balancer|ALB]] — client ↔ http/s ↔ ALB ↔ target group { json ↔ Lambda }, json has headers-section | queries-section as key-value props, multi-value headers = array de valores para given qp → must b enabled via EC2 > TG > attributes > multi value headers
    - trigger:CW Events / [[EventBridge]] — 4 cron jobs, permissions added when Lambda is set as target
    - trigger:[[Simple Storage Service|S3]] Events Notifs — set via bucket > props > event notifs > destination > lambda, permissions added when Lambda is set as target
    - [[SQS]] / [[SNS]]
        - target — for dead-letter queue service → enviar los logs para later analysis, needs permissions #test-question 
        - trigger — q poll, permissions added when Lambda is set as target
    - trigger:[[Kinesis Data Streams|KDS]] — shard poll, permissions added when Lambda is set as target
    - trigger:[[CloudFront]] — edge f(x), lógica que se ejecuta en las EL
        - CF Functions — CF native, handles only viewer rq and rta, use case: latency-sensitive (but) | high-scale, global-scope, JS only
        - Lambda@Edge — handles viewer/origin rq and rta, R-scope, longer execution time, 4 + complex logic, not the best @ BIG scale ^8f52e7
    - create:[[CloudFormation]]
        - in-line fx — very simple fx, no dependencias, prop: `Code.ZipFile`
        - S3 — fx zip’d w/ dependencies, props: `Code.S3Bucket` & `Code.S3Key`
    - monitor:[[X-Ray]] — no need 4 daemon in app ‘cause enabling X-Ray is genug, MUST manually give permissions tho
    - [[CodeDeploy]] — 4 auto version update (aka pasar de una versión a otra)
        - version update
            - Linear — actualiza weight en T amount, 4 step by step monitoring, more gradual and careful
            - Canary — x% in x T y luego 100% ⇒ initial small-scale test → full rollout
            - AllAtOnce
        - rollback — can b set auto by alarms
        - AppSpec.yml — template 4 version update
            - required properties
                - Name
                - Alias
                - CurrentVersion
                - TargetVersion
    - storage
        - S3 — use case: la app supera los 250mb | disponibilizar datos para todas las invocaciones | when defined via CForm
        - [[Elastic File System|EFS]] — use case: cuando las dependencias superan los 250mb | disponibilizar datos para todas las invocaciones
- integrations
	- [[RDS Proxy]] -- gestionar las múltiples rqs a [[Relational DB Service|RDS]] o [[Amazon Aurora|Aurora]] #test-question  ^6822c1