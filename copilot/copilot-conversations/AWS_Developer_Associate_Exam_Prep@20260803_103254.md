---
epoch: 1785763974264
modelKey: "gemini-2.5-flash|google"
topic: "AWS Developer Associate Exam Prep"



tags:
  - copilot-conversation
---

**user**: necesito, en función de los resultados de la tabla que muestran qué respuestas respondí incorrectamente, y sabiendo que me estoy preparando para rendir el examen de AWS certified developer associate, necesito que me listes en qué servicios tengo que profundizar más y qué aspectos específicos
[Context: Notes: Atlas/AWS/DVA-C02/A reforzar.md]
[Timestamp: 2026/08/03 10:32:54]

**ai**: 
<errorChunk>Model request failed: API key is not provided for the model: google/gemini-2.5-flash|openrouterai.</errorChunk>
[Timestamp: 2026/08/03 10:32:54]

**user**: necesito, en función de los resultados de la tabla que muestran qué respuestas respondí incorrectamente, y sabiendo que me estoy preparando para rendir el examen de AWS certified developer associate, necesito que me listes en qué servicios tengo que profundizar más y qué aspectos específicos
[Context: Notes: Atlas/AWS/DVA-C02/A reforzar.md]
[Timestamp: 2026/08/03 10:33:27]

**ai**: 
<errorChunk>Model request failed: Copilot Plus license key is not configured. Please enter your license key in the Copilot Plus section at the top of Basic Settings.</errorChunk>
[Timestamp: 2026/08/03 10:33:27]

**user**: necesito, en función de los resultados de la tabla que muestran qué respuestas respondí incorrectamente, y sabiendo que me estoy preparando para rendir el examen de AWS certified developer associate, necesito que me listes en qué servicios tengo que profundizar más y qué aspectos específicos
[Context: Notes: Atlas/AWS/DVA-C02/A reforzar.md]
[Timestamp: 2026/08/03 10:43:14]

**ai**: Para poder darte un análisis exacto y personalizado de los servicios y aspectos específicos que necesitas reforzar, necesito conocer cuáles son los títulos, temas o conceptos de las preguntas que te aparecen actualmente en la tabla de tu nota [[A reforzar]] (las que tienen la propiedad `incorrecta == true`).

Como la tabla de tu nota se genera de forma dinámica en tu Obsidian, no puedo ver directamente el resultado de la lista en este momento. Para ayudarte mejor, puedes hacer cualquiera de las siguientes opciones:

- Copiar y pegar aquí los títulos o los temas de las preguntas que te aparecen en esa tabla de incorrectas.
- Escribir tu próxima consulta usando `@vault` (por ejemplo: *"@vault analiza mis notas de preguntas incorrectas en Atlas/AWS/DVA-C02 y dime qué servicios debo reforzar"*) para que pueda buscar y leer el contenido de esas notas directamente en tu bóveda.

---

Mientras me compartes esa información, aquí tienes los **servicios clave y los aspectos más difíciles y recurrentes** en el examen **AWS Certified Developer Associate (DVA-C02)** que suelen requerir mayor profundización:

- **AWS Lambda**
- Configuración de concurrencia (Reserved Concurrency vs. Provisioned Concurrency).
- Integración con VPC (subredes privadas, ENIs) y manejo de accesos a internet.
- Variables de entorno y uso de AWS Systems Manager Parameter Store o Secrets Manager para datos sensibles.
- Destinos de Lambda (Lambda Destinations) y colas de mensajes no entregados (DLQ).

- **Amazon DynamoDB**
- Cálculo de unidades de capacidad de lectura (RCU) y escritura (WCU) para lecturas fuertemente consistentes, eventualmente consistentes y transaccionales.
- Índices Secundarios Locales (LSI) vs. Índices Secundarios Globales (GSI) (cuándo usar cada uno y sus limitaciones).
- DynamoDB Streams combinados con AWS Lambda para arquitecturas orientadas a eventos.
- Estrategias de optimización (evitar "hot partitions", uso de DAX para caché).

- **AWS Identity and Access Management (IAM) y Seguridad**
- Políticas de IAM (evaluación de políticas, diferencia entre Resource-based y Identity-based policies).
- AWS KMS: Concepto de Envelope Encryption, uso de las APIs `GenerateDataKey` y `Decrypt`, y rotación de claves.
- AWS Cognito: Diferencia clave entre User Pools (autenticación/registro de usuarios) e Identity Pools (autorización/obtención de credenciales temporales de AWS).

- **Herramientas de CI/CD (AWS CodeSuite)**
- AWS CodeBuild: Estructura y fases del archivo `buildspec.yml`.
- AWS CodeDeploy: Configuración del archivo `appspec.yml` (secciones de hooks para [[Elastic Container Service|ECS]], Lambda y EC2) y estrategias de despliegue (Canary, Linear, AllAtOnce).
- AWS CodePipeline: Integración de etapas y paso de artefactos entre ellas.

- **Amazon API Gateway**
- Tipos de integración: Lambda Proxy Integration vs. Lambda Custom Integration (cuándo se transforman las peticiones/respuestas).
- Mecanismos de autorización: Cognito Authorizers vs. Lambda Authorizers (Custom Authorizers).
- Configuración de CORS, almacenamiento en caché (Caching) y límites de velocidad (Throttling).

Quedo atento a que me compartas los temas o uses `@vault` para darte un plan de estudio completamente personalizado basado en tus fallos reales.
[Timestamp: 2026/08/03 10:43:29]

**user**: necesito, en función de los resultados de la tabla que muestran qué respuestas respondí incorrectamente, y sabiendo que me estoy preparando para rendir el examen de AWS certified developer associate, necesito que me listes en qué servicios tengo que profundizar más y qué aspectos específicos {Atlas/AWS}
[Context: Notes: Atlas/AWS/DVA-C02/A reforzar.md]
[Timestamp: 2026/08/03 10:44:55]

