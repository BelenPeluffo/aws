---
dudas: true
tags:
  - DVA02-28
aliases:
  - SFN
  - SFx
---
### Dudas
- [x] cuando hablamos de `Max Duration` y que las SFx standard puede ser de hasta un año, ¿a qué nos referimos? ¿que la task puede estar ejecutándose durante 1 año seguido?
	Una task se considera "viva" si está `RUNNING` o `WAITING`. Y, sí, puede estar en estos estados como máximo un año.
- [ ] ¿se le dice "low-code" visual workflow service porque se define mediante templates .yml?
### Notas
### Palabras clave
- concepto -- para definir workflow
	- workflow aka state machine -- proceso que se compone de varios pasos, `.json`
- task -- un step
	- `Activity` -- permite que un Activity Worker ([[Elastic Compute Cloud|EC2]]) haga POLL a SFx para ejecutar alguna task
		- `GetActivityTask` -- API donde rta de SFx viene con input y `TaskToken`
		- `SendTaskSuccess`
		- `SendTaskFailure`
		- `SendTaskHeartBeat` -- API para avisar a SFx que la Task está en proceso
- states
	- `CHOICE`
	- `FAIL`
	- `SUCCEED`
	- `PASS`
	- `WAIT`
	- `PARALLEL`
- error handling -- should b in SFx y no en [[Lambda]] so as 2 make the app simpler => no need 2 deploy if handling varies, evaluated TOP->BOTTOM
	- types
		- Retry -- retry task, `fx.Retry` = array de objetos en que se definen el tipo de error & max attemp y otras cosas
			- `Retry.ErrorEquals`
			- `Retry.MaxAttempts`
		- Catch -- transition 2 failure path, if retries are run out fx enters into this path
			- `Catch.ErrorEquals`
			- `Catch.Next` -- qué ejecutar según el error
			- `Catch.ResultPath` -- input sent 2 fx in `Next`
				- `$.error` -- agregar objeto `error` en caso de error al output de la fx para el `Next`
	- error codes
		- `States.ALL`
		- `States.Timeout`
		- `States.TaskFailed`
		- `State.Permissions`
- `arn:aws:....waitForTaskToken` -- 2 machine warte @ ein Task, caso de uso: when relying on external SS ([[SQS]])
	- sending -- `Parameters.MessageBody.TaskToken.$`
	- receiving -- output.`taskToken`
- workflows
	- standard -- default, alive 4 up 2 1 yr, pay 4 # state transition, non-[[idempotent]], exactly-once exec
	- express -- alive 4 up 2 5m, pay 4 # exec', [[idempotent]]
		- async -- at-least once exec, se ejecuta y no espera rta 'cause doesn't need it, para ver resultados hay que usar [[CloudWatch Logs|CW Logs]]
		- sync -- at-most once exec
