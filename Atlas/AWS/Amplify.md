---
dudas: true
tags:
  - DVA02-28
aliases:
---
### Dudas
- [ ] ¿qué diferencia hay entre STUDIO y HOSTING?
- [ ] ¿Amplify sólo sirve para deployar BE?
- [ ] ¿Qué diferencia hay con [[Elastic Beanstalk]]?
### Notas
### Palabras clave
- concept -- mobile & web, app mgmt UI, HTTPS, custom domains, 
- components
	- Studio -- dev suite, deploy, data modeling
	- CLI
		- `amplify init`
		- `amplify add auth` -- authen', [[Atlas/AWS/Cognito]]
		- `amplify add api` -- datastore, [[AppSync]] && [[Atlas/AWS/DynamoDB]]
		- `amplify add hosting`
	- Libraries -- 4 conn 2 other AWS SS
	- Hosting -- build, host, CICD, PR, custom domain
- E2E testing -- @ test step defin'd in `amplify.yml`, via Cypress #test-question  ^9e5771
- integrations
	- src code -- BitBucket, GitHub, CodeCommit