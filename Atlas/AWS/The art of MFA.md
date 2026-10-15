---
dudas: true
tags:
  - SOA-C03
aliases:
---
### Dudas
- [ ] si el MFA se aplica usando un device, ¿cómo hacen los Roles y groups para comply?
- [ ] ¿cómo se ve una policy que enforces MFA en un role o group?
- [ ] ¿se puede enforce el MFA a Users usando policies o el [[CLI]]?
- [ ] "You can use AWS Security Token Service (AWS STS) to request temporary credentials that enforce MFA" -- ¿ésto significa que entonces, si yo tengo una app y quiero enforce el MFA sí o sí tengo que crear un USER para esa app al que poder asociar un MFA device?
- [ ] MFA delete -- ¿existe para algún otro servicio o sólo para [[Simple Storage Service#^6a1c67|S3]]?
### Notas
### Palabras clave
- concepto -- xtra layer of protection 4 when pass is compromised, u need a token that is given 2 u by a device
- factors -- something u...
	- KNOW -- user y pass
	- HAVE -- MFA device
		- token devices
			- virtual MFA -- authenticator TOTP
			- FIDO keys -- hardware U2F/WebAuth
			- hardware TOTP
			- SMS
	- R -- biometric