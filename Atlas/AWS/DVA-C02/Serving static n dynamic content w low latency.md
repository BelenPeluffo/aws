---
dudas: true
tags:
aliases:
incorrecta: true
---
Pregunta: UDEMY
### Dudas
- [ ] CF -- features!!! -- origin groups??
### Notas
- 
### Situación
A website serves static content from an Amazon Simple Storage Service (Amazon [[Simple Storage Service|S3]]) bucket and dynamic content from an application load balancer. The user base is spread across the world and latency should be minimized for a better user experience.

Which technology/service can help access the static and dynamic content while keeping the data latency low?

- A. Configure [[CloudFront]] with multiple origins to serve both static and dynamic content at low latency to global users
	Keywords: static content from S3 & dynamic content from ALB.
	Éso es exactamente lo que hace lo de multiple origins.
- B. Use Global Accelerator to transparently switch between S3 bucket and load balancer for different data needs
- C. Use CloudFront's Lambda@Edge feature to server data from S3 buckets and load balancer programmatically on-the-fly
- D. Use CloudFront's Origin Groups to group both static and dynamic requests into one request for further processing
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer