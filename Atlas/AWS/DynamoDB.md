---
dudas: true
tags:
  - DVA02-22
  - database
aliases:
---
### Dudas
- [x] ¿Por qué AWS recomienda usar DynamoDB si es noSQL y muchos de los esquemas de DBs siguen siendo relacionales? — ~~ampliar~~
    
    Porque RDS no escala automáticamente y sólo permite escalado vertical. Y, además, NoSQL no significa que no podés crear modelos relacionales.
    
    De cualquier forma, la idea de Dynamo en sí es: escalabilidad y disponibilidad.
    
- [x] primary keys — ¿a qué se refiere con que la partition key debe ser “diverse” para que la data sea distributed? — ~~ampliar~~
    
    ~~Supongo que se refiere a que la primary key tenga la capacidad de 1. no repetirse y 2. ser un atributo que represente de forma unívoca al ítem.~~
    
    En realidad, quiere decir que el campo pueda tomar la mayor cantidad posible de valores. A más cantidad de valores posibles, más diverse es.
    
    # de valores = # de partition keys
    
    Mientras más valores haya, se combate más eficientemente el prospecto del hot partition.
    
- [x] strongly consistent read — ¿deberemos mandar ConstistentRead=true en cada llamada a la API o puede definirse en la config de la tabla? ¿cómo se vería la estructura de las API calls en ese caso? — ~~ampliar~~
    
    Correcto. Se debe enviar en cada rq de lectura que lo requiera.
    
    No se puede definir a nivel de tabla.
    
    ConsistentRead no es más que una propiedad en el json de la rq.
    
- [x] conditional writes — no termino de entender la conditional expression para IN y BETWEEN AND — ~~ampliar~~
    
    IN (:x, :y, :z) es como en SQL: la condición es que tenga el valor de alguno de los valores del array.
    
    BETWEEN :x AND :y: ídem.
    
    Los elementos de IN y los límites de B/ AND se definen en `--expression-attribute-values`, como si fueran variables de entorno.
    
    En formato JSON, se vería así:
    
    ```json
    {
      "TableName": "Orders",
      "Key": {
        "orderId": { "S": "ord-100" }
      },
      "UpdateExpression": "SET #s = :newStatus",
      "ConditionExpression": "#s IN (:p, :pr)",
      "ExpressionAttributeNames": {
        "#s": "status"
      },
      "ExpressionAttributeValues": {
        ":newStatus": { "S": "SHIPPED" },
        ":p": { "S": "PENDING" },
        ":pr": { "S": "PROCESSING" }
      }
    }
    ```
    
- [x] conditional writes — ¿sólo se pueden definir via CLI o pueden definirse a través del config de la tabla? — ~~ampliar~~
    
    No son configs a nivel de tabla, deben definirse a nivel de rq, so: CLI, console, SDK.
    
- [ ] conditional writes — el valor de `--expresion-attribute-values` puede definirse inline o siempre debe ser un .json? — ampliar
    
    Siempre debe ser un json. Dynamo exije placeholders y ésto por lo tanto implica que el valor de `--e-a-v` será siempre un json.
    
- [x] LSI — ¿qué son los Attrribute Projections y para qué se usan? — ~~ampliar~~
    
    Es un listado de los atributos que se quieren copiar de la main table al índice.
    
- [ ] LSI & GSI — leer teoría para entender diferencias de uso — ampliar
- [ ] PartiQL — can only b accesed via console or can the syntax b used via the code that uses the sdk? — ampliar
- [ ] DAX — ¿qué son cluster y node? — ampliar
- [ ] & Lambda — ¿por qué el source de lambda se tiene que definir como event source map? O sea, entiendo que la configuración de lambda es así: si es stream ⇒ source map PERO quiero saber por qué específicamente. Unx pensaría que el event source mapping es para hacer POLL, pero los Sstreams no hacen PUSH hacia sus targets? — ampliar
- [ ] conditional write — si no se cumple condición, ¿no se cobra la request? porque entiendo que se hace la request a la API y es ésta la que evalua la condición; no se hace en origen sino en la misma API de DynamoDB. Entonces, ¿se cobra por esta request o sólo se cobra el WCU si se realiza efectivamente la actualización? — ampliar
- [x] ¿sólo se pueden storear como máximo en total 400kb de data o éso es por ítem? — ~~ampliar~~
    Es por item.
