---
dudas: true
tags:
  - security
aliases:
incorrecta:
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 38 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103522-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [ ] [[Identity and Access Management|IAM]] instance profile???
	Se crea por defecto al crear cualquier rol de IAM. Está sólo accesible para las instancias de EC2. Para modificarla hay que modificar el rol. [[Identity and Access Management#^cfdbcd|Más al respecto]].
### Notas
- 
### Situación
App en [[Elastic Compute Cloud|EC2]] conectada a un [[Simple Storage Service|S3]] para listar sus objetos. Ése es el ideal. Al testear luego de implementar, la lista está vacía.
### Condiciones
- most secure solution?

### OPTS
a. upd IAM de EC2 para incluir `S3:*` -- le está dando permisos de más => poco segura

b. ídem para incluir `S3:ListBucket` -- ppio de least priviledge ^31dd0c

c. upd dev permissions para `S3:ListBucket` -- no es para el dev sino para la instancia

d. upd bucket policy para habilitar `S3:ListBucket` para acc específica del EC2 -- no es la más segura porque le estás dando acceso a LA CUENTA ENTERA y no específicamente al EC2

### Análisis
Mi primer instinto es B. Pero para gestión de accesos debería usarse una r-policy y por lo tanto debería ser la D, ¿o no...?
> [!note] Mi respuesta
> [[Acc permissions w bucket#^31dd0c|B]].
### Answer
B.