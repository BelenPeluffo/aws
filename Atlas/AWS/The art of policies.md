---
dudas:
tags:
  - SOA-C03
aliases:
---
### Dudas
- [ ] 
### Notas
### Palabras clave
- concept -- **permission doc 4 `ALLOW`/`DENY` acts on x rr**, `Statement=Array<Permission>` ^cef727
- eval of policies
	- ==general rule== -- eplicit `DENY` ? `DENY` : explicit `ALLOW` ? `ALLOW` : `DENY`, explicit `DENY` >> explicit `ALLOW`
	- vs [[Simple Storage Service|S3]] -- all rules are joined => IAM policy + bucket policy = total de policies
- elements ^85c1a1
	- `Effect` -- `ALLOW` | `DENY`
	- `Principal` -- affected entity, opt
	- `Action` -- `string | []`
	- `Resource` -- `string | []`
	- `Condition` -- opt
- types
	- ID-based -- inline 4 [[Identity and Access Management|IAM]] entities
	- r-based -- inline 4 rr, e.g: [[Simple Storage Service#^7bf99d|bucket policies]] | [[Identity and Access Management#^5ec1d6|role trust policies]]
	- org SCP[^1] -- [[AWS Organizations]], max perm 4 acc members
	- ACL (as seen in [[Network Access Control List|N-ACL]]) -- r-attached, 4 x-acc accs, not-JSON

[^1]: S Control Policy
