---
dudas:
tags:
aliases:
  - SQS
---
### Dudas
- [x]  ✅ 2026-08-05
### Notas
### Palabras clave
- q -- can b encrypt'd via [[Key Management Service|KMS]]
	- tags -- case-sensitive
- polling
	- long -- espera 20s para hasta obtener alguna rta
	- short -- no espera => si no hay rta igual retorna éso
- sms batching -- permite acumular hasta 10 sms para gestionarlos juntos
- types -- can't change it after creation
	- standard
	- FIFO
- APIs
	- `CreateQueue`
	- `Attributes.DelaySeconds` -- delay delivery, se puede definir al ejecutar `CreateQueue`
	- `Attributes.MessageRetentionPeriod` -- determinar cuánto tiempo vive un sms en una q sin ser eliminado, se puede definir al ejecutar `CreateQueue`
	- `DeleteQueue` -- delete q n contents
	- `PurgeQueue` -- delete sms leave q
	- `RemovePermission` -- remove q permissions related 2 specified label