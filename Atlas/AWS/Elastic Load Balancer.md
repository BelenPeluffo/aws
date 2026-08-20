---
dudas: true
tags:
  - DVA02-7
aliases:
  - ELB
  - ALB
  - CLB
  - NLB
---
### Dudas
- [ ] ELB Sticky Sessions — ~~Ver video~~ — Ampliar
    
- [x] ALB routing criteria — ~~Ver video~~
    
    - URL path — literalmente según algún parámetro del path, se redirige a un TG o a otro
    - URL hostname — según el dominio
    - URL query params
    - Request headers
- [x] ELB Routing criteria — ¿sólo disponible para ALBs o para cualquier ELB que no sea el CLB? — ~~Ampliar~~
    
    Es probable que no, que sólo esté disponible para los ALB ya que están relacionados a apps y no a RR en sí.
    
    Cuando digo “routing criteria” en realidad me estoy refiriendo al criteria que vimos en relación a elementos de la URL. Ese routing criteria en específico, sí, sólo es posible con ALB.
    
    NLB y CLB no manejan routing por elementos de la URL.
    
- [x] ELB Health Check — ~~Ampliar~~
    
    - ¿qué significa que se hagan a nivel de TG? ¿qué pasa si uno de los servicios del TG no responde pero los otros sí: redirige a otro TG? ¿sólo para los ALB? — ~~Ampliar~~
        
        Significa que se configura a nivel de TG (o sea que podemos tener TGs todos con configuraciones diferentes; ésto da más granularidad porque nos permite que sea específico según los targets que lo componen). Pero los health checks son por r.
        
        El ELB apunta, según la routing criteria, a un TG en particular y dentro de esos TGs se cerciora de sólo enviar a los RR sanos.
        
        No funciona así sólo con ALB, también con NLB.
        
        En el caso del CLB, el check es a nivel del LB. Ésto quiere decir que se define la configuración de health en el LB y por lo tanto es un sólo criterio de health para todos los RR.
        
    - ¿qué implica que soporten ciertos protocolos? ¿ésto es así para todos los ELB o sólo para NLB? — ~~Ampliar~~
        
        Significa que los health checks sólo se ejecutan usando ciertos protocolos: TCP y HTTP/S. Ésto es así para todos los ELB en el sentido de que todos usan alguno o todos estos protocolos:
        
        - NLB usa todos
        - ALB sólo usa HTTP/S
        
        A su vez, dependiendo del protocolo se define la profundidad del análisis:
        
        - TCP — funciona?
        - HTTP/S — no sólo si funciona sino también si funciona bien
- [x] NLB IPs — ¿qué onda éso de las IPs estáticas y elásticas? — ~~Ampliar~~
    
    Una IP estática es una que no cambia. La elástica, sí.
    
    En el caso de los NLBs, como se manejan en la capa de red es más común que requieran usar IPs estáticas.
    
- [x] ALB app-based cookies? — ~~Ver video~~
    
    Se refiere a las cookies que se crean para el Sticky Session para mantener la user data cuando el LB tiene que decidir hacia dónde redirigir a un cliente.
    
    Las app-based cookies son cookies que se crean en la aplicación, en contraste a las que crea por defecto el LB.
    
- [x] ELB Cross-Zone Load Balancing — ¿que hace exactamente? ¿en vez de distribuir evently entre AZs lo hace estando consciente de las instancias en particular? — ~~Ver video~~ — ~~Ampliar~~
    
    - ¿ésto significa que los ELB están definidos a nivel de AZ y por éso se puede dar el caso de que tengas que tener en cuenta la cantidad de instancias?
        
        Es un punto intermedio. El r ELB está definido a nivel de R PERO al configurarlo tenés que seleccionar en qué AZ va a operar. En las AZ que opere, se crea un nodo de ELB al que el ELB regional direccionará el tráfico.
        
        Justamente como el ELB está definido a nivel R es que es posible el Cross-Zone Load Balancing, ya que tiene “consciencia” de la cantidad de RR totales que gestiona cada uno de sus nodos.
        
- [x] ELB Server Name Indication — ¿sólo sirve para los ALB o para cualquier ELB? — ~~Ver video~~
    
    Sólo para ALB y NLB.
    
