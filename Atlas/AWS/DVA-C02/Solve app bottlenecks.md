---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: UDEMY
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A company's e-commerce application becomes slow when traffic spikes. The application has a three-tier architecture (web, application and database tier) that uses synchronous transactions. The development team at the company has identified certain bottlenecks in the application tier and it is looking for a long term solution to improve the application's performance.

As a developer associate, which of the following solutions would you suggest to meet the required application response times while accounting for any traffic spikes?

- A. Leverage horizontal scaling for the application's persistence layer by adding Oracle RAC on AWS
	Según la concepción que expliqué en B, ésta era mi opción original pero con el tema del Oracle RAC me quedé como ??? No es por acá porque wtf por qué sería tan específico de usar un Oracle??
- B. Leverage SQS with asynchronous AWS Lambda calls to decouple the application and data tiers
	Yo elegí ésta porque entendí como que estaba tardando mucho el flujo app -> DB y que éso estaba ralentizando todo el sistema. En base a esa concepción, me parecía que esta opción era la más cercana a una solución.
	Pero está mal porque como la consigna decía SYNCHRONOUS sí o sí éso debía mantenerse.
- C. Leverage horizontal scaling for the web and application tiers by using Auto Scaling groups and Application Load Balancer
	Ésta es la correcta.
- D. Leverage vertical scaling for the application instance by provisioning a larger Amazon EC2 instance size
	Entiendo que vertical scaling nunca es la solución.
### Condiciones
- 

### OPTS
a.

### Análisis
B
> [!note] Mi respuesta
> 
### Answer
C