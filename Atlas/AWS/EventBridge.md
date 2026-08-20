---
dudas:
tags:
aliases:
  - CW Events
---
### Dudas
- [x] EventBridge — necesito entender bien los elementos que lo componen y cómo interactuan entre sí — ~~ampliar~~
    
    Event bus — canal de comunicación. Diferentes tipos según el source.
    
    Event — es el mensaje
    
    Rule — definición de qué mensajes escuchar y qué hacer con ellos (transform&send o just send)
    
    Event pattern — propiedad que define filtrado
    
- [x] EB — ¿cómo se definen los distintos tipos de event buses (3rd party, custom, etc)? ¿son características de EB o son servicios distintos? — ~~ampliar~~
    
    No son servicios distintos, sin literalmente distintos tipos de event bus disponibles dentro de EB.
    
    Se definen de diferentes formas.
    
    El default se crea solo.
    
    El custom lo creás a mano a través de la acción create-custom-bus.
    
    El de 3P se crea ~solo al activar la integración con el s 3P.
    
- [x] EB — necesito entender cómo funciona el archive de events, a dónde se envían, dónde se define el período de archivado y cómo podés usarlos para replay’em — ~~ampliar~~
    
    Tanto dónde se define el archive como así también dónde se define el período, se hace al crear el archive. Los eventos se almacenan internamente mediante EB y no se tiene acceso a su gestión.
    
    El replay es una acción que tenés que ejecutar manualmente y a la que le referís el archive que querés ejecutar. Lo que sucede es que al hacer replay se envian los eventos del archive hacia el bus y se procesa según las rules actuales. Sirve para evaluar cómo reacciona el sistema.
    
- [x] EB — un event schema es lo mismo que una event rule? ¿qué diferencia hay entre event pattern y event rule? — ~~ampliar~~
    
    Event schema = interfaz esperada del mensaje-evento que ingresará al bus.
    
    Event rule = definición de gestión de los eventos recibidos
    
    Event pattern = condición que se usa dentro de event rule
    
- [x] EB — que las cuentas que van a centralizarse en un event bus en otra cuenta tengan definidas sus event rules significa que esas cuentas también tendrán que hacer uso internamente de EB? — ~~ampliar~~
    
    Sí, así es. Todas las cuentas que envíen al hub deberán tener definida una regla que tenga como target al hub de la cuenta central.
    
    <aside>  
    ☝🏾
    
    En el caso de las apps, se puede ejecutar el PUT de EB directamente en el código sin necesidad de crear una rule del bus. Mientras que el hub central permita el PUT desde la cuenta source, podrá hacerse.
    
    </aside>
    
    A su vez, la cuenta central deberá actualizar la policy del bus para aceptar de source a las otras cuentas.
    
    <aside>  
    ☝🏾
    
    Todas las cuentas tienen habilitado por defecto EB al ser creadas. Y por lo tanto el default bus ya está disponible también.
    
    </aside>
### Notas
### Palabras clave
- EventBridge (fka CW Events) — actions based on cron jobs | r behavior pattern, r criteria can b filter’d, event-driven = push, pay 4: event-IN & event-OUT & archive storage, enabled by default @ acc creation
	- source — [[Elastic Compute Cloud|EC2]], [[CodeBuild]], [[Simple Storage Service|S3]], [[Trusted Advisor]], [[Atlas/AWS/CloudTrail]]
	- target — [[Lambda]], Batch, [[ECS]], [[SQS]], [[SNS]], [[Kinesis Data Streams]], Code*, [[Elastic Compute Cloud|EC2]], etc…
	- Rule — JSON doc created by EB that details events, it is sent 2 target RR (`target` is a property), filters based on event pattern define’d, bus-based ⇒ “En ESTE event bus, escuchá eventos que cumplan ESTE patrón, y cuando ocurra, mandalos a ESTOS targets”
		- type
			- schedule — cron job
			- event pattern — filtros
	- Schema Registry — creates event bus data interface 2 reference in code, schemas can b versioned
		- event schema — interfaz esperada en el bus del mensaje-evento
	- event bus — canal por el que circulan los mensajes-evento
		- types
			- default — AWS SS, se crea por defecto
			- partner — 4 3rd party SS, se crea al activar integración con said s
			- custom — se crea manualmente
		- policy — r-based, manage permissions on bus PER bus
			- x-acc access — allows RR from other acc 2 comm w EB (`allow`, `events:PutEvents`), other acc RR must have `event-rule.target=central-eb`.
	- Archive — copia filtrada de eventos almacenados internamente en EB, caso de uso: mayoritariamente debugging/testing, bus-related
	- Replay — se envían eventos de un archive al bus como si estuvieran pasando en tiempo real, caso de uso: debugging/testing