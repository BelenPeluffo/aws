---
dudas:
tags:
aliases:
incorrecta:
---
Pregunta: https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/#:~:text=34-,Question%20%236,-Topic%201
### Dudas
- [x] ¿Cuál es el uso de cada una de las propiedades de un template?
- [x] `Parameters.AllowedValues` -- ¿ésto iría definido dentro del `Resources` que defina el [[Elastic Compute Cloud|EC2]]?
	Sí. Quedaría algo como:
	```yaml
	Parameters:
	  InstanceType:
	    Type: String
	    Description: Tipo de instancia EC2
	    AllowedValues:
	      - t2.micro
	      - t3.micro
	      - t3.small
	      - m5.large
	    Default: t2.micro
	Resources:
		MiInstanciaEC2Dinamica:
			Type: AWS::EC2::Instance
			Properties:
				InstanceType: !Ref InstanceType
	```
- [x] Resource/Parameter por type -- ¿hacer ésto no generaría que se instancien tantas instancias como types definidos a la hora de deployar el stack?
	Correcto.
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
Must create a [[CloudFormation]] template for creation of [[Elastic Compute Cloud|EC2]]. The instances must b of certain types.
### Condiciones
¿Cómo definir en el template los types que puede tomar?

### OPTS
a. Un template por type -- no. La idea de CForm es parametrizar y reutilizar. Ésto va en contra.

b. Un resource por type -- se podría, pero hay que definirlos manualmente, por lo que son ESTÁTICOS y no dinámicos => no es escalable.

c. Un parameter por type -- se usan como input, no definen una lista específica de valores; éso lo hace [[EC2 instance def w CloudFormation#^b1b7fa|d]].

d. Ingresar array de types en `Parameters.AllowedValues` ^b1b7fa

### Análisis

> [!note] Mi respuesta
> Me parece que es [[EC2 instance def w CloudFormation#^b1b7fa|D]]. ~~Porque un resource me da la sensación de que terminaría creando una instancia por cada type definido; es decir que si son 6 los types definidos, al deployar un solo template se deployarían 6 instancias~~. Y con respecto a parameter, no me parece, pero no puedo justificar. El de un template por type me parece que no es escalable.
### Answer
D.