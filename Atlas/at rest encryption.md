#encryption 
### server side
Encrypted after being received. Permanecerá encriptado mientras esté at rest, en cuanto sea enviado, se decriptará antes de proceder. Por esta razón, el server tiene las keys, no el cliente.

### client side
Se encripta y desencripta en el cliente, por lo que el server sólo tendrá acceso a la versión encriptada de los datos.