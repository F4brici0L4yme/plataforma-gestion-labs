# Anexo 1: Tabla Detallada de Roles y Habilidades

Este documento detalla las **habilidades técnicas específicas**, **herramientas** y **certificaciones sugeridas** de cada rol para cada uno de los dos proyectos.

---

## 1. Tech Lead / Arquitecto

### Proyecto 1 — Nivel Avanzado (2 semestres mínimos de práctica)

**Habilidades técnicas:**
- Diseño de arquitecturas de software (monolito modular vs. microservicios básicos).
- Modelado de arquitectura con notación C4 (Contexto, Contenedores).
- Fundamentos de contenedores (Docker) y orquestación básica (Docker Compose).
- Diseño de APIs REST y contratos entre servicios.
- Toma de decisiones técnicas documentadas (ADRs - Architecture Decision Records).
- Conocimiento base de CI/CD (pipelines simples en GitLab CI).

**Herramientas:**
- Draw.io / PlantUML (diagramación C4).
- GitLab (repositorios, CI/CD, MRs).
- Docker / Docker Compose.
- Postman / Insomnia (pruebas de API).

**Certificaciones sugeridas:**
- Docker Certified Associate (nivel introductorio, opcional).
- Cursos de fundamentos de arquitectura de software (ej. Coursera "Software Architecture" - Univ. Alberta).

---

### Proyecto 2 — Nivel Senior (4 semestres mínimos de práctica)

**Habilidades técnicas:**
- Arquitectura de sistemas distribuidos e híbridos (on-premise + nube).
- Diseño de diagramas C4 completos, incluyendo **Diagrama de Despliegue** (Deployment), no solo Contexto y Contenedores.
- Justificación técnica de decisiones de infraestructura (ej. K3s/Talos vs. Kubernetes completo, según recursos, footprint y facilidad de mantenimiento).
- Patrones de resiliencia y escalabilidad (circuit breaker, autoscaling, alta disponibilidad).
- Gobierno de arquitectura y revisión de ADRs de todo el Tribe.
- GitOps como práctica de despliegue (ArgoCD o Flux).

**Herramientas:**
- Kubernetes (K3s, Talos Linux, kubeadm).
- ArgoCD / Flux (GitOps).
- Terraform + Ansible (infraestructura como código).
- Structurizr o C4-PlantUML (diagramas de despliegue versionados).

**Certificaciones sugeridas:**
- CKA (Certified Kubernetes Administrator).
- TOGAF Foundation (opcional, para gobierno de arquitectura).
- HashiCorp Certified: Terraform Associate.

> **Nota de arquitectura (incorporando el comentario de revisión):** la propuesta actual cubre el "qué" del sistema con los diagramas C4 de Contexto y Contenedores. Se recomienda que el Tech Lead de Proyecto 2 complete el **Diagrama de Despliegue**, especificando explícitamente qué componentes corren on-premise (Proxmox, K3s/Talos) y cuáles en la nube (backups, servicios gestionados, etc.), junto con una breve justificación escrita de por qué se eligió K3s/Talos en lugar de un clúster Kubernetes completo (ej. footprint de recursos en el laboratorio, facilidad de mantenimiento por parte de estudiantes, seguridad por diseño en el caso de Talos).

---

## 2. Backend Developer

### Proyecto 1 — Nivel Intermedio-Avanzado (2 semestres)

**Habilidades técnicas:**
- Programación backend en al menos un lenguaje moderno (Node.js, Python, Java o Go).
- Diseño de bases de datos relacionales (modelado, normalización).
- Autenticación y autorización básica (JWT, OAuth2).
- Consumo e implementación de APIs REST.
- Pruebas unitarias e integración básicas.

**Herramientas:**
- PostgreSQL.
- Frameworks según lenguaje: Express/NestJS (Node), FastAPI/Django (Python), Spring Boot (Java).
- Postman, Jest/PyTest/JUnit (testing).
- GitLab CI (pipelines básicos de build y test).

**Certificaciones sugeridas:**
- freeCodeCamp Backend Development.
- Certificación específica del framework elegido (ej. Spring Professional, si aplica).

---

### Proyecto 2 — Nivel Avanzado (3-4 semestres)

**Habilidades técnicas:**
- Arquitectura de microservicios y comunicación asíncrona (colas de mensajes).
- Integración con Keycloak (OAuth2/OIDC completo, gestión de roles y scopes).
- Diseño de APIs versionadas y documentadas (OpenAPI/Swagger).
- Manejo de transacciones distribuidas y consistencia eventual.
- Observabilidad de aplicaciones (logs estructurados, métricas, trazas).

**Herramientas:**
- Keycloak (Identity & Access Management).
- RabbitMQ / Kafka (mensajería).
- MinIO (almacenamiento de objetos S3-compatible).
- Swagger/OpenAPI, Prometheus + Grafana (observabilidad).

**Certificaciones sugeridas:**
- AWS Certified Developer / Azure Developer Associate (fundamentos transferibles a nube híbrida).
- Certified Kubernetes Application Developer (CKAD).

---

## 3. DevOps / Platform Engineer

### Proyecto 1 — Nivel Intermedio (1-2 semestres)

**Habilidades técnicas:**
- Fundamentos de Linux y administración de servidores.
- Contenerización de aplicaciones (Dockerfile, buenas prácticas de imágenes).
- CI/CD básico (pipelines de build, test y despliegue).
- Automatización simple con scripts (Bash) o Ansible básico.
- Fundamentos de virtualización (Proxmox VE: creación de VMs/LXC).

