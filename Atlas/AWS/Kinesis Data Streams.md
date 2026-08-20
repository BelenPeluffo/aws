---
dudas: true
tags:
  - DVA02-19
aliases:
  - KDS
---
### Dudas
- [x] Kinesis > Partition key — ~~ver video~~ — ~~ampliar~~
    
    Kinesis ya de por sí ordena según llegada. Pero si tenés muchos shards y querés que algunos mensajes vayan hacia el mismo shard, necesitás especificar el partition key al transmitir el mensaje desde el producer.
    
    Tiene un uso parecido al de `MessageGroupId` pero la funcionalidad que tiene es la de poder dividir el esfuerzo entre shards.
    
- [x] Kinesis > Firehose — ~~ver video~~
    
- [x] Kinesis > shards — ¿por qué sería necesario usar instancias de EC2 para procesar mensajes? ¿la cantidad de shards define el límite de EC2s que se puede usar? — ~~ampliar~~
    
    Porque los shards no son los que procesan sino una especie de vía de transporte de los datos.
    
    Los EC2 en esta pregunta representan una unidad de procesamiento, un worker. En este sentido, es intercambiable con otros servicios de procesamient.
    
    La # de shards sí limita la # de unidades de procesamiento ya que 1 shard sólo puede tener 1 worker asociado.
    
- [ ] Kinesis — ¿sí o sí se necesita que haya un producer haciendo de pasa-manos de la real-time data hacia Data Stream o podrían existir casos en los que un device IoT, por ejemplo, transmita directamente hacia KDS?
    
    No, no se podría. Porque tenés que settear en alguna parte los datos para conectarte a la API. Para éso, sí o sí necesitás que la app o el KDS agent te haga de pasamano.
    
- [x] Kinesis — ¿cómo funciona y qué es el KDS agent? — ~~ampliar~~
    
    Es un producer out-of-the-box básico. Sirve para leer y transmitir logs hacia el Data Stream.
    
    Sólo sirve del lado del producer, nada más.
    
- [x] Kinesis — ¿cómo funcionan los distintos tipos de data transmission (pulling by consumers and pushing by producers)? — ~~ampliar~~
    
    Lo producers SIEMPRE hacen push.
    
    A lo que se refiere con push o pull es cómo EL CONSUMER recibe la información.
    
    En la transmisión standard, los consumers deben hacer pull manual para obtener los datos. En la enhanced, Kinesis se encarga de hacer push a los consumers.
    
    Además, hay una diferencia de capacidades. En la standard, la capacidad es de 2mb en total, por lo que los consumers deben dividirse esa capacidad. En la enhanced, es de 2mb pero para CADA consumer; es decir: tienen capacidad dedicada fija
    
- [ ] Kinesis — ¿cómo funciona el enhanced fan-out? — ~~ampliar~~
    
    Se le dice “enhanced” porque los shards disponibilizan mayor capacidad de transmisión. Para cada cosumer, hay un fijo dedicado de 2mb. Ésto permite menor latencia.
    
    “Fan-out” refiere a la capacidad del shard de permitir un consumo distribuido.
    
    Para determinar cuál de las dos transmisiones usar, simplemente se hace determinando cuál comando usar para consumir los datos: `GetRecords` (standard) ó `SubscribeToShard` (EFO).
    
- [x] Kinesis — ¿qué diferencia hay entre un consumer y un worker? — ~~ampliar~~
    
    El consumer es el target al que se destinan los datos de Kinesis.
    
    Un worker es una unidad lógica que procesa esos datos.
    
    1 consumer → M workers
    
    En este contexto, es que se dice que un shard puede ser procesado por 1 worker por cada consumer. Ésto puede ser confuso al principio, pero lo que tenemos que recordar es que los consumers siempre pueden consumir y procesar en paralelo entre ellos los datos del DS. La única limitación es que no podrán tener varios procesos de lectura internamente, sólo podrá cada uno ejecutar uno solo.
    
- [x] Kinesis — ¿en qué consiste el shard splitting? — ~~ampliar~~
    
    En separar una shard en más shards. Ésto se hace para escalar capadidad de transmisión y capacidad de procesamient, ya que a más shards se pueden usar más workers para procesamiento.
    
- [ ] Kinesis — ¿cómo se vería gráficamente la relación entre producer, kinesis, shards, consumer, workers? ¿dónde entrarían KDS Data Analytics y K Firehose? — ~~ampliar~~
    
    ![[Pasted image 20260720150248.png]]
    
- [x] Kinesis — ¿dónde se define el retention time? — ~~ampliar~~
    
    Se define al A/M un DS.
### Notas
### Palabras clave
- concept— data stream (REAL-TIME, large amounts of data) & storage, consumption in REAL TIME, capacity limited by # shards (1 shard → 1mb IN & 2mb OUT), SNS unsupported, can keep records 4 up 2 365d (defined when A/M)
- components
    - producer — app que envía data a un DS
        - message attrs
            - `PartitionKey` — prod-side, se usa para calcular el shard destino, use case: distribuir cargas entre shards
        - creación — AWS/3rd services ó AWS toolkits/libraries:
            - Kinesis Producer Library (KPL) — para procesar por el producer, puede usarse en vez de usar el SDK, procesa de forma más eficiente ^KPL
            - Kinesis agent — herramienta para enviar datos a Kinesis sin programar producer, caso de uso: envío de logs no relacionado con lógica de negocio, sólo producer-side
		- `PutRecord` / `PutRecords`
    - consumer — app que procesa toda la data de un DS
        - data transmition — ambos se definen desde el lado del consumer: 1. se los registra, 2. se decide el método que se usa: `GetRecords`/`subscribeToShard` (no hay que configurar nada, sólo hacer uso del comando correspondiente)
            - standard — data is PULLED by consumer = manual pull = `consumer.GetRecords`, capacidad: 2mb para repartir entre consumers
            - enhanced fan-out — data is PUSHED by Kinesis = push notifs = `consumer.SubscribeToShard`, capacidad: 2mb para cada consumer
        - creación — ídem producer
            - Kinesis Client Library (KCL) — para procesar por el consumer, es mejor que la SDK para gestionar loadbalancing & multiple consumers (gestión automática de resharding) => facilita lectura/procesamiento de datos desde app ^KCL
            - Kinesis Data Analytics — 2 perform analytics on data streams, source=Kinesis Data Streams
            - Kinesis Data Firehose — batch data transmition, fully managed, autoscales, load data into [[Simple Storage Service|S3]]/Redshift/3rd party/EPs, can perform transformations via [[Lambda]], supports [[SNS]], NEAR real time, native conversion 2 parquet/orc, NO DATA STORAGE #test-question ^kinesis-data-firehose
		- iterator age -- tiempo que registros pasan en KDS sin ser procesados #test-question  ^e8a40e
    - shard — secuence of records, 1 DS → M shards
        - resharding — escalado de capacidad (throughput/paralelismo) en función de la carga, provisioned? → a mano, on-demand? → auto, medios: CLI | consola | SDK
            - splitting — increases # of shards by splitting a shard
            - merging —
    - worker — instancia de procesamiento ejecutada por el consumer, 1 consumer → M workers, limit: dentro de un mismo consumer sólo puede haber 1 worker procesando un shard x
- capacity modes — cómo se gestiona la capacity y cómo te cobra esa capacity
    - provisioned — set shards in advance, can scale manually, pay: shard/hour, use case: predictable data volume
    - on-demand — default: 4MB, autoscales based on history, pay: stream/hour + in/out GB
