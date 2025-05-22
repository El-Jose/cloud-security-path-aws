# Proyecto Día 1: Hardening de Cuenta AWS

Configurar una cuenta de AWS siguiendo las mejores practicas para garantizar la seguridad desde el promer dia.

## ¿Que necesitas?
* Cuenta de AWS nueva o una ya existente.
* Permisos de administrador en la cuenta y Root.
* Navegador web y acceso a la consola AWS.

## Paso a paso
### 1. activar MFA para usuario root
* inicia sesion con el usuario root.
* Dirigete a "security credentials" y haz click en "Assign MFA device"
* Puedes seleccionar cualquiera de las siguientes 3 opciones: security key, Authenticator app y hardware OTPT token. Google authenticator app es recomendada para hacer esto seleccionando la segunda opcion.
**Importancia:** al realizar este paso evitas accesos no autorizados a la cuenta root.

