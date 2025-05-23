# Cloud Security Engineer – Plan de Proyectos / Project Plan

Este repositorio contiene una serie de proyectos prácticos diseñados para desarrollar habilidades como Cloud Security Engineer utilizando AWS.  
This repository contains a series of hands-on projects designed to develop skills as a Cloud Security Engineer using AWS.

---

## 🛡️ Etapa 1 – Fundamentos de seguridad en la nube  
### Stage 1 – Cloud Security Fundamentals

- **Hardening de cuenta AWS**  
  Configura una cuenta AWS desde cero: IAM seguro, MFA, políticas de presupuesto, CloudTrail, GuardDuty.  
  **AWS Account Hardening** – Set up an AWS account from scratch: secure IAM, MFA, budget policies, CloudTrail, GuardDuty.

- **Escáner de buckets S3 públicos (Python)**  
  Script que detecta y lista buckets S3 públicos, con opción de corregir.  
  **Public S3 Bucket Scanner (Python)** – Script to detect and list public S3 buckets, with an option to remediate.

- **Bloqueo y monitoreo de S3**  
  Configura buckets con acceso privado, versionado y logging. Incluye alerta vía SNS ante cambios.  
  **S3 Lockdown and Monitoring** – Configure private access buckets with versioning and logging. Include SNS alert on changes.

- **Terraform: Infraestructura segura (S3, EC2, VPC)**  
  Infraestructura básica definida como código, con control de accesos mínimos.  
  **Terraform: Secure Infrastructure (S3, EC2, VPC)** – Basic infrastructure defined as code with least-privilege access control.

- **AWS Config + Reglas de cumplimiento**  
  Configura reglas que detecten desviaciones: puertos abiertos, S3 públicos, IAM inseguros.  
  **AWS Config + Compliance Rules** – Set up rules to detect misconfigurations: open ports, public S3, insecure IAM.

---

## ⚙️ Etapa 2 – Automatización y detección  
### Stage 2 – Automation and Detection

- **CloudTrail + Sistema de alertas con Lambda**  
  Lambda que reacciona ante eventos de IAM o accesos sospechosos.  
  **CloudTrail + Lambda Alert System** – Lambda function that reacts to IAM events or suspicious access.

- **Checkov + CI/CD con Terraform**  
  Pipeline en GitHub Actions que escanea IaC en busca de vulnerabilidades antes de aplicar.  
  **Checkov + Terraform CI/CD** – GitHub Actions pipeline that scans IaC for vulnerabilities before deployment.

- **Escaneo de imágenes Docker con Trivy**  
  Pipeline automatizado que bloquea imágenes inseguras.  
  **Docker Image Scanning with Trivy** – Automated pipeline that blocks insecure images.

- **Análisis de políticas IAM (Python)**  
  Script que identifica políticas con comodines (*) o privilegios excesivos.  
  **IAM Policy Analysis (Python)** – Script that identifies wildcard policies (*) or excessive privileges.

- **Notificador de GuardDuty multirregión**  
  Script que habilita GuardDuty en múltiples regiones + alerta vía SNS.  
  **Multi-region GuardDuty Notifier** – Script that enables GuardDuty across regions + sends alerts via SNS.

---

## 🔐 Etapa 3 – Seguridad de aplicaciones y servicios  
### Stage 3 – Application and Service Security

- **CI/CD seguro para Lambda**  
  Despliegue controlado de funciones Lambda escaneadas (Bandit/Semgrep).  
  **Secure Lambda CI/CD** – Controlled deployment of scanned Lambda functions (Bandit/Semgrep).

- **Diseño seguro de microservicios (Fargate)**  
  Aplicación dividida en microservicios con permisos mínimos y tráfico restringido.  
  **Secure Microservices Design (Fargate)** – App split into microservices with least privilege and restricted traffic.

- **App Flask con autenticación IAM**  
  Mini app Flask desplegada en EC2, con acceso controlado vía roles IAM y seguridad básica.  
  **Flask App with IAM Authentication** – Mini Flask app deployed on EC2 with IAM role-based access control and basic security.

- **Monitor de logs con Athena + S3 + CloudWatch**  
  Consolida logs y permite consultas de seguridad vía Athena.  
  **Log Monitor with Athena + S3 + CloudWatch** – Consolidates logs and enables security queries using Athena.

---

## 📊 Etapa 4 – Visibilidad, auditoría y presentación  
### Stage 4 – Visibility, Auditing, and Presentation

- **Dashboard de seguridad con Grafana**  
  Visualiza hallazgos de CloudTrail, GuardDuty y Config en tiempo real.  
  **Security Dashboard with Grafana** – Visualizes findings from CloudTrail, GuardDuty, and Config in real time.

- **Simulación de incidente y respuesta**  
  Reproduce accesos sospechosos y automatiza la respuesta (bloqueo, logging, alerta).  
  **Incident Simulation and Response** – Recreates suspicious access and automates response (blocking, logging, alerting).

- **Reporte automatizado de cumplimiento**  
  Genera reporte semanal de hallazgos de seguridad y lo envía por correo (SES).  
  **Automated Compliance Report** – Weekly report of security findings sent via email (SES).

- **Cloud Security Lab – Integrador**  
  Una pequeña app en AWS con infraestructura segura, CI/CD, detección y remediación.  
  **Cloud Security Lab – Integrator** – A small AWS app with secure infrastructure, CI/CD, detection, and remediation.

- **Revisión y documentación de todos los proyectos**  
  Refinamiento, capturas, README.md, licencias, diagrama por proyecto.  
  **Review and Documentation of All Projects** – Refinement, screenshots, README.md, licenses, project diagrams.

- **Publicación y presentación del portafolio**  
  Publicar en GitHub, estructurar perfil, añadir README principal con índice y showcase.  
  **Portfolio Publishing and Presentation** – Publish on GitHub, structure profile, add main README with index and showcase.
