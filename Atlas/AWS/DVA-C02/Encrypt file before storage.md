---
dudas:
tags:
  - "#reading-error"
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 77 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/107443-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x]  ✅ 2026-08-05
### Notas
- 
### Situación
An application under development is required to store **hundreds of video files**. The data must be **encrypted** within the application **prior to storage**, with a **unique key for each video** file.  
  
How should the developer code the application?

- A. Use the KMS Encrypt API to encrypt the data. Store the encrypted data key and data.
- B. Use a cryptography library to generate an encryption key for the application. Use the encryption key to encrypt the data. Store the encrypted data. -- no, porque tiene que ser UNA por VIDEO; según esta propuesta, sería UNA por para TODAS.
- C. Use the KMS GenerateDataKey API to get a data key. Encrypt the data with the data key. Store the encrypted data key and data.
- D. Upload the data to an S3 bucket using server side-encryption with an AWS KMS key. -- no, porque tiene que encriptarse ANTES de ser almacenada...
### Condiciones
- 

### OPTS
a.

### Análisis
Siento que debería ser la B... Más que nada porque si tiene que ya estar encriptada antes de que llegue, entonces es la app la que se encargaría de la encriptación... En su defecto, C.
> [!note] Mi respuesta
> 
### Answer