- [x] ELB Status Check vs Health Checks — ~~Ampliar~~
    
    Creo que acá se me mezclaron un par de cosas.
    
    El uso de ambos checks lo hace ASG para determinar qué instancias reemplazar.
    
    El Status Check es un check que sucede a nivel de EC2 (check de infra). El Health Check se define a nivel de Target Group y lo ejecuta el LB en cada recurso en particular (check de app).
    
    - ¿los targets pueden ser cualquier servicio de AWS? ¿el health check se ejecuta indistintamente del tipo de servicio?
### Notas
- Escalado
    - vertical — + capacidad
    - horizontal — + cantidad
### Palabras clave
- concepto — static DNS name/fixed hostname (single point of access), managed but lowly tweakable, some can be set to private/public
- Target Groups — lista de grupo de RR x y config relacionadas
	- config
		- los RR afectados
		- cada cuánto y cómo hacer health check
		- listener (nodo de LB en AZ) al que está asociado — ésto le traspasa las config de health check al LB para ejecutar health checks
- types
	- Classic (CLB) — layers 4 & 7, http/https/tcp/ssl, for apps migrating from older setups, 1 LB → 1 app, 1 LB → 1 SSL cert, NOT RECOMMENDED BY AWS
		- Cross-Zone Load Balancing — disabled by default, BUT NO charge 4 data moved between AZs
	- Application (ALB) — layer 7, http/https/websocket, returns own IP by default, 1 LB → M Target Group (apps), redirects to TG based on criteria
		- routing criteria — URL hotsname, URL query params, headers, URL path
		- Target Groups — EC2, private IP, lambda f(x), [[Elastic Container Service|ECS]] tasks
		- app’s client IP data access — `X-Forwarded-For` (IP), `X-Forwarded-Port` (port), `X-Forwarded-Proto` (protocol)
		- Cross-Zone Load Balancing — enabled by default ⇒ no charge 4 data moved between AZs, can disable by TG
		- Server Name Indication — 1 LB → M SSL certs by using it, used by default
		- user case: micro-S/container apps
	- Network (NLB) — layer 4, ultra high perfo, tcp/udp, static IP
		- routing criteria — IP + puerto
		- Target Groups — EC2, private IP, ALB (use case: static IP del NLB + routing del ALB)
		- Cross-Zone Load Balancing — disabled by default ⇒ data moved between AZs IS CHARGED
		- Server Name Indication — 1 LB → M SSL certs by using it
		- user case: static IP, high performance
	- Gateway (GWLB) — layer 3, IP (including GENEVE 6081), TG determine whether or not traffic should reach apps
		- Target Groups — security appliances accessed via: EC2, private IP
		- Cross-Zone Load Balancing — disabled by default ⇒ data moved between AZs IS CHARGED
		- use case: analyse network traffic before it reaches the app
- Sticky Session — redirect user 2 same instance, objective: not 2 lose session data, cookie-based ^e97dfe
	
	- cookie names — depends on creator
		- LB-generated — AWSALB, AWSELB, AWSALBAPP, AWSALBTG
		- app-generated — custom, el LB es capaz de leerlas
- Health Checks — redirects only 2 healthy instances, terminates unhealthy instances & launches a new one
	
- Server Name Indication — concept: propiedad del objeto ClientHello en que el cliente envía server name al listener para que éste sepa qué cert usar al conectarlo ⇒ 1 listener → M SSL certs ⇒ 1 listener → M client apps que necesitan ≠ SSL certs, sólo para ALB y NLB
	
	La definición del listado de certificados disponibles se realiza en la configuración del ELB. Es una lista de ARNs que refieren al listado original en AWS Certificate Manager.
	
- Connection Draining/De-registration Delay — período de tiempo disponible en una EC2 en estado `draining` para que se terminen de completar las requests recibidas y luego darse de baja (por estarse dando de baja por el user o por unhealthy)
	
- Cross-Zone Load Balancing — ELBs son r REGIONAL pero en config tiene configuradas ciertas AZ, por éso es posible esta funcionalidad, porque el ELB padre tiene “consciencia” de todos los RR que gestiona cada nodo ELB de AZ