- [ ] S3 patterns — ¿qué diferencia hay entre el pattern de larg object y el de S3 object indexing? ¿no se guarda exactamente la misma información, en definitiva? — ampliar
    
    Quizás la diferencia sea que en el indexing sólo estamos haciendo GET de md de los objetos, pero en el large object estamos obteniendo la md pero sólo para hacer GET del objeto correspondiente.
    
- [ ] table copy — ¿hacerlo a mano con custom code va a ser más caro que a través de backup o glue, cierto? porque copiar a mano significa hacer PUT por cada ítem que haya en la tabla, lo que implica usar WCU Y RCU para leer los ítems del source. Entiendo que se vuelve caro si tenés MUCHOS ítems, por lo que quizás no siempre sea más caro que usar los otros servicios. ¿Podrías explicarme las diferencia? — ampliar
- [ ] fine-grained access control — en el IAM Role, ¿para qué sirve la propiedad LeadingKeys? ¿Cómo se limita acceso usando éso y qué diferencia hay con limitar at the attribute-level? — ampliar
- [ ] `ThroughPutExceededException` — la razón por la que no es recomendado solucionar este problema mediante el aumento de RCU (en contraste a usar DAX) es sólamente porque incurriríamos en un gasto mayorc, ¿cierto? — ampliar
- [ ] DDB y notifications — ¿DDB sólo se integra con KDS, KDL, Lambda o S3? — ampliar
### Notas
- errores
	- `ThroughputException` pueden ser por dos cosas
	    - hot keys/hot partition
	    - sobrepasado el límite provisionado de R/WCU
	- `UnprocessedKeys` -- no se procesaron todas las solicitudes del lote
		- capacidad
		- sobrecarga temporal
### Palabras clave
- table — NoSQL ⇒ no queries | no aggregation
    - items — rows, max: 400kb ^24ad5b
    - attributes — columns, can b add’d over time
        - data types
            - scalar — string, number, binary, bool, null
            - document — list, map
            - set — string | number | binary sets
    - partitions — donde se almacenan los ítems, se determina a dónde va el ítem en base a un algoritmo que usa el hash, W/RCUs spread’d evenly between partitions
        - `ProvisionedThruputExceededException`
            - reasons — hot keys, hot partition, very large items
            - solution — exponential backoff, distribute partition keys, DynamoDB Accelerator (DAX) 4 read issue
    - primary key -- ==allows 4 UNIQUE id'==
        - types
            - partition key (HASH)
            - HASH + sort key (HASH+RANGE)
    - index — attr project’ = attrs add’d 2 index 2 b used 4 query
        - Local Secondary — created @ table creation, uses main table’s provisioned R/WCU
        - Global Secondary — alt primary key, use case: speed up queries based on non-key attrs, must provision W/RCUs, created @ any moment, throtling? → main table throtles
    - TTL — attr that has expiration time stored as NUMBER, expired items are deleted auto & free (no use of WCU), unix epoch ts, deletion within 40h, process: 1. expire data → 2. delete data, deleted from GSI & LSI
