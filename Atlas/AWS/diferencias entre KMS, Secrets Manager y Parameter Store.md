# Keep your secrets: Diferencias entre KMS, Secrets Manager y Parameter Store
### [[Secrets Manager]]
KEY: Rotación automática de secretos de forma nativa. Ninguno de los otros servicios tiene esa feature.
Más caro.
[[Key Management Service|KMS]] mandatory.

### [[SSM Parameter Store]]
KEY: Store & built-in version track de secret values -> parameter history
USE CASES: más config que otra cosa.
Más económico.
Se puede hacer un rip-off de rotación pero requiere otros servicios y configuraciones ([[Lambda]] y [[EventBridge]]).
KMS optional porque no sólo se guardan secrets sino también simples parámetros que no necesariamente requieren de encrypt'.
Se encripta usando `Type=SecureString`. => Implica un paso extra, en comparación a SM, porque tenés que hacer 1. retrieval de secret, 2. retrieval de key KMS y 3. dencrypt'.

### [[Key Management Service]]
No sirve para guardar secretos. Es un servicio de encriptado.
Ambos, PS y SM lo usan para encriptar sus secretos.