**ai**: 
<errorChunk>[GoogleGenerativeAI Error]: Error fetching from https://generativelanguage.googleapis.com/v1beta/models/gemini-3.5-flash:streamGenerateContent?alt=sse: [429 ] You exceeded your current quota, please check your plan and billing details. For more information on this error, head to: https://ai.google.dev/gemini-api/docs/rate-limits. To monitor your current usage, head to: https://ai.dev/rate-limit. 
* Quota exceeded for metric: generativelanguage.googleapis.com/generate_content_free_tier_input_token_count, limit: 250000, model: gemini-3.5-flash
Please retry in 30.174989026s. [{"@type":"type.googleapis.com/google.rpc.Help","links":[{"description":"Learn more about Gemini API quotas","url":"https://ai.google.dev/gemini-api/docs/rate-limits"}]},{"@type":"type.googleapis.com/google.rpc.QuotaFailure","violations":[{"quotaMetric":"generativelanguage.googleapis.com/generate_content_free_tier_input_token_count","quotaId":"GenerateContentInputTokensPerModelPerMinute-FreeTier","quotaDimensions":{"model":"gemini-3.5-flash","location":"global"},"quotaValue":"250000"}]},{"@type":"type.googleapis.com/google.rpc.RetryInfo","retryDelay":"30s"}]</errorChunk>
[Timestamp: 2026/08/03 10:45:34]

**user**: sabiendo que me estoy preparando para rendir el examen de AWS certified developer associate y que hay notas que tienen la propiedad incorrect == true , necesito que me listes en qué servicios tengo que profundizar más y qué aspectos específicos {Atlas/AWS}
[Context: Notes: Atlas/AWS/DVA-C02/A reforzar.md]
[Timestamp: 2026/08/03 10:47:26]

**ai**: Basado en el análisis de tus notas y los resultados de las preguntas marcadas como `incorrecta: true` en tu bóveda, he identificado los servicios y conceptos clave donde estás teniendo dificultades.

Para el examen **AWS Certified Developer Associate (DVA-C02)**, debes profundizar en los siguientes puntos:

### 1. AWS Lambda (Servicio Crítico)
Tienes varias preguntas incorrectas relacionadas con la configuración y el comportamiento de Lambda.
*   **Aspectos a reforzar:**
    *   **Integración con VPC:** Entender por qué una Lambda en una subnet privada pierde acceso a internet y cómo solucionarlo (NAT Gateway vs. VPC Endpoints).
    *   **Destinos (Destinations):** Diferenciar cuándo usar DLQ (Dead Letter Queues) vs. Lambda Destinations para manejar fallos en invocaciones asíncronas.
    *   **Event Source Mapping:** Profundizar en cómo Lambda hace "poll" de fuentes como [[Simple Queue Service|SQS]], Kinesis o DynamoDB Streams.
    *   **Performance:** Entender que aumentar la memoria también aumenta la capacidad de CPU (y por ende la velocidad de procesamiento).

### 2. Amazon DynamoDB
Es un pilar del examen y tienes dudas sobre su escalabilidad y patrones de acceso.
*   **Aspectos a reforzar:**
    *   **Throttling:** Entender las causas de `ProvisionedThroughputExceededException` (hot partitions, exceso de capacidad).
    *   **Índices (GSI vs LSI):** Tienes dudas sobre cuándo crear uno u otro. Recuerda: los GSI permiten cambiar la clave de partición, los LSI solo la clave de ordenamiento (sort key).
    *   **Streams:** Entender que son la forma nativa de reaccionar a cambios en la tabla (triggers para Lambda).

### 3. Seguridad y Gestión de Secretos
Tienes varias notas sobre cómo manejar credenciales de forma segura.
*   **Aspectos a reforzar:**
    *   **Secrets Manager vs. Parameter Store:** Recuerda que Secrets Manager es el único con **rotación automática nativa** para RDS. Parameter Store es más barato pero requiere lógica extra (Lambda + EventBridge) para rotar.
    *   **IAM Policies:** Reforzar el principio de *Least Privilege*. Tienes dudas sobre cómo restringir acceso a nivel de objeto en S3 (Bucket Policies vs. IAM Policies).
    *   **KMS:** Entender la diferencia entre encriptación *at-rest* (SSE-S3, SSE-KMS) y *in-transit* (SecureTransport).

### 4. CI/CD y Despliegues (CodeSuite)
Las preguntas sobre estrategias de despliegue son muy comunes.
*   **Aspectos a reforzar:**
    *   **CodeDeploy:** Diferenciar claramente entre *In-place* (downtime) y *Blue/Green* (zero downtime).
    *   **Estrategias de tráfico:** Entender `Canary` (porcentaje inicial, luego el resto) vs. `Linear` (incrementos constantes).
    *   **Hooks:** El orden de ejecución de los hooks en `appspec.yml` (`ApplicationStop` -> `BeforeInstall` -> `AfterInstall` -> `ApplicationStart`).

### 5. Networking (VPC)
*   **Aspectos a reforzar:**
    *   **VPC Endpoints:** Diferencia entre *Interface Endpoints* (PrivateLink) y *Gateway Endpoints* (S3 y DynamoDB).
    *   **VPC Flow Logs:** Son la herramienta principal para troubleshooting de conectividad (ver si el tráfico llega o es bloqueado por SG/NACL).

---

### Plan de acción recomendado:
1.  **Revisa tus notas de "Incorrectas":** He notado que tienes dudas específicas en preguntas de *ExamTopics* que ya has guardado. Vuelve a leer la explicación de por qué fallaste en:
    *   `Lambda processing error` (DLQ).
    *   `Lambda slow processing` (Iterator age y memoria).
    *   `Batch rq a Dynamo` (Manejo de `UnprocessedKeys`).
2.  **Práctica de Laboratorio:** Si puedes, crea un pequeño stack con SAM que incluya una Lambda, un S3 y un DynamoDB, y fuerza errores (ej. quita permisos IAM) para ver qué logs aparecen en CloudWatch.
3.  **Enfoque en "Least Operational Overhead":** Muchas preguntas del examen buscan la solución más simple. Si una opción requiere crear una Lambda extra para algo que AWS ya hace nativamente (como rotar credenciales con Secrets Manager), esa opción suele ser incorrecta.