**Herramientas:**
- Proxmox VE.
- Docker, Docker Compose.
- GitLab CI/CD.
- Ansible (playbooks básicos).

**Certificaciones sugeridas:**
- Linux Foundation Certified IT Associate (LFCA).
- Docker Certified Associate.

---

### Proyecto 2 — Nivel Senior (3-4 semestres)

**Habilidades técnicas:**
- Administración de clústeres Kubernetes en producción (K3s/Talos).
- Infraestructura como código a nivel avanzado (Terraform + Ansible integrados).
- Implementación de GitOps (despliegues declarativos y auditable).
- Gestión de Harbor: políticas de retención, réplicas, escaneo automático.
- Gestión de infraestructura híbrida (balanceo de carga entre on-premise y nube, políticas de failover).

**Herramientas:**
- Talos Linux / K3s, Rancher (opcional, para gestión multi-clúster).
- Terraform, Ansible.
- Harbor (registry + Trivy integrado).
- ArgoCD/Flux, Prometheus/Grafana, Loki (logs).

**Certificaciones sugeridas:**
- CKA / CKS (Certified Kubernetes Security Specialist).
- HashiCorp Certified: Terraform Associate.
- Red Hat Certified Engineer (RHCE), si se usa distro compatible.

---

## 4. Security Engineer

### Proyecto 1 — Nivel Básico-Intermedio (1 semestre)

**Habilidades técnicas:**
- Fundamentos de seguridad en aplicaciones web (OWASP Top 10).
- Escaneo básico de vulnerabilidades en imágenes de contenedores.
- Buenas prácticas de gestión de secretos (variables de entorno, no hardcodear credenciales).
- Conceptos de autenticación segura (hashing de contraseñas, tokens).

**Herramientas:**
- Trivy (escaneo de imágenes).
- GitLab Secret Detection (built-in).
- OWASP ZAP (escaneo básico de aplicaciones web).

**Certificaciones sugeridas:**
- CompTIA Security+ (fundamentos generales).
- OWASP Top 10 (curso introductorio, ej. TryHackMe/PortSwigger Academy).

---

### Proyecto 2 — Nivel Avanzado (2-3 semestres)

**Habilidades técnicas:**
- Firma digital y verificación de imágenes de contenedores (cadena de confianza / supply chain security).
- Políticas de seguridad en Kubernetes (RBAC, Network Policies, Pod Security Standards).
- Gestión de identidad avanzada con Keycloak (federación, MFA, políticas de acceso condicional).
- Auditoría y trazabilidad completa (logs de acceso, cumplimiento normativo básico).
- Hardening de infraestructura (Talos Linux como base segura por diseño).

**Herramientas:**
- Cosign / Notary (firma digital de imágenes).
- Trivy + Harbor (escaneo automatizado en pipeline).
- Kyverno / OPA Gatekeeper (políticas como código en Kubernetes).
- Keycloak (MFA, federación de identidades).

**Certificaciones sugeridas:**
- Certified Kubernetes Security Specialist (CKS).
- CompTIA Security+ o superior.
- Certificación de proveedor cloud en seguridad (ej. AWS Security Specialty), como referencia transferible.

---

## 5. UX/UI Designer

### Proyecto 1 — Nivel Intermedio (1-2 semestres)

**Habilidades técnicas:**
- Diseño de interfaces para paneles administrativos (dashboards).
- Prototipado de baja y media fidelidad.
- Principios básicos de usabilidad y accesibilidad (WCAG nivel A).
- Diseño responsivo (desktop-first, ya que el uso principal es en laboratorio).

**Herramientas:**
- Figma (wireframes y prototipos).
- Design systems básicos (componentes reutilizables).

**Certificaciones sugeridas:**
- Google UX Design Certificate (Coursera).
- Curso introductorio de accesibilidad web (WCAG básico).

---

### Proyecto 2 — Nivel Avanzado (2-3 semestres)

**Habilidades técnicas:**
- Diseño de sistemas de diseño (Design Systems) escalables y documentados.
- Diseño de dashboards de analítica avanzada (métricas de uso de laboratorios, imágenes descargadas, etc.).
- Accesibilidad nivel AA (WCAG) para cumplimiento en entorno empresarial.
- Investigación de usuarios (entrevistas, tests de usabilidad) con estudiantes y personal de TI.
- Colaboración estrecha con Frontend para implementación fiel del diseño (design tokens, handoff).

**Herramientas:**
- Figma (con librerías de componentes y variantes).
- Storybook (documentación de componentes vivos).
- Herramientas de testing de accesibilidad (axe, Lighthouse).

**Certificaciones sugeridas:**
- Certified Usability Analyst (CUA) — opcional.
- Nielsen Norman Group UX Certification (referencia de prestigio en la industria).

---

## Resumen de Progresión General

| Rol | Proyecto 1 | Proyecto 2 |
|---|---|---|
| Tech Lead | Diagramas C4 de Contexto/Contenedores | Arquitectura híbrida completa con Diagrama de Despliegue y ADRs justificados |
| Backend | API REST monolítica | Microservicios con mensajería e IAM avanzado |
| DevOps | Docker/Ansible básico | Kubernetes en producción con GitOps |
| Security | Escaneo básico (Trivy) | Firma digital, RBAC y cumplimiento |
| UX/UI | Wireframes y dashboard simple | Design System y analítica avanzada |

---
