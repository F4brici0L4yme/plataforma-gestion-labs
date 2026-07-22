# Procesos y Organización del Laboratorio

**Documento Integral de Organización y Métodos**  
**Proyecto:** Plataforma Híbrida de Gestión de Laboratorios  
**Asignatura:** Organización y Métodos  
**Versión:** 1.0  
**Fecha:** Julio 2026

---

## 1. Introducción

Este documento presenta la **organización completa** y los **procesos clave** del laboratorio de computación. Su propósito es estandarizar el funcionamiento, reducir tiempos improductivos, garantizar trazabilidad y servir como referencia para la asignatura de **Organización y Métodos**.

Se incluyen descripciones detalladas, diagramas BPMN textuales, matriz RACI, indicadores y propuestas de mejora.

---

## 2. Estructura Organizacional Mínima

### Roles Principales

- **Director de Escuela / Departamento**: Máxima autoridad académica. Autoriza el uso completo del laboratorio para asignaturas o proyectos de investigación, y resuelve conflictos de prioridad entre solicitudes de docentes.
- **Administrador de Laboratorio**: Responsable general de la operación física y digital.
- **Responsable de Imágenes**: Gestor del catálogo de contenedores (Docker).
- **Chapter de Organización y Procesos**: Profesor líder (encargado de definir, documentar y mejorar procesos).
- **Docente / Product Owner**: Solicita y valida recursos por curso/proyecto.
- **Estudiante / Desarrollador**: Usuario final.
- **Chapter Leads Técnicos**: Profesores por especialidad (DevOps, Seguridad, etc.).

### Propuesta de Organización

Se recomienda un **Chapter de Organización y Procesos** (transversal) en lugar de un squad completo. Este Chapter trabajará junto con un **Rol de "Process Owner"** dentro de cada Squad técnico.

**Justificación**: Permite mantener los squads enfocados en desarrollo mientras se garantiza que los procesos sean prácticos y bien documentados.

---

## 3. Procesos Principales (con Descripción Detallada)

### 3.1 Proceso: Solicitud y Asignación de Recursos de Hardware

**Objetivo:** Gestionar de forma eficiente las computadoras, servidores e impresoras.

**Flujo BPMN (Textual):**

Start → Solicitud por Portal → Verificación Automática de Disponibilidad 
→ ¿Disponible? 
   → Sí → Aprobación Automática / Manual → Asignación + Notificación → Check-in (QR) → Uso → Check-out → Liberación → End
   → No → Notificación de Espera → Cola de Prioridad → Revisión Manual



**Descripción Detallada:**
1. El usuario inicia sesión y selecciona el recurso.
2. El sistema verifica disponibilidad en tiempo real.
3. Se registra el préstamo con fecha/hora de devolución.
4. Al llegar al laboratorio se realiza Check-in.

---

### 3.2 Proceso: Gestión del Catálogo de Imágenes de Contenedores (Core)

**Objetivo:** Proporcionar entornos estandarizados y trazables.

**Flujo BPMN (Textual):**

Start → Solicitud de Imagen (Estudiante/Docente)
→ Búsqueda Automática en Harbor
→ ¿Imagen Disponible y Actualizada?
   → Sí → Entrega de Enlace de Descarga → Uso Local / Laboratorio → End
   → No → Notificación al Responsable de Imágenes
      → Análisis (Oficial vs Crear)
      → Descarga / Creación de Imagen
      → Escaneo de Vulnerabilidades
      → Firma Digital
      → Aprobación
      → Publicación en Harbor
      → Notificación a Solicitante



**Descripción Detallada:**
- Toda imagen debe estar **escaneada y firmada**.
- Los estudiantes pueden descargar la imagen oficial y ejecutarla en su computadora personal con Docker o Podman.
- Se mantiene un historial completo de versiones.

---

### 3.3 Proceso: Actualización y Mantenimiento de Imágenes

**Flujo BPMN:**

Start → Detección Automática de Nueva Versión
→ Pipeline de Rebuild
→ Escaneo de Seguridad
→ ¿Requiere Aprobación Manual?
   → Sí → Revisión por Responsable → Aprobación/Rechazo
   → No → Actualización Automática
→ Publicación → Notificación a Usuarios Activos → End



---

### 3.4 Proceso: Reserva y Uso de Laboratorio (Individual)

**Flujo BPMN:**