- R/W
    - capacity modes — swichable once every 24h
        - provisioned — pay 4 W/RCUs/hour, capacity plan’d beforehand, can b autoscalable
            - burst capacity — capacity cuando se superó lo provisioned, `ProvisionedThroughputExceededException`? → burst capacity consumed
        - on-demand — default, scaling based on workloads, pay per R/WRU used (RU = request unit), $ $ $ = 2.5 x provisioned
    - reads — RCU = read capacity unit = 1 strongly/second x 4kb = 2 eventually/second x 4kb, > 4kb? $ $ $, bts: data replication in servers, can use filter expressions
        - modes
            - strongly consistent — will always get updated data, RCU x 2, some latency
            - eventually consistent — possibility of getting stale data ‘cause replica’ is done EVENTUALLY
        - calc — strongly/sencond x (item size/4kb)
            - always round-up item size 2 the nearest múltiplo de 4
            - strongly = ítems * (item size/4kb)
            - eventually = ítems/2 * (item size/4kb)
    - writes — WRU = write capacity unit, > 1kb? $ $ $
        - calc — # (items/second) x (item size/1kb)
            - aways round-up to next entero
        - types
            - concurrent — m updates 4 same item, all successfull, all overwritten, not the best type
            - conditional — xpr that determins which items get updated, `condition-expression`
                - conditions
                    - `attribute_exists(attr)`
                    - `attribute_not_exists(attr)` — use cases: not 2 overwrite data
                    - `attribute_type`
                    - `contains`
                    - `begins_with`
                    - `size`
                - optimistic locking — based on conditional writes, an attr works as a version number
            - atomic — se aplica sucesivamente todos los cambios
            - batch — m changes @ once
- PartiQL — SQLish syntax 2 manipulate table, commands: insert | update | select | delete
- Accelerator (DAX) — in-memory cache, use case: when hot key
- Streams — stream of item modif in table, max retention: 24h, use case: react 2 changes in real time, not retroactive #test-question ^9aa407
    - target — [[Kinesis Data Streams|KDS]], [[Lambda]] (process data), Kinesis Data Library apps (process data)
        - Lambda — event source mapping ⇒ lambda needs PULL permissions, sync invocation
    - stream data — `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`
    - shard — just like KDS, por éso lo soporta KDL, provision’d managed by AWS
- CLI
    - `--projection-expression` — attrs 2 retrieve
    - `--filter-expression`
    - pagination — `--page-size`, `--max-items`, `--starting-token` (token que devuelve la rq con —max-items)
- transactions — coordinate CxUD on M items, 1 fails ⇒ all fail, 2W/RCU, ACID=atomicity & consistency & isolation & durability, use cases: financial trans | managin orders | multiplayer games
    - important commands
        - `TransactGetItems`
        - `TransactPutItems`
    - capacity computation — item size denominator logic is same as regular R/W
        - WCU — # writes/second * (item size/1kb) * 2
        - RCU — # writes/second * (item size/4kb) * 2
- use case:Session State cache — common use case, shared cache, serverles opt (en contraste a ElastiCache, que es in-memory)
- partition strategies — 2 better distribute consumption/use
    - W sharding — adds suffix 2 partition key
        - random suffix
        - calculated suffix
- integrations
    - S3
        - large objs pattern — store objs in S3 & metadata in DDB, process: 1. write: store object → store metadata & 2. read: get metadata → get object f(md)
        - S3 object indexing — bucket → notif → lambda → md → DDB
    - DB Migration Service (AWS DMS) — migrate’ from/2
    - Cognito — User Pools, 4 direct user access 2 table, restrict IAM 2 DDB access
- operations
    - table cleanup
        - scan & delete item — $ $ $, very slow
        - drop table & recreate it — faster, cheap
    - table copy
        - AWS Backup — restore from backup
        - AWS Glue — ETL, reads source & writes wherever
        - a mano — custom code, scan & PutItem/BatchWriteItem, not the best
- security — VPC EPs 4 access w/o internet, IAM, KMS 4 encrypt @ rest, SSL 4 encrypt in transit
- backup & restore — point-in-time recovery
- global tables — M R, multi-active, needs Stream on
- DDB Local — DDB sim in local PC 4 testing w/o internet