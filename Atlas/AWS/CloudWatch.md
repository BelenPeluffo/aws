---
dudas:
tags:
  - DVA02-20
aliases:
  - CW
---
### Dudas
- [x] CW — ¿qué servicios pueden ser source? ¿todos los servicios? — ~~ampliar~~
    
    Muchos. Hay algunos que requieren más configuración que otros.
    
- [x] CW vs. X-R — ¿qué diferencia hay en cuanto al SCOPE de ambos servicios? — ~~ampliar~~
    
    El scope en realidad tiene que ver con la finalidad de cada servicio.
    
    CloudWatch tiene la finalidad de monitorear. Por éso se concentra en métricas y en los niveles más macro. Lograr que detalle más requiere más configuración, if any.
    
    [[X-Ray]] tiene la finalidad de tracing. Se concentra en los traces y detalla a niveles más micro. Además, usa IA para investigar los causantes. Funciona así sin ninguna configuración más que la indicación del stack.
### Notas
### Palabras clave
- concept — monitors performance & RR use & ops health
	- EC2 Detailed Monitoring — pay’d feat, 1-min metrics
- [[CloudWatch Logs|CW Logs]]
- [[CloudWatch Alarms|CW Alarms]]
- [[EventBridge]]

