- [ ] EC2, Autoscaling groups, security groups -- cómo están wired, IP ranges n all that; NEED 2 know
- [ ] ECS y los contenedores que se comparten entre tasks
- [ ] ElasticBeanstalk y envs
- [ ] NACL vs SG -- memo-way 2 remember which allows which n which allows whut
- [ ] EC2-EBS wiring
- [ ] ECS-ASG -- wiring?
- [x] specific sizes -- SQS sms, storages ✅ 2026-08-13
	- [[Simple Storage Service|S3]] -- 5tb max size/object, 100 buckets /acc
	- [[Simple Queue Service|SQS]] -- 1024kb max/sms, ret day: 14 max
	- [[Lambda]] -- exec time: 15m max
	- [[DynamoDB]] -- 400kb max/item, tablas: 256 max
	- [[Kinesis Data Streams]] -- 1mb max/registro
- [ ] CloudFront -- varias preguntas me costaron
- [ ] EFS storage clases
- [ ] S3 x-acc acc permissions
- [ ] S3 signed URL vs CFront signed URL?? -- ¿qué diferencia hay?
```dataviewjs
const incorrectQuestions = dv.pages('"Atlas/AWS/DVA-C02"').where(p => p.incorrecta == true).length;
const correctQuestions = dv.pages('"Atlas/AWS/DVA-C02"').where(p => p.incorrecta == false || p.incorrecta == null).length;

dv.paragraph(`
\`\`\`chart
type: doughnut
labels:
 - Incorrectas
 - Correctas
series:
 - data:
    - ${incorrectQuestions}
    - ${correctQuestions}
\`\`\`
`);
```
```base
filters:
  and:
    - file.inFolder("Atlas/AWS/DVA-C02")
    - incorrecta == true
properties:
  file.name:
    displayName: Question
views:
  - type: table
    name: Table
    sort: []

```