---
dudas:
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 82 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107445-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] 
### Notas
- 
### Situación
A developer is building a **highly secure** healthcare application using **serverless components**. This application requires writing temporary data to **/tmp storage** on an AWS [[Lambda]] function.  
  
How should the developer encrypt this data?

- A. Enable Amazon EBS volume encryption with an AWS KMS key in the Lambda function configuration so that all storage attached to the Lambda function is encrypted.
	No puede ser esta porque nos está diciendo que el storage tiene que ser en /temp, entonces no puede ser en EBS.
- B. Set up the Lambda function with a role and key policy to access an AWS KMS key. Use the key to generate a data key used to encrypt all data prior to writing to /tmp storage.
	Creo que es ésta, pero no dice el tipo de encriptado.
	En realidad, sí nos dice: al decir *generate data key* nos está nombrando el método que va a usar, que es el de encriptado asimétrico.
- C. Use OpenSSL to generate a symmetric encryption key on Lambda startup. Use this key to encrypt the data prior to writing to /tmp.
	No queremos que sea simétrico. Para más seguridad, es mejor asimétrico.
- D. Use an on-premises hardware security module (HSM) to generate keys, where the Lambda function requests a data key from the HSM and uses that to encrypt data on all requests to the function.
	No sé por qué no puede ser ésta. Porque genera latencia y no es práctica a los fines de ser serverless.
### Condiciones
- 

### OPTS
a.

### Análisis
Si me dice **highly secure**, entonces pienso [[CloudHSM]].
> [!note] Mi respuesta
> 
### Answer
B