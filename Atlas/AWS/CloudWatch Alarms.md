---
dudas:
tags:
aliases:
  - CW Alarms
---
### Dudas
- [x]  ✅ 2026-08-05
### Notas
### Palabras clave
- concept — mostly based on CW metrics (in opposition 2 QUERIES), their states triggers actions/notifs 4 any metric
	- targets — [[Elastic Compute Cloud|EC2]], EC2 autoscaling, [[SNS]]
	- High Resolution — related 2 high resolution metrics, can b set 2 b triggered every 10/30s or multiples of 60s
	- Composite Alarms — CW Alarm → monitos 1 metric (filter’d 2) & CW Composite Alarm → monitors state of M alarms ⇒ M metrics, && ||,
	- `CLI.set-alarm-state` — test alarm kostenloss
