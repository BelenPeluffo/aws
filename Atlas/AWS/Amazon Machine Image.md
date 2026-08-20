---
dudas:
tags:
  - DVA02-6
  - ec2
aliases:
  - AMI
---
### Dudas
- [x] ¿cómo se encriptan?
	No es más que habilitar la opción de encriptado a la hora de crear la imagen.
- [x] ¿cómo se copian de una región a otra?
	Una acción en la UI.
### Notas
- Se pueden copiar AMIs que no están encriptadas y encriptarlas en el proceso de copia.
### Palabras clave
- concept -- custom' of [[Elastic Compute Cloud|EC2]], allows 4 faster boot&config T
- props
	- R-scoped, copiable 2 other RR
	- EC2 is always launched from an AMI
		- public -- AWS-managed & mantained
		- own -- managed & mantained by usr
		- marketplace -- someone else's AMI
	- creation process -- 1. customize EC2, 2. create image from it
	- encrypt' can only b defined @ creation time ^7a3967