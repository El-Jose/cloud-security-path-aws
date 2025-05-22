# Proyecto Día 1: Hardening de Cuenta AWS

Configurar una cuenta de AWS siguiendo las mejores practicas para garantizar la seguridad desde el promer dia.

## ¿Que necesitas?
* Cuenta de AWS nueva o una ya existente.
* Permisos de administrador en la cuenta y Root.
* Navegador web y acceso a la consola AWS.

## Paso a paso
### 1. Activar MFA para usuario root
* Inicia sesion con el usuario root
* Dirigete a "security credentials" y haz click en "Assign MFA device"
* Puedes seleccionar cualquiera de las siguientes 3 opciones: security key, Authenticator app y hardware OTPT token. Google authenticator app es recomendada para hacer esto seleccionando la segunda opcion.
**Importancia:** al realizar este paso evitas accesos no autorizados a la cuenta root.
### 2. Crear un usuario administrador desde IAM
* Dirigete a IAM > Users > Add user
* Selecciona un nombre, para este ejemplo es "admin-user"
* Habilita acceso programatico y desde consola
* Selecciona la opcion "I want to create an IAM user"
* Selecciona la opcion de password autogenerado y habilita el checkbox para forzar cambio de password en el proximo acceso del usuario
* Asigna este usuario a un grupo, dado caso que no exista crealo. asegurate que el grupo tiene como politica adjunta "	
AdministratorAccess"
* Habilita MFA en este usuario tambien
**Importancia:** El usuario root no debe utilizarse nunca para tareas del dia a dia, admin-user es el encargado de eso.
