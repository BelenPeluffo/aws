---
dudas: true
tags:
aliases:
incorrecta: true
---
Pregunta: UDEMY
### Dudas
- [ ] Acc partitions -- ????
- [ ] S3 & ACL permissions -- investigar
- [ ] ¿qué diferencia hay entre A y C?
### Notas
- 
### Situación
A large firm stores its static data assets on Amazon [[Simple Storage Service|S3]] buckets. Each service line of the firm has its own AWS account. For a business use case, the Finance department needs to give access to their S3 bucket's data to the Human Resources department.

Which of the below options is NOT feasible for cross-account access of S3 bucket objects?

- A. Use Resource-based policies and AWS Identity and Access Management ([[Identity and Access Management|IAM]]) policies for programmatic-only access to S3 bucket objects
	Éste es el medio más común por el que gestionar este tipo de casos.
- B. Use Access Control List (ACL) and IAM policies for programmatic-only access to S3 bucket objects
	Casi siempre es mejor optar por IAM roles en vez de ACL, pero hay escenarios en los que podría justificarse su uso. Ampliar.
- C. Use Cross-account IAM roles for programmatic and console access to S3 bucket objects
	Es lo ideal usar éste, porque así no dependés tanto de usar las resource-based policies.
- D. Use IAM roles and resource-based policies delegate access across accounts within different partitions via programmatic access only
	Sólo tienen esa capacidad within THE SAME partition.
### Condiciones
- 

### OPTS
a.

### Análisis
B
> [!note] Mi respuesta
> 
### Answer
D