---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: UDEMY
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A pharmaceutical company uses Amazon EC2 instances for application hosting and Amazon CloudFront for content delivery. A new research paper with critical findings has to be shared with a research team that is spread across the world.

Which of the following represents the most optimal solution to address this requirement without compromising the security of the content?

- a. Use [[CloudFront]] signed URL feature to control access to the file
	Éste es justo el uso de las signed URLs.
- b. Using CloudFront's Field-Level Encryption to help protect sensitive data
	The name of the feat says it all: encrypt'. We need acc, not encrypt'.
- c. Use CloudFront signed cookies feature to control access to the file
	U would use it if there were more than one file 2 b acc'd. In this case, 'cause it's just 1 u can do w signed URLs.
- d. Configure AWS Web Application Firewall ([[WAF]]) to monitor and control the HTTP and HTTPS requests that are forwarded to CloudFront
	Se usa en casos con un scope más grande de users. En este caso, como serán una docena como mucho de users scattered x-world no existe un criterio con que se pueda definir el WAF.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer
A