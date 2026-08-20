---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: 
### Dudas
- [ ] Open Telemetry -- ??
- [x] X-Ray -- Auto-instrumentation agent -- ? ✅ 2026-08-06
	Agente que facilita la integración de X-Ray en el código con tweaks manuales mínimos. Pero, como tal, no permite un control granular.
### Notas
- 
### Situación
A developer is incorporating AWS [[X-Ray]] into an application that handles personal identifiable information (PII). The application is hosted on Amazon [[Elastic Compute Cloud|EC2]] instances. The application trace messages include encrypted PII and go to Amazon [[CloudWatch]]. The developer needs to ensure that no PII goes outside of the EC2 instances.  
Which solution will meet these requirements?

- A. Manually instrument the X-Ray SDK in the application code. ^63bb76
	Si no lo instrumentás en el código, no tenés forma de enviar los traces.
- B. Use the X-Ray auto-instrumentation agent. -- ??
	Éste no se podría porque no nos permite un control granular de los datos que se envían en los traces; y es justamente éso lo que necesitamos para 
- C. Use Amazon [[Macie]] to detect and hide PII. Call the X-Ray API from AWS [[Lambda]]. 
	-- Macie es para éso? [[Amazon Macie|Sí]].
- D. Use AWS Distro for Open Telemetry. -- ?
### Condiciones
- 

### OPTS
a.

### Análisis
Interpreto que será la opción de Macie, pero realmente no tengo ni idea.
> [!note] Mi respuesta
> 
### Answer
[[Hiding PII#^63bb76|A]]. Macie en este caso no corresponde porque en la descripción de la situación se define que los datos están en el EC2 y no se nombra ningún bucket de S3. Macie sólo trabaja detectando sobre S3.