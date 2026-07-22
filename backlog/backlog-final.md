# Backlog Final del Proyecto

**Proyecto:** Plataforma Híbrida de Gestión de Laboratorios de Computación
**Estado:** Versión Completa (Priorizado)
**Fecha:** Julio 2026

---

## Épicas Principales

### Épica 1: Gestión Organizacional y Procesos del Laboratorio
**Prioridad:** Alta (Fundacional)
**Descripción:** Definir, documentar e implementar la organización mínima requerida para el uso efectivo de la plataforma, incluyendo roles, procesos y flujos de trabajo.

#### Historias de Usuario

- [ ] Como **Administrador**, quiero definir roles y permisos claros, para que cada usuario sepa sus responsabilidades.
- [ ] Como **Product Owner / Docente**, quiero un catálogo de procesos estandarizados del laboratorio (reserva de equipos, solicitud de imágenes, etc.), para que todos los usuarios sigan el mismo flujo de trabajo.
- [ ] Como **Responsable**, quiero un flujo claro de aprobación y gestión de imágenes de contenedores, para evitar publicar software sin control ni trazabilidad.
- [ ] Como **Estudiante**, quiero conocer el proceso para solicitar recursos y obtener imágenes para mi computadora personal, para no perder tiempo averiguando a quién pedirle acceso.
- [ ] Como **Jefe de Laboratorio**, quiero dashboards que muestren el estado de uso de los recursos físicos y virtuales, para tomar decisiones informadas sobre capacidad y mantenimiento.
- [ ] Como **Equipo**, quiero una matriz RACI clara para todos los procesos críticos, para saber quién decide, ejecuta y es consultado en cada actividad.
- [ ] Como **Docente**, quiero un proceso documentado de onboarding para estudiantes nuevos al inicio del semestre, para que puedan usar la plataforma desde el primer día de clases sin soporte manual.

**Criterios de Aceptación:**
- Documentación oficial de procesos (en Markdown y versión PDF).
- Matriz RACI implementada.
- Flujos automatizados donde sea posible.

---

### Épica 2: Gestión de Usuarios, Proyectos/Cursos y Permisos
**Prioridad:** Alta (Must Have)
**Descripción:** Centralizar la autenticación y el control de acceso, y permitir organizar usuarios dentro de proyectos (empresa) o cursos (universidad).

#### Historias de Usuario

- [ ] Como **Estudiante o Docente**, quiero iniciar sesión mediante un sistema de autenticación centralizado (Keycloak), para no manejar credenciales distintas por cada servicio de la plataforma.
- [ ] Como **Docente**, quiero crear un Curso (o **Product Owner**, un Proyecto en la versión empresa) y asociarle una lista de participantes, para organizar el trabajo bajo un mismo espacio.
- [ ] Como **Administrador**, quiero asignar usuarios a un proyecto/curso específico, para que solo tengan acceso a los recursos que les corresponden.
- [ ] Como **Administrador**, quiero configurar permisos mediante control de acceso basado en roles (RBAC avanzado), para restringir acciones según el rol del usuario (estudiante, docente, admin, etc.).
- [ ] Como **Administrador**, quiero revocar el acceso de un usuario a un proyecto/curso cuando este finalice, para mantener actualizada la seguridad de la plataforma.
- [ ] Como **Administrador**, quiero distinguir entre el modo Académico y el modo Empresarial al configurar un espacio de trabajo, para aplicar automáticamente el nivel de permisos y estándares que corresponde a cada contexto.

**Criterios de Aceptación:**
- Integración funcional con Keycloak (SSO).
- Roles y permisos configurables sin intervención de código.
- Registro de auditoría de cambios de permisos.

---

### Épica 3: Catálogo de Imágenes de Contenedores
**Prioridad:** Alta (Must Have - MVP)
**Descripción:** Proveer un catálogo centralizado y trazable de imágenes de contenedores, desde su creación hasta su descarga por parte de los estudiantes.

#### Historias de Usuario

