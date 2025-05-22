# Proyecto Día 1: Hardening de Cuenta AWS

Este proyecto implementa medidas de seguridad recomendadas para proteger una cuenta de AWS desde su creación desde AWS CLI.

## ¿Que necesitas?
* Cuenta de AWS nueva o una ya existente.
* Permisos de administrador en la cuenta y Root.
* AWS CLI

## Paso a paso
### 1. Activar MFA para usuario root
Este paso SOLO se puede hacer desde la consola de AWS
**Importancia:** al realizar este paso evitas accesos no autorizados a la cuenta root.

### 2. Crear un usuario administrador desde IAM
`esto es un bloque de codigo`


* Dirigete a IAM > Users > Add user
* Selecciona un nombre, para este ejemplo es "admin-user"
* Habilita acceso programatico y desde consola
* Selecciona la opcion "I want to create an IAM user"
* Selecciona la opcion de password autogenerado y habilita el checkbox para forzar cambio de password en el proximo acceso del usuario
* Asigna este usuario a un grupo, dado caso que no exista crealo. asegurate que el grupo tiene como politica adjunta "	
AdministratorAccess"
* Habilita MFA en este usuario tambien
 El usuario root no debe utilizarse nunca para tareas del dia a dia, admin-user es el encargado de eso.

### 3. Eliminar claves de acceso del usuario root
* Ve a IAM > Root user > Access keys.
* Si existen, elimínalas.
**Importancia:** El root no debe tener claves de acceso para evitar automatizaciones peligrosas.

### 4. Crear politica de contraseña segura
* Ve a IAM > Account settings
* Define una politica para contraseña como:
    - Longitud mínima: 14 caracteres
    - Requiere mayúsculas, minúsculas, números y caracteres especiales
    - Caducidad: 90 días
    - No reutilizar últimas 5 contraseñas
**Importancia:** Con esto redimos el riesgo a contraseñas debiles o que ya esten comprometidas

### 5. Activar AWS Cloudtrail
AWS Cloudtrail es un servicio que permite registrar, monitorear y retener todas las actividades realizadas en la cuenta.
* Ve a CloudTrail > Trails > Create trail
* selecciona como nombre "OrganizationTrail" o "MainTrail"
* Aplicar a todas las regiones
* Guardar en un bucket S3 privado, podrias nombrarlo cloudtrail-logs-<id>
* Activar log file validation y insight events
 Esto nos permite dejar un rastro auditable de todas nuestras acciones

### 6. Activar GuardDuty
* Ve a GuardDuty > Enable.
* Habilítalo en todas las regiones donde tengas recursos
* Opcional: Configura SNS para recibir alertas
**Importancia:** Detecta comportamiento malicioso o anómalo automáticamente

### 7. Configurar presupuestos y alertas de costo
* Ve a Billing > Budgets > Create budget
* Define un presupuesto mensual (por ejemplo, USD 5)
* Configura alertas por email cuando se supere el 50%, 80%, 100%.
 Con esta configuracion evitas cobros altos no esperados, sobre todo util para entornos de prueba

### 8. Activar AWS Config
* Ve a Config > Settings.
* Selecciona todas las regiones.
* Crear un bucket nuevo para logs si se solicita.
* Usa reglas predefinidas como:
    - s3-bucket-public-read-prohibited
    - iam-user-mfa-enabled
    - cloudtrail-enabled
**Importancia:** Auditoría en tiempo real de configuraciones peligrosas

## Recursos
- [AWS IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
- [AWS Well-Architected Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/)