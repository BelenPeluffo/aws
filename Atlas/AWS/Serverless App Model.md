---
dudas: false
tags:
  - DVA02-25
  - serverless
aliases:
  - SAM
---
### Dudas
- [x] `sam local start-lambda` -- necesito entender un poco más cómo funciona ésto
	Habilita un servidor local al que pueden hacerse rqs.
	¿O sea que disponibiliza todas las lambdas que estén definidas en el proyecto desde el que se ejecuta el comando?
	Sí.
	¿Se ejecuta todo sin hacer requests a la nube de AWS?
	Sí. Son ejecutables en local todas las lambdas definidas en `template.yaml`
- [x] `sam local invoke --profile` -- ¿qué diferencia tiene con `start-lambda`?
	Simplemente ejecuta la función indicada en local, nada más. O sea: lo usarías en local para probar que la función funcione correctamente.
	Para invocar las remotas, deberías usar el [[Atlas/AWS/CLI]]: `aws lambda invoke ...`
### Notas
### Palabras clave
- concepto -- framework 4 dev & deploy of serverless apps, shortcut to using [[CloudFormation]], creás templates, use case: run SS locally 4 testing & dev
- integraciones -- SS que puede gestionar por el momento
	- resource types
		- `AWS::Serverless::Function` -- [[Lambda]]
		- `AWS:Serverless::Api` -- [[API Gateway|API-GW]]
		- `AWS:Serverless::SimpleTable` -- [[Atlas/AWS/DynamoDB]]
	- [[CloudFormation]] rr
		- `AWS::S3::Bucket` -- [[Simple Storage Service|S3]]
		- `AWS::SNS::Topic` -- [[SNS]]
		- `AWS::SQS::Queue` -- [[SQS]]
		- `AWS::StepFunction::StateMachine` -- [[Atlas/AWS/Step Functions]]
- steps
		1. creás template SAM -- manual o a través de `sam init`
		2. `sam build` -- SAM template -> CloudForm template
		3. `sam deploy` ó `sam deploy --guided`
			- steps
				1. zip & upload template + app 2 [[Simple Storage Service|S3]]
				2. create CForm stack based on template
			- `sam deploy --config-env <entorno-x>` -- deployar en entorno definido en `samconfig.toml`
- SAM Accelerate
	- `sam sync` -- actualiza infra & code
	- `sam sync --code` -- just code
	- `sam sync --code --resource <r>` -- x recurso
	- `sam sync --watch` -- cualquier cambio realizado se deploya de inmediato
- local
	- `sam local start-lambda` -- habilita EP contra el que testear como si fuera la [[Lambda]], queda activo y podés hacer cuantas llamadas quieras
	- `sam local invoke --profile` -- ejecuta lambda con un payload mockeado, al terminar la ejecución -> exits
	- `sam local start-api` -- habilita HTTP server que hostea todas las fx
	- `sam local generate-event` -- event 4 [[Lambda]]
- policy templates
- multiple-envs -- `samconfig.toml`, definición de envs
- BTS SS
	- [[Atlas/AWS/CodeDeploy]] -- 2 deploy [[Lambda]], [[traffic shifting]] para pasar de una ver a la nueva