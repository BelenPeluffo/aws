---
dudas: true
tags:
  - cache
  - in-memory
  - DVA02-8
aliases:
---
### Dudas
- cluster-mode??
### Notas
### Palabras clave
- concepto -- [[cache]] para reducir rqs a DB al almacenar en memoria queries repetidas
- props
	- managed
	- mAZ -- set at creation
	- in premises | cloud
	- caching strategies -- considerations: [[eventually consistent]] ok? & cache is needed? & data str is proper? & best design pattern?
		- lazy loading / cache-aside / lazy-populat' -- cached: only rq'd data, cache miss? -> 1. rq cache (the miss) -> 2. rq db -> 3. rq cache 2 store => latency, potential stale data, recomm: most recommended
		- write through -- cached: when app writes db -> writes cache as well => a lot of data in cache, recomm: mostly used alongside lazy loading ^write-thru
	- cache evictions
		- methods
			- manual
			- least recently used (LRU)
			- ttl -- setting 4 auto delet', recomm: not used w/ [[ElastiCache#^write-thru|write through]]
		- scaling -- si no queda espacio -> data auto-evict'd, solución? scale up/out 4 + space, acá viene handy el Redis Cluster que es quien permite el scale-out
	- cluster-mode ? 15 read-replicas : 3 read-replicas