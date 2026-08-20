---
dudas: true
tags:
  - DVA02-30
aliases:
---
### Dudas
- [ ] dynamic refs -- ¿refiere a hacer referencia a valores dinámicos o a crear valores de forma dinámica en el template?
- [x] `Parameters` -- ¿entonces sólo pueden definirse dentro de las secciones de Resources o Outputs y no como una sección propia?
	Es una sección de nivel superior como `Resources` y `Outputs`. ^dbd5e6
- [ ] `Outputs`, `Rules`, `Conditions` -- is a stand-alone section or is it a subsection?
- [ ] `Mappings`, `Conditions` -- ?
- [ ] `Transform` -- ¿cómo está relacionado con [[Serverless App Model|SAM]]?
- [ ] no termino de entender cómo funcionan las funciones... ¿qué diferencia hay entre `Ref` y `!Ref` y `Fn::GetAttr` y `!GetAttr`?
### Notas

### Palabras clave
- elements
	- dynamic refs -- retrieves values during CxUD ^dinamic-refs
	- `Outputs.Secret.Value` -- prop en que se almacenan secrets
	- `Resources.Properties.GenerateSecretString` -- 2 dynamically create secret
- stack -- conjunto de rr definidos en un template
	- set -- conjunto de stacks, permite gestionar INSTANCIA de stack x-acc simultáneamente, ELIMINAR UN SET ELIMINA TODOS LOS RR CREADOS A PARTIR DE UN STACK AFECTADO POR LA ELIMINACIÓN ^88b804
	- policy -- json, podés agregarla desde la consola/CLI a new/existing stack, define qué acciones se pueden realizar sobre qué rr
	- template
		- sections
			- `Resources` -- req, ID & config details
				```yaml
				Resources
					NombreDelRecurso:
						Type: AWS::Servicio::TipoRecurso
						Properties:
							<varía según el Type>
				```
				- `DeletionPolicy` -- acá es donde se define la política a ejecutar para el RR específico ^53e920
					- valores
						- `Delete` -- por defecto
						- `Retain` -- para que no se elimine
						- `Snapshot` -- para hacer snapshot antes de eliminación
			- `Parameters` -- allows 4 flexibility (parametrization & reusability), user input @ CxUx, sección de nivel superior a la que se hace referencia por lo general dentro de `Resources` y `Outputs` ^10be7c
				```yaml
				Parameters:
					NombreParámetro:
						Type:
						AllowedPattern:
						AllowedValues:
						ConstraintDescription:
				```
				- `Type` -- req, `String | Number | List`
				- `AllowedPattern`
				- `AllowedValues`
				- `NoEcho` -- para que la data sensible se muestre como `****` ^22071e
			- `Outputs` -- returns x values related 2 stack
			- `Mappings` -- `Resources`/`Outputs`
			- `Metadata` -- additional data about template
			- `Rules` -- validates parameter values @ runtime before creating/updating resource
			- `Conditions`
			- `Transform` -- macros during template processing, related to [[Serverless App Model|SAM]]
		- functions
		- ``
- integrations
	- [[Secrets Manager]] -- thru dynamic refs points 2 values stored, `{{resolve:secretsmanager:<secret-id>:<secret-string>:<json-key>:<version-stage>:<version-id>`
	- [[SSM Parameter Store]] -- thru dynamic refs points 2 values stored, `{{resolve:ssm:<parameter-name>:<version>` 4 non-encrypt'd values, `{{resolve:ssm-secure:<parameter-name>:<version> 4 encrypt'd values
