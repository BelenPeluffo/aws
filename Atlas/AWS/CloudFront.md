---
dudas:
tags:
  - DVA02-15
aliases:
---
### Dudas
- [x] Signed URLs — ¿pueden usarse para acceder a cualquier r o sólo a algunos? ¿Las URLs cambian todo el tiempo o una vez generadas se mantienen igual? ¿O “signed” significa que se le agrega un query param con la firma a la URL original? — ~~ver video~~ — ~~ampliar~~
    
    Se puede acceder a cualquier r servido por CF pero DEBE SER PRIVADO.
    
    Las URLs no cambian todo el tiempo aunque sean generadas dinámicamente, ya que la URL indica la dirección de acceso al r. Lo que cambia son los QP que se agregan a esa URL base.
    
- [x] Signed URL/Cookie — la policy ¿dónde se adjunta? ¿en la distribución de CF? ¿en el recurso que se está exponiendo? — ~~ampliar~~
    
    No se adjunta a ninguna parte. Son datos que se envían en las requests y van encriptados. CF se encarga de desencriptarlos usando las keys del TKG.
    
    Se definen en el cliente que hace la request y se usa la private key para firmarlo y en la policy se define el ID de la public key que debe buscar CF para verificar la firma.
    
- [x] CF 101 — ¿qué SS pueden asociarse a CF? — ~~ampliar~~
    
    Cualquier s/r que tenga un EP HTTP/S accesible por DNS. Pueden ser buckets, EC2, servers externos.
    
- [x] Trusted Key Group? CF Key Pair? — ~~ver video~~ — ~~ampliar~~
    
    TKG es la nueva forma de definir lo pairs.
    
    - ¿cómo es el proceso de crear el key group? ¿cómo creamos el key pair y cómo asignamos el private key al r determinado?
        
        El key pair lo creamos usando cualquier app que cree keys RSA 2048. Nos va a dar una public y otra private. La public es la que definimos en el TKG. La private la usamos en nuestro BE donde se define la policy que usará esa private key.
        
- [x] Caching & Caching Policies — ¿qué diferencia hay entre cache policy y origin policy y cómo trabajan juntas? — ~~ampliar~~
    
    La cache policy determina en definitiva si se va a servir lo cacheado o si se tiene que buscar en origen. Si ponemos como criterio un qp específico, por ejemplo, significa que la request con `?qp=a` y otra con `?qp=b` requieren cacheos distintos. Por lo tanto, si no hay nada cacheado para ninguna, ambas rq requieren buscar en origen.
    
    Lo que hay que tener en cuenta acá es lo que se denomina `hit ratio`. Ya con agregar un criterio a la policy de cache, se harán tantos rq como valores de ese criterio existan. Mientras más rq se necesiten, el `hit ratio` disminuye porque hay menos que se cachea. Lo ideal en lo posible es, ya que estamos usando CF, mantener el `hit ratio` lo más alto posible. Pero ésto dependerá de qué tanto dependa lo que sirve el origin de los criterios…
    
    La origin policy lo que hace es definir qué atributos de la rq queremos que llegen hacia origen cuando CF hace la consulta. Estos atributos el origin los necesita para construir la rta para el CF.
    
    El tema de qué se define en cache y qué en origen no es lineal, hay que evaluar según las necesidades de la arq e incluso así no hay una sola vía de implementación para “cada” caso, hay varias posibles que deben, nuevamente, decidirse según las necesidades.
### Notas
### Palabras clave
- concepto — Content Delivery Network (CDN), serves RR faster by caching content in EL, preferred when RR do not depend on data beeing freq updated, refreshes content based on TTL or invalidation
- Signed — se usa para brindar acceso a private RR
    - types
        - URLs — para acceder a contenido desde buckets conectados a CF, 4 access 2 INDIVIDUAL files, firma va en QP
        - Cookies — ídem URLs but 4 access 2 MULTIPLE files, firma va en cookies header
    - signers
        - Trusted Key Group — recommended, 1CF Disto → 1/M TKG, pair=private key + public key, public-k 4 CF and private-k 4 requesting r, cada public key dada de alta en CF tiene un ID que es al que se refiere en la policy del requesting r, debe asociarse el TKG a una distro particular
        - CF Key Pair — legacy, avoid
    - policy — se genera fuera de CF y se envía en cada request dirigida a CF
- origins — [[Simple Storage Service|S3]], [[VPC]], HTTP
    - públicos — S3, HTTP
    - privados — VPC origin sirve de acceso a A/NLB//[[Elastic Compute Cloud|EC2]] en VPC a CF público
- cache key — ID of object, key=hostname+r path in URL
- cache policies — user can define M policies specific 2 x needs
    - CF Cache Policy — config how 2 create keys, criteria on si hit (use cache)/miss (rq origin): headers/cookies/qp,
    - CF Origin Request Policy — criteria: same as cache policy, qué datos se ff al origen desde CF para calcular rta pertinente
- Geo Restriction — based on country
- Origin Access Control — need 2 set r 2 b requested only by CF
- Invalidation — updates served version with source version, target: all files/x path
- protocol policies
	- viewer -- client, can define secure via HTTPS
	- origin -- server, ídem
- Integration
	- [[Certificate Manager|ACM]] -- acepta certificados en `us-east-1` por el momento