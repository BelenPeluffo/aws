---
dudas:
tags:
  - DVA02-26
aliases:
  - CDK
---
### Dudas
- [x]  ✅ 2026-08-05
### Notas
### Palabras clave
- concepto -- define infra in programming lang, allow deployment of infra & code 2gether, allows  4 type safety, it's a library
	- construct -- alle wir brauchen 2 create the final stack
		- layers -- higher the level -> less config
			- 1 -- CFN rr, los métodos empiezan con `Cfn...`, pareciera ser de más bajo nivel como el lenguaje assembler es a C++, por ejemplo
			- 2 
			- 3 -- pattern
- CDK CLI
	- `cdk init`
	- `cdk bootstrap` -- oncper acc&R, needs this in acc before deploy anything
	- `cdk synth` -- transforms code into [[CloudFormation]] template
	- `cdk deploy` -- deploy template 2 CloudForm
	- `cdk diff` -- ver diff entre lo local y lo deployado
	- `cdk destroy`
- testing
	- `.fromStack` -- template already deploy'd
	- `fromString` -- template not deploy'd
- [[Serverless App Model|SAM]]
	- differences -- SAM focuses only on serverless & u write in yaml, with CDK u can do server & is more 4 INFRAaC & u write in a prog-lang
	- integrat' -- synth app & test template locally w SAM CLI
