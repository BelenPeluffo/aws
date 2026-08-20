---
dudas: true
tags:
aliases:
incorrecta: true
---
Pregunta: UDEMY
### Dudas
- [ ] Pregunta
	- ¿Todos los atributos de la EC2 pueden cambiarse a través de la CLI y surtir efecto sin apagar y reiniciar la instancia?
### Notas
- 
### Situación
A development team has noticed that one of the [[Elastic Compute Cloud|EC2]] instances has been wrongly configured with the 'DeleteOnTermination' attribute set to True for its root EBS volume.

As a developer associate, can you suggest a way to disable this flag while the instance is still running?

- A. Set the `DisableApiTermination` attribute of the instance using the API
	Ésta propiedad determina si se puede o no terminar una instancia usando CLI, API o consola.
- B. Update the attribute using AWS management console. Select the EC2 instance and then uncheck the Delete On Termination check box for the root EBS volume
	Ésto sólo lo podés hacer cuando estás CREANDO la instancia.
- C. The attribute cannot be updated when the instance is running. Stop the instance from Amazon EC2 console and then update the flag
	- 
- D. Set the `DeleteOnTermination` attribute to False using the command line
	This is a thing!
### Condiciones
- 

### OPTS
a.

### Análisis
C
> [!note] Mi respuesta
> 
### Answer
D