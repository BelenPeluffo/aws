---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: UDEMY
### Dudas
- [x] pregunta ✅ 2026-08-13
	- ¿Cómo se generan las git creds con IAM?
		Muy fácil. Seleccioná el IAM User y en la sección de creds de seguridad, elegí la opción *Generar HTTPS creds 4 Git*.
- [x] Diferencia entre usar IAM Roles o Acc keys + acc key ID ✅ 2026-08-13
	Ambos sirven para habilitar la interacción con ss de AWS.
	Las keys, específicamente, se usan a la hora de gestionar programáticamente la comunicación.
	Roles son una IAM ID con creds propias temporales. Las acc keys themselves son creds.
### Notas
- 
### Situación
A company would like to migrate the existing application code from a GitHub repository to AWS CodeCommit.

As an AWS Certified Developer Associate, which of the following would you recommend for migrating the cloned repository to [[Atlas/AWS/CodeCommit]] over HTTPS?

- A. Use Git credentials generated from [[Identity and Access Management|IAM]]
	Ésta es la correcta. Como CodeCommit 
- B. Use authentication offered by GitHub secure tokens
	- 
- C. Use IAM user secret access key and access key ID
	Ésto sólo se puede dar para que entidades tomen un rol. Éso no lo puede hacer Git.
	Se recomienda mejor asignar IAM Roles en vez de acc key y acc key ID que se usan con IAM Users y que se emplean de forma programática o a través de la CLI.
	Es PARA OTROS AWS S, no para Git.
- D. Use IAM Multi-Factor authentication
	Requiere, igual, que haya un medio de autenticación previo.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer