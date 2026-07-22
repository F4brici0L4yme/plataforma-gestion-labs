# Backlog Inicial del Proyecto

**Proyecto:** Plataforma Híbrida de Gestión de Laboratorios de Computación  
**Estado:** Versión Inicial (Priorizado)  
**Fecha:** Julio 2026

---

## Épicas Principales

### Épica 1: Gestión Organizacional y Procesos del Laboratorio
**Prioridad:** Alta (Fundacional)  
**Descripción:** Definir, documentar e implementar la organización mínima requerida para el uso efectivo de la plataforma, incluyendo roles, procesos y flujos de trabajo.

#### Historias de Usuario

- [ ] Como **Administrador**, quiero definir roles y permisos claros para que cada usuario sepa sus responsabilidades.
- [ ] Como **Product Owner / Docente**, quiero un catálogo de procesos estandarizados del laboratorio (reserva de equipos, solicitud de imágenes, etc.).
- [ ] Como **Responsable**, quiero un flujo claro de aprobación y gestión de imágenes de contenedores.
- [ ] Como **Estudiante**, quiero conocer el proceso para solicitar recursos y obtener imágenes para mi computadora personal.
- [ ] Como **Jefe de Laboratorio**, quiero dashboards que muestren el estado de uso de los recursos físicos y virtuales.
- [ ] Como **Equipo**, quiero una matriz RACI clara para todos los procesos críticos.

<span style="color:red">**[Comentario]:** A favor de esta épica como base fundacional. Sin embargo, varias historias (2ª, 3ª, 4ª, 5ª, 6ª) no siguen el formato completo Como/quiero/**para**, les falta el beneficio explícito. Se puede completar sin perder la intención original.</span>

**Criterios de Aceptación:**
- Documentación oficial de procesos (en Markdown y versión PDF).
- Matriz RACI implementada.
- Flujos automatizados donde sea posible.

<span style="color:red">**[Comentario]:** En contra de mezclar aquí procesos internos del equipo (matriz RACI, roles del squad) con procesos que usará el usuario final (reserva de equipos, solicitud de imágenes). Son dos audiencias distintas y podría dividirse en dos épicas o dejar la RACI fuera del backlog de producto.</span

---

### Épica 2: Gestión de Usuarios, Proyectos/Cursos y Permisos

- [ ] Sistema de autenticación centralizado (Keycloak).
- [ ] Gestión de Proyectos (Empresa) y Cursos (Universidad).
- [ ] Asignación de usuarios a proyectos/cursos.
- [ ] RBAC avanzado (Roles Based Access Control).

> 🔴 **[Comentario]:** En contra del formato actual: ninguno de estos 4 puntos es una historia de usuario, son features sueltas sin rol ni beneficio. Además falta prioridad y descripción, que sí tiene la Épica 1. También noto que no hay ninguna historia sobre distinguir el modo Académico vs. Empresarial.

---

### Épica 3: Catálogo de Imágenes de Contenedores

- [ ] Implementación de Harbor como Registry privado.
- [ ] Pipeline automatizado de escaneo y firma de imágenes.
- [ ] Interfaz para solicitar y aprobar imágenes.
- [ ] Descarga segura de imágenes para uso local (estudiantes).

> 🔴 **[Comentario]:** A favor del contenido (cubre bien el flujo: solicitud → escaneo → firma → descarga). En contra de mantener escaneo y firma como un ítem más de esta épica: dado que se define un rol de Security Engineer y estándares de seguridad superiores para la versión empresarial, creo que merece ser su propia épica en vez de quedar diluido aquí.

---

### Épica 4: Gestión de Hardware e Inventario

- [ ] Inventario automatizado de computadoras, servidores e impresoras.
- [ ] Sistema de reserva de equipos.
- [ ] Monitoreo del estado de los laboratorios.

> 🔴 **[Comentario]:** A favor del alcance. En contra de que falte una historia sobre gestión de incidencias/mantenimiento correctivo, consecuencia lógica de "monitorear el estado de los laboratorios": si detectas una falla, debe quedar registrada en algún lado.

---

### Épica 5: Frontend y Portal de Usuario

- [ ] Dashboard principal.
- [ ] Interfaz de reserva de recursos.
- [ ] Visualización de imágenes disponibles.

> 🔴 **[Comentario]:** En contra de lo escueto de esta épica en comparación con las demás: no tiene prioridad, descripción ni formato de historia. Además, no contempla un panel de administración centralizado para el Administrador, solo cubre las vistas de estudiante/docente.

---

### Épica 6: Arquitectura e Infraestructura Base

- [ ] Configuración de Proxmox + Kubernetes.
- [ ] Integración GitLab + Harbor.
- [ ] Configuración híbrida (local + nube).

> 🔴 **[Comentario - Persona C]:** A favor del contenido técnico, coincide con lo que se necesita (Proxmox, K3s/Talos, GitLab, Harbor). En contra de la falta total de formato de historia de usuario.

---

## Priorización MoSCoW

**Must Have (Fase 1 - Universitario):**
- Épica 1 (Organización y Procesos)
- Épica 2 (Usuarios y Permisos)
- Épica 3 (Imágenes - MVP)
- Épica 4 (Gestión básica de Hardware)

**Should Have:**
- Dashboards y reportes
- Descarga de imágenes para uso local

**Could Have:**
- Automatizaciones avanzadas
- Integración con SIEM / Compliance (Fase 2)

---

## Pregunta Estratégica: ¿Cómo estructurar la "Organización y Procesos"?

### Propuesta Recomendada

**Opción Elegida: Chapter de Organización + Rol Dedicado en Squads**

#### Razón de la Propuesta:

1. **No es conveniente crear un Squad completo** solo para procesos y organización, ya que sería muy costoso en recursos y podría generar silos.
2. **La mejor solución es un enfoque híbrido**:

   - **Chapter de "Organización y Procesos"** (liderado por un profesor con experiencia en Gestión de Proyectos o ITIL).
   - **Rol específico dentro de cada Squad**: **Process Owner** o **Organization Champion** (un miembro de cada squad dedicado parcialmente a definir y documentar procesos relacionados con su área).
   - **Equipo Transversal Temporal** (al inicio del proyecto) formado por:
     - 1 Profesor (Chapter Lead)
     - 1-2 Estudiantes Senior (con interés en Gestión)
     - El Product Owner General

#### Ventajas de esta aproximación:

- Mantiene los squads enfocados en desarrollo técnico.
- Garantiza que los procesos sean **realistas y practicados** por quienes los ejecutan.
- Permite evolución continua de los procesos (no se define todo al inicio).
- Facilita la adopción por parte de administradores y docentes.

**Responsabilidades del Chapter de Organización:**
- Definir la matriz RACI inicial.
- Documentar procesos clave (reserva, solicitud de imágenes, aprobación, etc.).
- Establecer indicadores de uso del laboratorio.
- Asegurar alineación entre la parte técnica y los procesos operativos.

---

## Próximos Pasos

1. Aprobar estructura organizacional propuesta.
2. Formar el Chapter de Organización.
3. Iniciar refinamiento del Backlog con los squads.
4. Definir Definition of Done (DoD) común.

---
