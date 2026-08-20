---
dudas:
tags:
  - DVA02-30
  - DVA02-20
aliases:
  - CW Logs
---
### Dudas
- [x] CW Logs — ¿qué es log retention policy? — ver video — ampliar
	Es la regla que define cuánto tiempo se almacenan esos datos. Se define a nivel de log group, es decir: se define cuando creás o editás un log group.
### Notas
### Palabras clave
- concept — by default logs never expire, log group > log stream, logs encrypted by default, can use KMS
	- targets — [[Simple Storage Service|S3]] (via batch), KDS (via subscription), [[Kinesis Data Streams|KDS]] (via subscription), [[Lambda]] (via subscription), [[OpenSearch]]
	- sources — SDK, [[CloudWatch Agent|CW Agent]], [[Elastic Beanstalk]], [[ECS]], Lambda, [[VPC Flow logs]], [[API Gateway]], [[CloudTrail]] filters, [[Atlas/AWS/Route 53]] DNS qs
	- cross-acc subscription — receives logs from other acc via sub destination, must create destination access policy 2 allow receiving data from origin
	- Insights — 2 q historical logs, can save q & show in CW Dashboard ^3de2c6
	- Metrics Filter — filter logs via keywords, not retroactive, up 2 3Ds, can b used 2 trigger alarms
	- Log Retention Policy — storage T, defined at log group-level, default: never expire
	- Custom Metrics
		- Metric Resolution — `StorageResolution`
			- Standard — 1m
			- High Resolution — hasta 1-sec metrics, use case: apps con necesidades real-time, related alarms can only b triggered every 10s minimum, $ $ $
		- `CLI.PutMetricData` — push custom metric data
- integration
	- [[Key Management Service|KMS]] -- encrypt' w/ kms keys @ log group-level => key assigned 2 log group, ==only via CW Logs API (NOT via UI)==, needs key policy 2 work ([[Key Management Service#^no-policy-no-access|no-policy-no-access]])
		- `associate-kms-key` 4 E log group
		- `create-log-group` 4 log group create' & key assignment