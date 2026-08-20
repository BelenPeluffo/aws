---
aliases:
  - OSI model
---
#infra
Es un modelo de transferencia de info en internet, donde cada capa representa un set de tareas particulares.

| CAPA      | DOMINIO         | CONCEPTO                                                             | EJEMPLOS AWS                                                                                                                                                                          |
| --------- | --------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 7 ^capa-7 | Aplicación      | + cercana al user, residen las apps; interpreta interacción con user | [[API Gateway]], [[ALB]], [[Atlas/AWS/Lambda\|Lambda]], [[AppSync]], [[Atlas/AWS/CloudFront\|CloudFront]], [[Atlas/AWS/DynamoDB\|DynamoDB]], [[Atlas/AWS/Relational DB Service\|RDS]] |
| 6 ^capa-6 | Presentación    | transforma datos, encripta/desencripta                               | [[Key Management Service\|KMS]]                                                                                                                                                       |
| 5 ^capa-5 | Sesión          | gestiona la conexión entre las partes y garantiza su continuidad     | [[Atlas/AWS/Cognito\|Cognito]], ELB Sticky Sessions, [[SSM Session Manager]]                                                                                                          |
| 4 ^capa-4 | Transporte      | se encarga de que la info llegue bien                                | [[NLB]] (TCP, UDP)                                                                                                                                                                    |
| 3 ^capa-3 | Red             | rutea                                                                | Route tables, [[IGW]], [[NATGW]], Transit-GW, [[Atlas/AWS/Route 53\|Route 53]]                                                                                                        |
| 2 ^capa-2 | Enlace de datos | gestiona pasaje de info entre dispositivos                           | VPC, SG, NACL?                                                                                                                                                                        |
| 1 ^capa-1 | Física          | infra física que permite la comunicación                             | Regiones, AZ, infra física                                                                                                                                                            |