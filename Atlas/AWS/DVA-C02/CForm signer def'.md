---
dudas:
tags:
aliases:
incorrecta: true
---
Pregunta: UDEMY
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
A developer is defining the signers that can create signed URLs for their Amazon [[CloudFront]] distributions.

Which of the following statements should the developer consider while defining the signers? (Select two)

- a. Both the signers (trusted key groups and CloudFront key pairs) can be managed using the CloudFront APIs
	No, sólo los key groups.
- b. When you use the root user to manage CloudFront key pairs, you can only have up to two active CloudFront key pairs per AWS account
	Correcto. Si usás key groups podés crear hasta 5 por group, y por cuenta podés tener 4 groups.
- c. CloudFront key pairs can be created with any account that has administrative permissions and full access to CloudFront resources
	No, sólo con la root acc.
- d. You can also use AWS Identity and Access Management (IAM) permissions policies to restrict what the root user can do with CloudFront key pairs
	No, no se puede limitar los permisos del root.
- e. When you create a signer, the public key is with CloudFront and private key is used to sign a portion of URL
	Correcto.
### Condiciones
- 

### OPTS
a.

### Análisis

> [!note] Mi respuesta
> 
### Answer
BE