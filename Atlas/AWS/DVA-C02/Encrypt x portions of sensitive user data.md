---
dudas: true
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 550 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/157510-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] ¿what did WAF stand 4?
	Web App Firewall.
- [ ] what is the use of WAF?
- [ ] field-level encrypt' -- ???
- [ ] CloudFront y WebSocket -- ??
### Notas
- 
### Situación
A developer is building an application that stores **sensitive user data**. The application includes an Amazon [[CloudFront]] distribution and multiple AWS [[Lambda]] functions that handle user requests.  
  
The user requests contain over 20 data fields. Each application transaction contains **sensitive data that must be encrypted**. Only specific parts of the application need to have the ability to decrypt the data.  
  
Which solution will meet these requirements?

- A. Associate the CloudFront distribution with a [[Lambda#^8f52e7|Lambda@Edge]] function. Configure the function to perform field-level asymmetric encryption by using a user-defined RSA public key that is stored in AWS Key Management Service (AWS [[Key Management Service|KMS]]).
- B. Integrate AWS WAF with CloudFront to protect the sensitive data. Use a Lambda function and self-managed keys to perform the encryption and decryption processes.
	-- mmm... me parece que para ésto no sirve [[WAF]]
- C. Configure the CloudFront distribution to use WebSockets by forwarding all viewer request headers to the origin. Create an asymmetric AWS KMS key. Configure the CloudFront distribution to use field-level encryption. Use the AWS KMS key.
- D. Configure the cache behavior in the CloudFront distribution to require HTTPS for communication between viewers and CloudFront. Configure GoudFront to require users to access the files by using either signed URLs or signed cookies.
	-- no tiene que ver con acceso seguro
### Condiciones
- 

### OPTS
a.

### Análisis
A
> [!note] Mi respuesta
> 
### Answer
~~C~~
Ambas son correctas, pero según la IA de Udemy, la A es la mejor porque es más simple y está más preparada para la masividad de CloudFront.