- [ ] Como **Administrador de Plataforma**, quiero implementar Harbor como Registry privado, para centralizar el almacenamiento y distribución de imágenes de contenedores.
- [ ] Como **Docente**, quiero solicitar la creación o importación de una imagen para mi curso mediante una interfaz simple, para no depender de comandos manuales de Docker/Harbor.
- [ ] Como **Responsable de Aprobación**, quiero revisar y aprobar (o rechazar) las solicitudes de imágenes antes de su publicación, para mantener el control de calidad del catálogo.
- [ ] Como **Estudiante**, quiero descargar de forma segura una imagen oficial del catálogo, para ejecutarla en mi computadora personal fuera del laboratorio.
- [ ] Como **Estudiante**, quiero ver los metadatos de cada imagen (versión, curso asociado, fecha de publicación), para asegurarme de usar la versión correcta.
- [ ] Como **Docente**, quiero recibir una notificación cuando una imagen de mi curso tenga una nueva versión disponible, para decidir si la aplico antes del siguiente laboratorio.

**Criterios de Aceptación:**
- Registry Harbor desplegado y accesible.
- Pipeline de publicación integrado con la Épica 7 (escaneo y firma).
- Descarga funcional validada desde fuera de la red del laboratorio.

---

### Épica 4: Gestión de Hardware e Inventario
**Prioridad:** Alta (Must Have - básico)
**Descripción:** Llevar control centralizado del hardware del laboratorio y su disponibilidad para reserva.

#### Historias de Usuario

- [ ] Como **Administrador del Laboratorio**, quiero un inventario automatizado de computadoras, servidores e impresoras, para tener visibilidad actualizada del hardware disponible.
- [ ] Como **Docente o Estudiante**, quiero reservar un equipo o laboratorio en un horario específico, para asegurar su disponibilidad antes de una clase o práctica.
- [ ] Como **Administrador**, quiero monitorear el estado de los laboratorios (equipos activos, en mantenimiento, fuera de servicio), para priorizar reparaciones y evitar sorpresas el día de la clase.
- [ ] Como **Técnico de Laboratorio**, quiero registrar una incidencia sobre un equipo, para dar seguimiento a su mantenimiento correctivo.
- [ ] Como **Administrador**, quiero recibir una alerta automática cuando un equipo lleve varios días marcado con incidencia sin resolver, para evitar que quede fuera de servicio indefinidamente.

**Criterios de Aceptación:**
- Inventario sincronizado con el estado real del hardware.
- Sistema de reservas sin conflictos de horario.
- Panel de monitoreo visible para administradores.

---

### Épica 5: Frontend y Portal de Usuario
**Prioridad:** Should Have (dashboards) / Must Have (funciones base)
**Descripción:** Proveer una interfaz unificada donde los distintos roles interactúen con la plataforma sin necesidad de herramientas externas.

#### Historias de Usuario

- [ ] Como **Estudiante**, quiero un dashboard principal donde ver mis cursos, imágenes disponibles y reservas activas, para acceder a todo desde un solo lugar.
- [ ] Como **Docente o Estudiante**, quiero una interfaz de reserva de recursos con calendario visual, para elegir horario y equipo de forma intuitiva.
- [ ] Como **Estudiante**, quiero visualizar el catálogo de imágenes disponibles con su descripción y curso asociado, para elegir la correcta antes de descargarla.
- [ ] Como **Administrador**, quiero un panel de administración centralizado (usuarios, imágenes, hardware), para gestionar la plataforma sin cambiar de herramienta.
- [ ] Como **Estudiante**, quiero recibir notificaciones dentro de la plataforma (nuevas imágenes, cambios de horario, incidencias resueltas), para estar al tanto sin revisar múltiples canales.

**Criterios de Aceptación:**
- Dashboard responsivo y accesible desde navegador.
- Tiempos de carga aceptables con datos reales del backend.
- Consistencia visual entre los distintos paneles (estudiante/docente/admin).

---

### Épica 6: Arquitectura e Infraestructura Base
**Prioridad:** Alta (Must Have - fundacional)
**Descripción:** Establecer la infraestructura híbrida (on-premise + nube) sobre la que corren todos los demás componentes.

#### Historias de Usuario

