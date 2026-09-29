---
dudas: true
tags:
aliases:
---
### Dudas
- [ ] ABAC & IAM principals -- ¿cómo es éso?
- [ ] Tag Editor -- ¿por dónde se accede a él?
- [ ] AWS Resource Groups -- ??
### Notas
### Palabras clave
- concepto -- assign metadata 2 rr using `key=value`
- what 4?
	- org' n ID -- criteria: owner, project, env -- ABAC[^1] -- PILLAR: [[Well-Architected Framework#^ca7a1c|OPS EXCEL]] & [[Well-Architected Framework#^8f68ef|SECURITY]]
	- COST ALLOC' & OPT' -- tag-based billing -> track costs based on tags -- PILLAR: [[Well-Architected Framework#^f202d5|COST OPT']]
	- auto' based on tags -- PILLAR: [[Well-Architected Framework#^ca7a1c|OPS EXCEL]]
- strategies -- BPs
	- implementation
		- reqs
			- tagging STAKEHOLDERS -- x-fx team 2 consider ALL tagging needs
			- 1 tag -> 1 owner -- tags n values r important => need dedicated attn', owners define the tag values
			- focus on req'd/conditionally req'd tags
			- start with just a few tags -- the ones w higher priority
			- use'em consistently
		- steps
			- define strategy
			- tag policies -- [[AWS Organizations]], 4 consistency & standard', can b enforced
			- r tagging w [[(Simple) Systems Manager]] -- 4 auto/bulk tagging => programmatic app'
			- dashboard ur data
- Integration
	- [[AWS Config]] & [[AWS Control Tower]] -- enforce tagging policies
	- [[Console]] -- can consolidate rr based on tags
	- [[Cost Explorer]] -- detailed billing cost by tag breakdowns
	- [[Resource Groups]] -- create groups based on tags
	- [[Identity and Access Management|IAM]] policies -- supports tag-based conditions, caution: define who can modify tags

[^1]: attr-based access ctrl