¿Quieres que profundice en la explicación de alguno de estos servicios en particular?
[Timestamp: 2026/08/03 10:47:38]

**user**: ¿de qué trataban específicamente las preguntas que respondí incorrectamente o que me quedaron dudas? haceme un listado, por favor {Atlas/AWS}
[Context: Notes: Atlas/AWS/Lambda.md]
[Timestamp: 2026/08/03 11:17:39]

**ai**: 
<errorChunk>[GoogleGenerativeAI Error]: Error fetching from https://generativelanguage.googleapis.com/v1beta/models/gemini-3.1-flash-lite:streamGenerateContent?alt=sse: [429 ] You exceeded your current quota, please check your plan and billing details. For more information on this error, head to: https://ai.google.dev/gemini-api/docs/rate-limits. To monitor your current usage, head to: https://ai.dev/rate-limit. 
* Quota exceeded for metric: generativelanguage.googleapis.com/generate_content_free_tier_input_token_count, limit: 250000, model: gemini-3.1-flash-lite
Please retry in 44.411570014s. [{"@type":"type.googleapis.com/google.rpc.Help","links":[{"description":"Learn more about Gemini API quotas","url":"https://ai.google.dev/gemini-api/docs/rate-limits"}]},{"@type":"type.googleapis.com/google.rpc.QuotaFailure","violations":[{"quotaMetric":"generativelanguage.googleapis.com/generate_content_free_tier_input_token_count","quotaId":"GenerateContentInputTokensPerModelPerMinute-FreeTier","quotaDimensions":{"location":"global","model":"gemini-3.1-flash-lite"},"quotaValue":"250000"}]},{"@type":"type.googleapis.com/google.rpc.RetryInfo","retryDelay":"44s"}]</errorChunk>
[Timestamp: 2026/08/03 11:18:19]

**user**: ¿de qué trataban específicamente las preguntas que respondí incorrectamente o que me quedaron dudas? haceme un listado, por favor {Atlas/AWS}
[Timestamp: 2026/08/03 11:18:36]

**ai**: ¡Claro! Basándome en tus notas y las preguntas marcadas como `incorrecta: true` o con `dudas: true`, he compilado un listado detallado de los temas y servicios específicos en los que tienes que profundizar para el examen AWS Certified Developer Associate (DVA-C02).

Aquí tienes el desglose:

### 1. AWS Lambda (Configuración, Despliegue y Errores)

*   **Gestión de mensajes de error (asíncronos y Event Source Mapping):**
    *   Necesitas entender mejor cómo se gestionan los mensajes de error en invocaciones asíncronas y con Event Source Mapping, especialmente el tema de los *batches de error*. (Duda en [[Lambda]])
    *   **Pregunta incorrecta:** [[Lambda processing error]] - Fallo en el procesamiento de órdenes por Lambda asíncrona sin errores en logs. La solución correcta es inspeccionar la *Dead Letter Queue (DLQ)* de Lambda.
    *   **Pregunta incorrecta:** [[Lambda as destination of lambda]] - Manejo de timeouts de una Lambda con una segunda Lambda. La solución correcta es usar *Lambda Destinations*.
*   **Despliegue y versiones (Aliases y Canary):**
    *   No terminas de entender el *Canary deployment* con aliases y sus casos de uso. (Duda en [[Lambda]])
    *   **Pregunta incorrecta:** [[Enable Lambda 4 test w-o affecting customer usage]] - Desplegar nueva versión de Lambda para testing sin afectar a clientes usando alias de API Gateway. La solución correcta implica usar un *alias ponderado* para dirigir un porcentaje de tráfico a la nueva versión.
    *   **Pregunta incorrecta:** [[Lambda version handling]] - Necesidad de poder volver a versiones anteriores de una función Lambda con el menor overhead. La solución correcta es usar *alias de función* para diferentes versiones.
*   **Conectividad y VPC:**
    *   **Pregunta incorrecta:** [[Lamda conn 2 private subnet]] - Una función Lambda en una subred privada pierde acceso a una API pública. La solución correcta es asegurar que el tráfico saliente de la subred privada se enrute a un *NAT Gateway público*.
    *   **Pregunta incorrecta:** [[Lambda acc 2 private subnet r]] - Acceso seguro de Lambda a un clúster Aurora en subredes privadas sin cruzar internet público. La solución correcta es configurar la VPC, subredes y un *security group* para las funciones Lambda.
    *   **Pregunta incorrecta:** [[Conn Lambda 2 private RDS]] - Conectar funciones Lambda a una instancia RDS MySQL en una subred privada. La solución correcta es crear funciones Lambda *dentro de la VPC* con la política `AWSLambdaVPCAccessExecutionRole` y modificar el security group de RDS.
*   **Almacenamiento y dependencias:**
    *   **Pregunta incorrecta:** [[Lib storage in Lambda]] - Centralizar y versionar librerías compartidas (100MB) para funciones Lambda. La solución correcta es crear una *Lambda layer*.
    *   **Pregunta incorrecta:** [[File storage common 2 instances of Lambda]] - Compartir archivos de resultados y logs entre instancias de Lambda y recursos on-premises. La solución correcta es usar un sistema de archivos *Amazon EFS*.
    *   Duda: "¿se puede montar un EFS en una Lambda??" (Duda en [[File storage common 2 instances of Lambda]])
    *   **Pregunta incorrecta:** [[Lx procss heavy video footage]] - Procesar archivos de video pesados (1-2GB) con Lambda de forma optimizada. La solución correcta es aumentar el tamaño del *almacenamiento efímero* a 2GB y copiar los archivos al directorio `/tmp`.
    *   **Pregunta incorrecta:** [[Encryption of data stored in tmp]] - Encriptar datos temporales escritos en `/tmp` de una función Lambda para una aplicación altamente segura. La solución correcta es usar una clave KMS para generar una clave de datos y encriptar los datos antes de escribir en `/tmp`.
