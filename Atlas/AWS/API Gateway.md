---
dudas: true
tags:
  - DVA02-23
aliases:
  - API-GW
---
### Dudas
- [ ] ¿Dónde se activa el CORS?
- [ ] CW Logs — ¿hay que activarlo o está activado por defecto? — ampliar
- [ ] Investigar un poco más sobre los integrations. Repasar video.
- [ ] ¿qué es un resource? ¿diferencia con method?
- [ ] listado de stage variables
- [ ] ¿las stage variables sólo funcionan con Lambda?
- [ ] ¿qué diferencia hay entre method request e integration request?
- [ ] Si el tiempo de ejecución máximo de API-GW es de 19s, ¿qué pasa con la integración con Lambda, que tiene como máximo un tiempo de ejecución de 15m? ¿API-GW dará error? ¿cómo se gestiona éso?
- [ ] cuando se trata de gestionar x-acc acc, ¿se debe usar siempre r-based policies además de IAM roles?
- [ ] ¿authorizers son a nivel de acc, de API o de método? ¿ídem La autenticación con IAM y r policies?
### Notas
- Para que los cambios se efectivicen, se deben DEPLOYAR, no sólo guardar.
- El máximo que puede estar con una rq es 29s.
### Palabras clave
- raison d’être — API REST, dar acceso a RR pero sin exponerlos, auth
- elementos
    - EP types
        - Edge-Optimized — uses [[Atlas/AWS/CloudFront]] infra 2 provide access from all over the world, default, API-GW still in one R
        - Regional — can b integrated w CFront 2 control access
        - Private — only accessed from VPC via VPC EP
	        - VCP EP -- para garantizar acceso privado a los RR de una [[private subnet]] ^2e0841
    - stages — own config = stage vars (access’d via `${stageVariables.nombreDeVariable}`, versioning, canary deploy available
	    - `stageVariables.lambdaAlias` -- se usa al definir el nombre de la Lambda y esta variable sirve de token que luego se deberá definir en las env vars de cada entorno
    - usage plan — ==limit enforcement==, limitar # rq que un cliente puede hacer en un período x de T, who, how much, how fast, id API key, throtling, quota, set up? 1. create key → 2. config method 2 use key → 3. deploy key in stage → 4. create plan → 5. assoc stage & key 2 plan #test-question 
	    - rate limit -- rq/s
		- quota -- rq/T period
    - API key — ==acc control==, unique ID 4 clients 2 auth when acc API, permite monitor&track client usage, key 2 access securely, throtling is @ key-level, client must send in `x-api-key` header #test-question 
- security
    - authentic’ — [[Identity and Access Management|IAM]] Roles, [[Amazon Cognito]], Custom Authorizer
    - CORS -- permite acc desde múltiples orígenes
- rq validation — uses Open API spec, `x-amazon-apigateway-request-validators`=json, bouncer 4 BE, verifies structure of rq & determines whether 2 send it or nah
- cache — TTL: 0m - 5m (default) - 1h, 1 stage → 1 cache, encryptable, overridable by stage, size: 0.5gb-237gb, $ $ $ $, can b invalidated via GUI or client headers, via headers ? implement IAM Policy : any user can invalidate it
- integraciones
    - types
        - MOCK — mock responses, no rq 2 BE #test-question  ^144d15
        - HTTP/AWS — must config integ rq & integ rta, mapping templates 2 structure data as needed before sending 2 client/BE, desacopla lógica de mapeo del BE, 2 implement mapping logic uses VTL (velocity template language), can filter output results, rq must be `ContentType IN (application/json, application/xml)`, use case: REST API (json) → SOAP API (xml)
        - AWS_PROXY (aka Lambda proxy) — client rq goes 2 lambda, NO modif of rq and rta, es pasamanos
        - HTTP_PROXY — can only add headers 2 sms sent 2 BE ^1e86da
    - servicios
        - targets
            - [[Lambda]] — stage vars passed through context obj, flow: API-GW → alias → function
            - [[Step Functions]]
            - [[KDS]]
            - [[SQS]]
            - EP del BE
        - [[CloudWatch]]
            - Logs — info abt rq/rta, can be enable’d @ stage-level
            - [[CW Metrics]] — logs x2, can enable detail metrics
                - `CacheHitCount` — success
                - `CacheMissCount` — error
                - `Count` — # API calls ^0b349c
                - `IntegrationLatency` — tiempo entre que API-GW envía rq a BE y recibe la rta de éste ^2a7236
                - `Latency` — tiempo entre que cliente envía rq y recibe rta ^54c760
                - `4XXError` — # errores cliente
                    - 429 — throttling
                - `5XXError` — # errores BE
        - [[Atlas/AWS/X-Ray]]
### Errors

| error code             | error description            | cause                                                       |
| ---------------------- | ---------------------------- | ----------------------------------------------------------- |
| [[Atlas/IoT/400\|400]] | bad rq                       |                                                             |
| [[Atlas/IoT/403\|403]] | access denied                | [[Atlas/AWS/Web Application Firewall\|WAF]] filtered        |
| [[Atlas/IoT/429\|429]] | quota exceeded<br>throttling |                                                             |
| [[Atlas/IoT/502\|502]] | bad gw                       | - incompatible OUT from lambda BE<br>- out-of-order invokes |
| [[Atlas/IoT/503\|503]] | s unavailable                |                                                             |
| [[Atlas/IoT/504\|504]] | integ fail                   | - EP req timeout (29s exceeded)                             |
### CORS
API-GW supports [[Atlas/IoT/Cross Origin Request Sharing|CORS]]. Must b enabled manually 2 receive API calls. 