Start → Login → Seleccionar Horario y Equipo
→ Validación de Disponibilidad
→ Reserva Confirmada → Recordatorio 15 min antes
→ Check-in en Laboratorio → Uso → Check-out → Liberación Automática

---

### 3.5 Proceso: Separación y Asignación de Horarios de Laboratorio por Curso o Proyecto

**Objetivo:** Reservar y asignar el uso exclusivo de un laboratorio completo de computación para el dictado de una asignatura regular o la ejecución de un proyecto de investigación/desarrollo institucional de mediano o largo plazo.

**Flujo BPMN (Textual):**

Start → Solicitud de Reserva de Laboratorio Completo (Docente/Product Owner)
→ Evaluación de Disponibilidad y Prioridad del Plan de Estudios (Director)
→ ¿Aprobación del Director?
   → No → Notificación de Rechazo al Docente → Fin
   → Sí → Asignación Recurrente del Laboratorio completo (Administrador)
      → Registro y Bloqueo de Horarios del Laboratorio en el Sistema
      → Notificación a Docentes y Alumnos
      → Preparación de Imágenes de Contenedores Requeridas (Responsable de Imágenes)
      → Dictado de Clases / Uso por Proyecto
      → Fin de Semestre / Culminación del Proyecto
      → Liberación Automática del Laboratorio en el Sistema → End

**Descripción Detallada:**
1. **Solicitud**: El Docente inicia la solicitud formal indicando el laboratorio requerido, horarios, cupos y lista de imágenes de contenedores/software necesarios.
2. **Evaluación**: El Director de Escuela aprueba basándose en la prioridad del plan de estudios y la optimización de los espacios físicos disponibles.
3. **Configuración**: El Administrador de Laboratorio bloquea la reserva individual en el sistema durante esos bloques horarios recurrentes.
4. **Habilitación de Entornos**: El Responsable de Imágenes asegura que las imágenes solicitadas estén testeadas y publicadas en Harbor antes de iniciar el curso.

---

## 4. Matriz RACI General

| Actividad / Proceso | Administrador Lab | Responsable Imágenes | Docente | Estudiante | Director | Chapter Organización |
|---|---|---|---|---|---|---|
| Solicitud de Recursos Hardware | A | I | C | R | I | C |
| Solicitud y Aprobación de Imágenes | A | R | C | R | I | C |
| Creación de Nueva Imagen | C | R/A | C | I | I | C |
| Reserva de Equipos (Individual) | A | I | C | R | I | I |
| Separación de Horarios por Curso/Proyecto | R | I | C | I | A | C |
| Actualización de Imágenes | I | R | C | I | I | C |
| Definición y Mejora de Procesos | C | C | C | I | C | R/A |

---

## 5. Indicadores de Desempeño (KPIs)

- Tiempo promedio de aprobación de nueva imagen: **≤ 48 horas**
- Porcentaje de solicitudes resueltas automáticamente: **≥ 70%**
- Tiempo promedio de configuración de entorno por estudiante: **≤ 15 minutos**
- Tasa de utilización de imágenes oficiales: **≥ 75%**
- Nivel de satisfacción de usuarios (Encuesta): **≥ 85%**
- Tiempo promedio de reserva de equipo: **≤ 5 minutos**

---

## 6. Mejora Continua y Recomendaciones

- Realizar **revisiones mensuales** de procesos con el Chapter de Organización.
- Utilizar herramientas como **Draw.io, Bizagi o Camunda** para mantener diagramas BPMN actualizados.
- Implementar **automatización progresiva** de decisiones mediante reglas de negocio.
- Crear un **manual de usuario** y **guías rápidas** para estudiantes.
- Establecer un **comité de procesos** (Administrador + Chapter Leads + Estudiantes representantes).

**Próximos Pasos:**
1. Modelar todos los diagramas BPMN en herramienta gráfica.
2. Validación del documento con docentes y administradores.
3. Integración de flujos automatizados en la plataforma.

---

**Este documento integra toda la parte de Organización y Procesos del Laboratorio.**  
Está diseñado para ser entregado como **trabajo de curso de Organización y Métodos**.

---

¿Deseas que agregue más procesos (ej. Gestión de Incidentes, Onboarding de Nuevos Usuarios, Cierre de Semestre, etc.) o que prepare una versión con PlantUML para generar diagramas reales?

