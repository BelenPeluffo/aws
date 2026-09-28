---
dudas: true
tags:
aliases:
  - WAFrame
---
### Dudas
- [ ] [[runbook]]s??
- [ ] [[playbook]]s??
### Notas
### Palabras clave
- concept -- tools 2 evaluate & improve sys based on BPs
- pillars -- la APLICACIÓN del criterio del general principle -- CoRSOPS
	- ==ops excellence== -- **hacerlo bien, monitorearlo y mejorarlo** -- automatización y monitoreo y mejora de procesos -- what u doing? IMPLEMENT BPs -- what 4? reliable, efficient, cost-effective envs
		- design principles
			- teams org' = f(business outcome) -- base ur sys model 2 support the client's goals n' priorities
			- observe 2 take action -- use the Key Performance Indicators (KPIs) 2 understand what can b perfected
			- automate, w caution -- cloud workload AS CODE
			- frequent, small, reversible changes
			- better ur procedures frequently
			- anticipate failure
			- learn from all op events
			- manag'd ss, gurl
		- BPs -- OPOE
			- organice -- ops = f(gov&compliance reqs)
				- org priorities -- make sure 1. u know org's goals n 2. ops are aligned 2 that
				- op model -- make sure 2 know WHO owns WHAT, those people will help u w definition
				- org culture -- make ur team involved in this
			- prepare -- understand WL and expected behaviors and monitor them
				- observability -- monitor, bitch
				- implement Ps that allow 4
					- fast releases n testing
					- ~version control of arch
				- what is READY in ur arch? -- make a checklist 4 evaluating when ur sys ir ready n' can b deployed. Interesante: [[runbook]]s 4 routines, [[playbook]]s 4 issue handling
			- operate -- achievement of business outcome = SUCCESS
				- observe, analyze n' implement betterment -- set BASELINES n' THRESHOLDS that will help u determine when something's not working according 2 plan
				- what is HEALTHY? -- que las métricas definidas lo estén en base en OUTCOMES para que sus datos sean más valiosos
				- respond 2 events -- creá tus [[playbook]] y [[runbook]] para rtas consistentes a los eventos. RCAs[^1] para documentar workarounds
			- evolve -- u need 2 make time 2 RCA & investigate on what could b better'd
	- security -- proteger DATA/SYS/RRs -- acc ctrl, encrypt', security BPs 
	- reliability -- non stop -- fault tolerant, plan Bs
	- sustainability -- use as little energy as possible -- monitor r use
	- perfo eficc -- sys tailored 2 business needs -- monitor use, auto-scale, 
	- cost opt -- pay as little as possible -- right-sizing, reserved
- general design principles -- el CONCEPTO fundante -- what 4? effective cloud archs
	- kno thy capacity needs -- use auto-scaling when possible
	- test as in PROD -- u can create envs for testing and then turn them down and pay only for the RR n' T u used them
	- automate, automate, automate! -- what 4? 2 b able 2 experiment w the structure and have a safe rollback sys.
	- sys evolve, remember that -- decouple ur sys so when fix or update is needed other parts of sys won't b affected
	- use the data provided by monitoring
	- el que no rompe, no trabaja

[^1]: Root Cause Analysis