*   **Rendimiento y escalabilidad:**
    *   **Pregunta incorrecta:** [[Lambda slow processing]] - Aumentar la velocidad de procesamiento de una Lambda que consume Kinesis Data Streams con `iterator age` creciente. Las soluciones correctas son *aumentar el número de shards* del stream y *aumentar la memoria* asignada a la función Lambda.
    *   Duda: `iterator age metric` (Duda en [[Lambda slow processing]])
    *   **Pregunta incorrecta:** [[Increase Lambda speed]] - Mejorar el rendimiento de una función Lambda `CPU-bound`. La solución correcta es *aumentar la memoria* asignada a la función.
*   **Monitoreo y Testing:**
    *   **Pregunta incorrecta:** [[Lambda monitored by CW Logs Insights]] - Activar CloudWatch Logs Insights para funciones Lambda usando un template SAM. La solución correcta es agregar la *extensión Lambda Insights* y la política `CloudWatchLambdaInsightsExecutionRolePolicy`.
    *   Duda: `CW Logs Insights` (Duda en [[Lambda monitored by CW Logs Insights]])
    *   **Pregunta incorrecta:** [[Testear Lambda en local]] - Probar una función Lambda específica localmente en una aplicación serverless CDK usando SAM CLI. La solución correcta es usar `cdk synth` y `sam local invoke`.
    *   Duda: `CDK SYNTH` (Duda en [[Testear Lambda en local]])
    *   **Pregunta incorrecta:** [[Get Lambda event ID]] - Obtener el ID de evento de Lambda para logs. La solución correcta es obtener el ID de la solicitud del objeto `context` y configurar la aplicación para escribir logs en la salida estándar.
    *   **Pregunta incorrecta:** [[Get data on Lambda delay]] - Medir la latencia entre una función Lambda y un bucket S3 cuando la escritura es lenta. La solución correcta es *habilitar AWS X-Ray* en la función Lambda y seleccionar la línea entre Lambda y S3 en el mapa de trazas.