- [ ] Como **DevOps / Platform Engineer**, quiero configurar Proxmox y Kubernetes como base de la infraestructura on-premise, para alojar los servicios de la plataforma de forma escalable.
- [ ] Como **DevOps / Platform Engineer**, quiero integrar GitLab con Harbor mediante pipelines de CI/CD, para automatizar la construcción y publicación de imágenes.
- [ ] Como **Tech Lead**, quiero definir la configuración híbrida (componentes locales vs. en nube), para balancear costos, rendimiento y disponibilidad.
- [ ] Como **DevOps**, quiero automatizar el aprovisionamiento de infraestructura (Ansible/Terraform), para reducir errores manuales y acelerar despliegues futuros.

**Criterios de Aceptación:**
- Clúster Kubernetes operativo sobre Proxmox.
- Pipeline CI/CD GitLab → Harbor funcional de punta a punta.
- Infraestructura documentada y reproducible vía código (IaC).

---

### Épica 7: Seguridad y Cumplimiento de Imágenes
**Prioridad:** Alta (Must Have)
**Descripción:** Garantizar que toda imagen publicada en el catálogo cumpla con estándares de seguridad e integridad antes de estar disponible para su uso.

#### Historias de Usuario

- [ ] Como **Security Engineer**, quiero que cada imagen subida al Registry pase por un escaneo automático de vulnerabilidades (Trivy) dentro del pipeline de CI/CD, para evitar publicar software inseguro sin intervención manual.
- [ ] Como **Administrador de Plataforma**, quiero que las imágenes aprobadas queden firmadas digitalmente, para garantizar su integridad y origen ante cualquier modificación posterior.
- [ ] Como **Security Engineer**, quiero definir umbrales de severidad de vulnerabilidades que bloqueen automáticamente la publicación de una imagen, para no depender de una revisión manual en cada caso.
- [ ] Como **Administrador**, quiero un registro de auditoría de qué imágenes fueron aprobadas, por quién y cuándo, para tener trazabilidad completa ante una revisión de cumplimiento.

**Criterios de Aceptación:**
- Escaneo y firma integrados como paso obligatorio del pipeline (no opcional).
- Reporte de vulnerabilidades accesible para el responsable de aprobación.
- Historial de auditoría consultable por imagen.

---

### Épica 8: Reportería y Analítica de Uso
**Prioridad:** Should Have
**Descripción:** Proveer indicadores y reportes de uso de la plataforma para apoyar la toma de decisiones académicas y operativas.

#### Historias de Usuario

- [ ] Como **Jefe de Laboratorio**, quiero un reporte periódico de uso de imágenes por curso, para identificar qué asignaturas requieren más recursos.
- [ ] Como **Docente**, quiero ver estadísticas de qué estudiantes descargaron y usaron la imagen de mi curso, para dar seguimiento al avance práctico del grupo.
- [ ] Como **Administrador**, quiero exportar reportes de uso de hardware e imágenes en formato descargable (CSV/PDF), para incluirlos en informes institucionales.
- [ ] Como **Chapter Lead / Profesor**, quiero indicadores agregados del laboratorio (ocupación, incidencias, imágenes más usadas), para justificar decisiones de inversión en infraestructura.

**Criterios de Aceptación:**
- Reportes generados a partir de datos reales de las demás épicas (no simulados).
- Exportación funcional en al menos un formato descargable.
- Frecuencia de actualización de datos definida (diaria o en tiempo real, a decidir en refinamiento).

---

## Priorización MoSCoW

**Must Have (Fase 1 - Universitario):**
- Épica 1 (Organización y Procesos)
- Épica 2 (Usuarios y Permisos)
- Épica 3 (Imágenes - MVP)
- Épica 4 (Gestión básica de Hardware)
- Épica 6 (Infraestructura base)
- Épica 7 (Seguridad y Cumplimiento de Imágenes)

**Should Have:**
- Épica 5 (Dashboards y reportes)
- Épica 8 (Reportería y Analítica de Uso)
- Descarga de imágenes para uso local

**Could Have:**
- Automatizaciones avanzadas
- Integración con SIEM / Compliance (Fase 2)
