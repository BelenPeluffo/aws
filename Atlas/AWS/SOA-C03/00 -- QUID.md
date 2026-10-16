---
dudas:
tags:
aliases:
---
> [!info] PRE-LEARN
> ![video](https://youtu.be/5JTBS09e7ew?si=iSdvE3L0YyHEKjaP&t=105)
### Dudas

### Domains
- Monitoring, logging, remediation, perfo optim'
- Reliability, BS continuity
- Deploy, privision, auto'
- Sec & complu
- Network & cont delivery
### Temario
- [[The art of ID and ACC mgmt]]
- [[The art of TAGS]]
- [[The art of policies]]
- [[The art of MFA]]
- [[IAM Identity Center]] -- auth
- [[AWS Organizations]] -- central mgmt
- [[AWS Control Tower]] -- central mgmt, more powerful than AWS Orgs (which is used under-the-hood in Control Tower), keyword: landing zone
- [[CloudTrail]] -- audit
### Notas
> [!note] Dónde quedé
> En [AWS Skill Builder](https://skillbuilder.aws/learning-plan/BZJS8KQ916/aws-cloudops-engineer-learning-plan-includes-labs/8ZFKBMAMFH)

- CloudOps = {deploy, monitor, ~~maintain~~ sustain, secure, optimize} = DMSx2O

```base
filters:
  and:
    - file.inFolder("Atlas/AWS")
    - dudas == true
    - file.tags.contains("SOA-C03")
properties:
  file.name:
    displayName: Question
views:
  - type: table
    name: Table
    sort: []

```