*   **Permisos:**
    *   **Pregunta incorrecta:** [[Allow usr acc 2 Lambda invok']] - Configurar la autenticación de URLs de funciones Lambda para que un grupo IAM QA pueda invocarlas. La solución correcta es crear un script CLI para agregar una URL de función Lambda con tipo de autenticación `AWS_IAM` y otro script para crear una política basada en identidad IAM que permita `lambda:InvokeFunctionUrl` al ARN del grupo QA.
    *   Duda: Diferencia entre opciones A y C en [[Allow usr acc 2 Lambda invok']] (relacionado con políticas IAM).
*   **Cálculos y Concurrencia:**
    *   **Pregunta incorrecta:** [[Calculations w Lambda]] - Asegurar un cálculo preciso del promedio móvil en una función Lambda que consume [[Simple Queue Service|SQS]]. La solución correcta es establecer la *concurrencia reservada* de la función en 1 y almacenar el promedio en ElastiCache.

### 2. Amazon DynamoDB (Modelado, Rendimiento y Operaciones)

*   **Índices (LSI vs GSI):**
    *   Necesitas leer la teoría para entender las *diferencias de uso entre LSI y GSI*. (Duda en [[DynamoDB]])
    *   Duda: "¿qué diferencia hay entre que una prop sea partition key o sort key? ¿cómo éso encaja con GSI y LSI? ¿qué casos de usos tiene cada uno?" (Duda en [[DynamoDB querying w GSI y LSI]])
    *   Duda: "qué significa que no quiera recrear la tabla? ¿que no quiere crear una nueva en que el customer_type sea la partition key?" (Duda en [[DynamoDB querying w GSI y LSI]])
*   **Throttling y resiliencia:**
    *   **Pregunta incorrecta:** [[Batch rq a Dynamo]] - Aumentar la resiliencia de una aplicación que usa `BatchGetItem` y recibe `UnprocessedKeys`. Las soluciones correctas son *reintentar con exponential backoff y delay random* y *aumentar la capacidad de lectura provisionada*.
    *   **Pregunta incorrecta:** [[Handle DynamoDB throttling]] - Eliminar el throttling y cargar datos de forma más consistente en DynamoDB con cargas de tráfico variables. La solución correcta es refactorizar la función Lambda en dos, usando una cola [[Simple Queue Service|SQS]] intermedia.
    *   **Pregunta incorrecta:** [[DynamoDB ProvisionedThroughputExceededException related 2 partition key]] - Resolver `ProvisionedThroughputExceededException` cuando la clave de partición es `country` y hay un aumento de jugadores en un país específico. La solución correcta es *revisar la clave primaria para usar identificadores más únicos*.
    *   Duda: "¿qué implica el partition key?" (Duda en [[DynamoDB ProvisionedThroughputExceededException related 2 partition key]])
    *   Duda: "`ThroughPutExceededException` — la razón por la que no es recomendado solucionar este problema mediante el aumento de RCU (en contraste a usar DAX) es sólamente porque incurriríamos en un gasto mayorc, ¿cierto?" (Duda en [[DynamoDB]])
*   **Escrituras condicionales y transacciones:**
    *   Duda: `conditional writes` — el valor de `--expresion-attribute-values` puede definirse inline o siempre debe ser un .json? (Duda en [[DynamoDB]])
    *   Duda: `conditional write` — si no se cumple condición, ¿no se cobra la request? (Duda en [[DynamoDB]])
*   **Integración con Lambda y Streams:**
    *   Duda: `DynamoDB Streams` — ¿por qué el source de lambda se tiene que definir como event source map? (Duda en [[DynamoDB]])
    *   Duda: Leer más sobre DynamoDB streams (Duda en [[Near real-time processing triggered by up 2 S3]])
    *   Duda: `DDB y notifications` — ¿DDB sólo se integra con KDS, KDL, Lambda o S3? (Duda en [[DynamoDB]])
*   **DAX y PartiQL:**
    *   Duda: `DAX` — ¿qué son cluster y node? (Duda en [[DynamoDB]])
    *   Duda: `PartiQL` — can only b accesed via console or can the syntax b used via the code that uses the sdk? (Duda en [[DynamoDB]])
*   **Patrones de S3 con DynamoDB:**
    *   Duda: `S3 patterns` — ¿qué diferencia hay entre el pattern de larg object y el de S3 object indexing? (Duda en [[DynamoDB]])
*   **Copias de tablas y control de acceso:**
    *   Duda: `table copy` — ¿hacerlo a mano con custom code va a ser más caro que a través de backup o glue, cierto? (Duda en [[DynamoDB]])
    *   Duda: `fine-grained access control` — en el IAM Role, ¿para qué sirve la propiedad LeadingKeys? (Duda en [[DynamoDB]])

### 3. Amazon S3 (Seguridad, Eventos y Acceso)

*   **CORS:**
    *   Duda: `CORS` — ver el hands-on & ampliar (Duda en [[Simple Storage Service]])
*   **URLs Pre-firmadas:**
    *   Duda: `S3 Pre-Signed URL` — ampliar (Duda en [[Simple Storage Service]])
    *   **Pregunta incorrecta:** [[Acc private S3 securely]] - Compartir y acceder de forma segura a archivos en un bucket S3 privado con una aplicación serverless. La solución correcta es usar *S3 presigned URLs*.
*   **Eventos y Notificaciones:**
    *   **Pregunta incorrecta:** [[S3 event doesn't trigger Lambda]] - Por qué una notificación de evento S3 para archivos grandes no activa una Lambda. La solución correcta es que la *política basada en recursos* de la función Lambda no tiene los permisos necesarios.
    *   Duda: "The S3 event notification does not activate for files that are larger than 1,000 MB. -- ¿por qué sería así?" (Duda en [[S3 event doesn't trigger Lambda]])
    *   Duda: "Lambda functions cannot be invoked directly from an S3 event. -- falso, ¿no existe para éso el event notification?" (Duda en [[S3 event doesn't trigger Lambda]])
    *   **Pregunta incorrecta:** [[Trigger Lambda by up files 2 S3]] - Invocar una función Lambda cuando se sube un archivo .csv a S3. Las soluciones correctas son crear una *regla de EventBridge* para el evento de creación de objeto S3 y agregar un *trigger a la función Lambda*.
    *   Duda: "¿para éste fin no se podrían usar las S3 event notifications?" (Duda en [[Trigger Lambda by up files 2 S3]])
*   **Encriptación:**
    *   **Pregunta incorrecta:** [[Encrypt objs 2 prevent 3P acc 2 them]] - Prevenir el acceso de terceros a documentos subidos a S3 mediante encriptación. La solución correcta es *Server-side encryption with AWS KMS keys (SSE-KMS)*.
    *   Duda: "¿por qué no A?" (Duda en [[Encrypt objs 2 prevent 3P acc 2 them]])
*   **Control de versiones:**
    *   Duda: `Object Lock` -- is this a thing?? (Duda en [[Keep certain ver of objects in S3]])
    *   Duda: "con la bucket policy se podría lograr ésto?" (Duda en [[Keep certain ver of objects in S3]])
*   **Acceso y Permisos:**
    *   **Pregunta incorrecta:** [[Acc permissions w bucket]] - Solución más segura para que una aplicación EC2 liste objetos en un bucket S3. La solución correcta es actualizar la política IAM de EC2 para incluir `S3:ListBucket`.

### 4. Seguridad (IAM, KMS, Secrets Manager, Parameter Store)

*   **Secrets Manager y rotación de credenciales:**
    *   Duda: `Secrets Manager` — integración con [[Atlas/AWS/CloudFormation]] -- ¿cómo se implementa y para qué casos de uso? (Duda en [[Secrets Manager]])
    *   Duda: `SecretRDSAttachment` -- ¿en el template de qué recurso tengo que linkear a la instancia de RDS para que rote? (Duda en [[Secrets Manager]])
    *   **Pregunta incorrecta:** [[Store n retrieve db creds in Lambda]] - Almacenar y recuperar credenciales de base de datos de forma segura para múltiples Lambdas sin actualizaciones de código/configuración. La solución correcta es almacenar en *Secrets Manager* y acceder al secreto *en tiempo de ejecución*.
    *   Duda: "¿por qué es más seguro acceder at runtime que tener una env var que refiera a la ARN del secreto? ¿qué diferencia habría a nivel de código?" (Duda en [[Store n retrieve db creds in Lambda]])
*   **Parameter Store y políticas:**
    *   Duda: `secrets storage` — ¿[[diferencias entre KMS, Secrets Manager y Parameter Store]]? (Duda en [[SSM Parameter Store]])
    *   Duda: `Secrets Manager integration` — ¿cómo funciona esa integración? (Duda en [[SSM Parameter Store]])
    *   **Pregunta incorrecta:** [[Store config vars, set exp date n notif user when exp date is near]] - Almacenar variables de configuración con fecha de caducidad y notificación previa. La solución correcta es usar un *parámetro avanzado* en Parameter Store y establecer políticas de expiración y notificación.
    *   Duda: "¿difgerencia entre parámetro standard y advanced?" (Duda en [[Store config vars, set exp date n notif user when exp date is near]])
    *   Duda: "Set Expiration and ExpirationNotification policy types. -- is that a thing??" (Duda en [[Store config vars, set exp date n notif user when exp date is near]])
*   **KMS y acceso cross-account:**
    *   Duda: `customer-managed` -- ¿se paga $1 POR KEY o por usar el servicio? (Duda en [[Key Management Service]])
    *   Duda: `imported keys` -- ¿caen dentro de la definición de "customer-owned" o son una categoría diferente? (Duda en [[Key Management Service]])
    *   Duda: `GenerateDataKey` -- el envelope con la file encriptada ¿dónde queda? (Duda en [[Key Management Service]])
    *   Duda: `GenerateRandom` -- ¿para qué se usa? (Duda en [[Key Management Service]])
    *   Duda: `IAM policies` -- ¿qué diferencia hay entre IAM role session y Federated user session? (Duda en [[Key Management Service]])
    *   Duda: `encrypt'` -- ¿qué es RSA? (Duda en [[Key Management Service]])
    *   Duda: `policies` -- ¿sólo se pueden asignar policies a las CMK o a cualquier tipo de key? (Duda en [[Key Management Service]])
    *   Duda: `integration w/ Lambda` -- ¿qué diferencia hay entre el in-flight encrypt' y las encrypted variables? (Duda en [[Key Management Service]])
    *   **Pregunta incorrecta:** [[Allow KMS key acc from x-acc]] - Permitir que una clave KMS en una cuenta de desarrollo sea accesible desde una cuenta de producción. La solución correcta es crear una *nueva clave KMS administrada por el cliente* en la cuenta de desarrollo y especificar la cuenta de producción en la política de clave.
    *   **Pregunta incorrecta:** [[Copy AMIs 2 another R]] - Encriptar AMIs no encriptadas al copiarlas a otra región. La solución correcta es *crear nuevas AMIs encriptadas* y copiarlas.
    *   Duda: "¿Para qué se usa exactamente [[Certificate Manager]] y cómo se articula con los ss que usan [[in-flight encryption]]?" (Duda en [[Copy AMIs 2 another R]])
    *   Duda: "¿existe el encryption by default?" (Duda en [[Copy AMIs 2 another R]])
*   **Hiding PII:**
    *   **Pregunta incorrecta:** [[Hiding PII]] - Asegurar que no se filtre PII de instancias EC2 cuando se usa X-Ray y los traces van a CloudWatch. La solución correcta es *instrumentar manualmente el SDK de X-Ray* en el código de la aplicación.
    *   Duda: `Open Telemetry` (Duda en [[Hiding PII]])
    *   Duda: `X-Ray -- Auto-instrumentation agent` (Duda en [[Hiding PII]])
*   **Encriptación de datos sensibles:**
    *   **Pregunta incorrecta:** [[Encrypt x portions of sensitive user data]] - Encriptar porciones específicas de datos sensibles en solicitudes de usuario manejadas por CloudFront y Lambda. La solución correcta es configurar la distribución de CloudFront para usar *Field-Level Encryption* con una clave KMS asimétrica.
    *   Duda: `WAF` (Duda en [[Encrypt x portions of sensitive user data]])

### 5. Networking (VPC, Endpoints, Security Groups, NACL)

*   **VPC Endpoints:**
    *   Duda: "¿el flujo que llega a través del GW y la interface pasa antes por la NAT? ¿Cómo se integran estos RR al circuito de conectividad en que están el IGW, NACL y SG?" (Duda en [[VPC EP]])
    *   Duda: "GW vs. Interface -- ¿uno se instancia en la subnet privada y el otro en la pública?" (Duda en [[VPC EP]])
*   **Control de tráfico (SG, NACL):**
    *   Duda: `Control de tráfico` — ¿a qué niveles se puede hacer? Security groups es para EC2, ¿NACL para donde? ¿Era para a nivel de red o de VPN? Repasar qué contiene a qué. (Duda en [[Elastic Compute Cloud]])
    *   Duda: `Network Access Control List` — ¿qué diferencia hay entre ésto y la [[route table]]? (Duda en [[Network Access Control List]])

### 6. CI/CD (CodePipeline, CodeDeploy, SAM)

*   **CodeDeploy y estrategias de despliegue:**
    *   **Pregunta incorrecta:** [[Using CodePipeline]] - Ejecutar unit tests en CodePipeline para un repositorio GitHub con el menor overhead. Las soluciones correctas son crear un *proyecto CodeBuild* y agregar una *nueva etapa* después de la etapa de origen.
    *   **Pregunta incorrecta:** [[CodeDeploy hooks order]] - Orden correcto de los hooks del ciclo de vida de CodeDeploy para un despliegue in-place. La solución correcta es `AppStop -> BeforeInstall -> AfterInstall -> AppStart`.
    *   Duda: `in-place deployments` -- ?? existe otro tipo de deploy?? qué diferencia existe?? (Duda en [[CodeDeploy hooks order]])
    *   **Pregunta incorrecta:** [[Exponer new ver in ECS by percentage over time]] - Desplegar una nueva versión de aplicación en [[Elastic Container Service|ECS]] con CodeDeploy, exponiendo inicialmente el 10% del tráfico durante 15 minutos, luego el resto. La configuración predefinida correcta es `CodeDeployDefault.ECSCanary10Percent15Minutes`.
    *   Duda: "¿qué diferencia hay entre A y C?" (Duda en [[Exponer new ver in ECS by percentage over time]])
    *   **Pregunta incorrecta:** [[ASG deployment strategy]] - Solución más rentable para un problema de despliegue en Elastic Beanstalk (política all-at-once, 5 instancias EC2, rendimiento degrada si < 4). La solución correcta es cambiar la política de despliegue a *rolling with additional batch* con un tamaño de batch de 1.
    *   **Pregunta incorrecta:** [[Testing code in EBeanstalk w zero down time]] - Desplegar y probar código y versión de plataforma en Elastic Beanstalk con cero downtime. La solución correcta es realizar una *actualización inmutable*.
    *   Duda: "¿diferencia entre C y D?" (Duda en [[Testing code in EBeanstalk w zero down time]])
*   **SAM y testing local:**
    *   **Pregunta incorrecta:** [[Testear Lambda en local]] - Probar una función Lambda específica localmente en una aplicación serverless CDK usando SAM CLI. La solución correcta es usar `cdk synth` y `sam local invoke`.
    *   Duda: `CDK SYNTH` (Duda en [[Testear Lambda en local]])
*   **Lambda@Edge y despliegue:**
    *   **Pregunta incorrecta:** [[SAM stack deploy fail 'cause of Lambda@Edge]] - Por qué falla un despliegue de stack SAM al desplegar Lambda@Edge en `eu-west-1`. La razón es que las funciones *Lambda@Edge solo se pueden crear en la región `us-east-1`*.

### 7. Monitoreo y Observabilidad (CloudWatch, X-Ray)

*   **CloudWatch Agent:**
    *   **Pregunta incorrecta:** [[Gather perfo info from EB]] - Recopilar información sobre el uso de memoria de una aplicación de procesamiento por lotes en Elastic Beanstalk. La solución correcta es configurar el *agente de Amazon CloudWatch* para rastrear el uso de memoria.
    *   Duda: "¿Qué permite hacer el [[CloudWatch Agent|CW Agent]]?" (Duda en [[Gather perfo info from EB]])
*   **CloudWatch Logs y Métricas:**
    *   **Pregunta incorrecta:** [[Filtering logs in CW Logs]] - Por qué un nuevo filtro de métricas de CloudWatch Logs para excepciones no devuelve resultados. La razón es que CloudWatch Logs solo publica datos de métricas para eventos que ocurren *después de que se crea el filtro*.
    *   **Pregunta incorrecta:** [[Publish on SNS topic on API error]] - Notificar al equipo de soporte en tiempo casi real cuando la tasa de error de una API de terceros supera el 5%. La solución correcta es usar *métricas personalizadas en CloudWatch* y configurar alarmas para notificar al tema SNS.
    *   Duda: "custom metrics in CWatch. config [[CW Alarms]] 2 notify topic. -- creo que sería esta, porque es la más straight forward; pero sólo si se pueden definir custom metrics en CWatch... Aunque creo que las métricas pueden ser sólo relacionadas a la performance, o no...?" (Duda en [[Publish on SNS topic on API error]])
*   **X-Ray:**
    *   **Pregunta incorrecta:** [[Acc STS user creds from CFront distro]] - Obtener credenciales de usuario de STS sin hardcodearlas en una aplicación de redes sociales que usa CloudFront y S3. La solución correcta es agregar una *función Lambda@Edge* a la distribución.
    *   Duda: `CFront fx` -- is that a thing??? (Duda en [[Acc STS user creds from CFront distro]])
*   **CloudWatch Evidently:**
    *   **Pregunta incorrecta:** [[CW Evidently use case]] - Configurar CloudWatch Evidently para trabajar exclusivamente con la Variación A de una prueba A/B. La solución correcta es *agregar un override a la característica* y establecer el identificador del override al ID de usuario del ingeniero.
    *   Duda: `CW Evidently` -- ?? (Duda en [[CW Evidently use case]])

### 8. Amazon API Gateway (Configuración, Caching y Troubleshooting)

*   **Mock Integrations:**
    *   **Pregunta incorrecta:** [[Mock rtas w API-GW]] - Simular diferentes respuestas de backend para una aplicación móvil que llama a API Gateway sin invocar servicios de backend. La solución correcta es usar una *integración mock* y plantillas de mapeo.
    *   Duda: `API Gateway -- proxy integration` (Duda en [[Mock rtas w API-GW]])
*   **Stages y Despliegue:**
    *   **Pregunta incorrecta:** [[API-GW parallel stages]] - Permitir a otros desarrolladores acceder a nuevos endpoints de API Gateway (con incompatibilidad retroactiva) sin afectar a los clientes. La solución correcta es definir una *etapa de desarrollo* en API Gateway y que los desarrolladores apunten a ella.
*   **Rendimiento y Caching:**
    *   **Pregunta incorrecta:** [[API-GW responsiveness]] - Mejorar la capacidad de respuesta de una API Gateway/Lambda con acceso de lectura no autenticado a datos actualizados diariamente. La solución correcta es *habilitar el caching* en API Gateway.
    *   Duda: `VPC EP` (Duda en [[API-GW responsiveness]])
    *   Duda: `usage plans` (Duda en [[API-GW responsiveness]])
*   **Troubleshooting con CloudWatch Metrics:**
    *   **Pregunta incorrecta:** [[API-GW time-out CW metric troubleshooting]] - Qué dos métricas de CloudWatch pueden ayudar a solucionar problemas de timeouts de API Gateway cuando Lambda termina antes del límite. Las métricas correctas son `IntegrationLatency` y `Latency`.
*   **WebSocket APIs:**
    *   **Pregunta incorrecta:** [[Identify client conn'd 2 API-GW]] - Identificar y eliminar un cliente que se conecta y desconecta repetidamente de una API Gateway WebSocket API. Las soluciones correctas son *implementar rutas `$connect` y `$disconnect`* en el servicio de backend y *usar la URL de callback para desconectar al cliente*.
    *   Duda: `API-GW -- ¿qué diferencia hay entre HTTP y REST?` (Duda en [[Identify client conn'd 2 API-GW]])
    *   Duda: `API-GW -- websocket??` (Duda en [[Identify client conn'd 2 API-GW]])
    *   Duda: `API-GW -- remove a client??` (Duda en [[Identify client conn'd 2 API-GW]])

### 9. Amazon RDS (Escalabilidad, Seguridad y Almacenamiento)

*   **Escalabilidad y Réplicas de Lectura:**
    *   Duda: `auto scale` -- ¿cuáles son los criterios? ¿dónde se maneja? ¿cómo se settea? no entendí (Duda en [[Relational DB Service]])
    *   Duda: `read replicas & multi-az` -- ¿dónde se settea para usar uno u otro? (Duda en [[Relational DB Service]])
*   **Almacenamiento y Encriptación:**
    *   Duda: `storage backed by EBS` -- ¿éso qué significa? ¿cómo se usa EBS tras bambalinas? (Duda en [[Relational DB Service]])
    *   Duda: `ManageMasterUserPassword` -- ¿puede settearse desde la consola o sólo desde [[CloudFormation]]? (Duda en [[Relational DB Service]])
*   **RDS Proxy:**
    *   **Pregunta incorrecta:** [[Lambda 2 many rqs when acc 2 RDS]] - Hacer una aplicación API Gateway/Lambda/RDS resiliente a errores de "demasiadas conexiones" durante picos de uso impredecibles. La solución correcta es usar *Amazon RDS Proxy*.

### 10. Amazon Kinesis Data Streams (Producers, Consumers y Escalabilidad)

*   **Interacción Producer/Consumer:**
    *   Duda: `Kinesis` — ¿sí o sí se necesita que haya un producer haciendo de pasa-manos de la real-time data hacia Data Stream o podrían existir casos en los que un device IoT, por ejemplo, transmita directamente hacia KDS? (Duda en [[Kinesis Data Streams]])
*   **Enhanced Fan-Out:**
    *   Duda: `Kinesis` — ¿cómo funciona el enhanced fan-out? (Duda en [[Kinesis Data Streams]])
*   **Visualización de la arquitectura:**
    *   Duda: `Kinesis` — ¿cómo se vería gráficamente la relación entre producer, kinesis, shards, consumer, workers? ¿dónde entrarían KDS Data Analytics y K Firehose? (Duda en [[Kinesis Data Streams]])
*   **Firehose y PII:**
    *   **Pregunta incorrecta:** [[Delete PII from Firehose 2 store in S3]] - Eliminar PII de Kinesis Data Firehose y almacenar datos transformados en S3. La solución correcta es usar una *función Lambda* para la transformación de datos.
    *   Duda: "¿qué es un delivery stream y qué tiene de diferente con [[Kinesis Data Streams|KDS]]?" (Duda en [[Delete PII from Firehose 2 store in S3]])

### 11. Amazon Cognito (Autenticación y Autorización)

*   **User Pools vs Identity Pools:**
    *   **Pregunta incorrecta:** [[Federated login in AWS]] - Usar cuentas de redes sociales para registrarse en una nueva aplicación. La solución correcta es usar *Amazon Cognito User Pools*.
    *   **Pregunta incorrecta:** [[Employee directory]] - Reescribir un directorio de empleados para usar servicios de AWS, almacenando datos personales y fotos de alta resolución, con funciones de búsqueda y recuperación. La solución correcta es almacenar datos en *DynamoDB* y fotos en *S3*.
    *   Duda: "¿qué diferencia hay entre **user** pools y **identity** pools?" (Duda en [[Amazon Cognito]])
*   **Acceso para usuarios autenticados y no autenticados:**
    *   **Pregunta incorrecta:** [[Handle acc 2 rr 4 auth n unauth usrs]] - Implementar un proceso de autenticación para una aplicación multimedia que permite acceso a usuarios invitados y autenticados. Las soluciones correctas son crear un *Amazon Cognito Identity Pool* y configurar roles IAM para usuarios autenticados y no autenticados.

### 12. AWS CloudFormation (Templates y Gestión de Recursos)

*   **Protección contra eliminación:**
    *   **Pregunta incorrecta:** [[CloudFormation r deletion protection]] - Prevenir la eliminación accidental de la base de datos y asegurar que el despliegue de la aplicación no cause la eliminación/recreación de la DB. Las soluciones correctas son usar `DeletionPolicy: Retain` para el recurso de la base de datos y *actualizar la política de stack* de CloudFormation.
    *   Duda: "¿[[CloudFormation]] stack set??" (Duda en [[CloudFormation r deletion protection]])
*   **Parámetros y funciones intrínsecas:**
    *   Duda: `dynamic refs` -- ¿refiere a hacer referencia a valores dinámicos o a crear valores de forma dinámica en el template? (Duda en [[CloudFormation]])
    *   Duda: `Parameters` -- ¿entonces sólo pueden definirse dentro de las secciones de Resources o Outputs y no como una sección propia? (Duda en [[CloudFormation]])
    *   Duda: `Outputs`, `Rules`, `Conditions` -- is a stand-alone section or is it a subsection? (Duda en [[CloudFormation]])
    *   Duda: `Mappings`, `Conditions` -- ? (Duda en [[CloudFormation]])
    *   Duda: `Transform` -- ¿cómo está relacionado con [[Serverless App Model|SAM]]? (Duda en [[CloudFormation]])
    *   Duda: no termino de entender cómo funcionan las funciones... ¿qué diferencia hay entre `Ref` y `!Ref` y `Fn::GetAttr` y `!GetAttr`? (Duda en [[CloudFormation]])

### 13. Amazon EC2 (Tráfico, Almacenamiento y AMIs)

*   **AMIs y encriptación:**
    *   Duda: `Replicating an AMI in another R` — ¿qué diferencia hay entre *copy* y *build*? (Duda en [[Replicating an AMI in another R]])
*   **Almacenamiento:**
    *   Duda: `EBS & Instance Store` -- ¿cómo harías para compartir las files? (Duda en [[Migración de on-prem a cloud filesys]])
    *   Duda: `Cost comparison` entre todas las opciones de almacenamiento (Duda en [[Migración de on-prem a cloud filesys]])
    *   Duda: `micro-instancia` -- ?? (Duda en [[Migración de on-prem a cloud filesys]])
    *   Duda: `montaje local de S3` -- ?? (Duda en [[Migración de on-prem a cloud filesys]])

### 14. Amazon ElastiCache (Estrategias de Caching)

*   **Modo Clúster:**
    *   Duda: `cluster-mode`?? (Duda en [[ElastiCache]])
*   **Sticky Sessions:**
    *   Duda: `ELB Sticky Sessions` — Ver video — Ampliar (Duda en [[Elastic Load Balancer]])
*   **Almacenamiento de estado de sesión:**
    *   **Pregunta incorrecta:** [[Session state storage]] - Mejor opción para almacenar el estado de sesión de una aplicación web de comercio electrónico tolerante a fallos y altamente escalable. La solución correcta es *Amazon ElastiCache*.
    *   Duda: "¿qué diferencia hay en la gestión del session state entre los 2 que elegí?" (Duda en [[Session state storage]])

---

Este listado te proporciona un mapa claro de dónde enfocar tus esfuerzos. Te recomiendo:

1.  **Revisar las explicaciones de las preguntas incorrectas:** Entender por qué la respuesta correcta es la que es, y por qué tus opciones fueron incorrectas.
2.  **Profundizar en los conceptos de las dudas:** Utiliza la documentación oficial de AWS, videos explicativos o laboratorios prácticos para aclarar cada punto.
3.  **Practicar con escenarios similares:** Una vez que entiendas los conceptos, intenta resolver problemas parecidos para solidificar tu conocimiento.

¡Mucho éxito en tu preparación para el examen!
[Timestamp: 2026/08/03 11:22:29]