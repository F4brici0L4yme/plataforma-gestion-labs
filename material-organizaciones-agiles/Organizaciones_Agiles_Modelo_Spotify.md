---
marp: true
title: Organizaciones Ágiles para Problemas Complejos
paginate: true
---

# Organizaciones Ágiles para Problemas Complejos

**El Modelo Spotify aplicado a un caso real: la Plataforma Híbrida de Gestión de Laboratorios de Computación**

Curso de Organización y Métodos · Julio 2026

---

## Agenda de la sesión

**Del problema complejo al diseño organizacional**

1. **Fundamentos** — Problemas complejos, VUCA y el marco Cynefin: por qué la jerarquía tradicional no basta.
2. **Modelo Spotify** — Squads, Tribes, Chapters y Guilds: cómo equilibrar autonomía con alineación.
3. **Caso aplicado** — La Plataforma Híbrida de Gestión de Laboratorios: el modelo puesto en práctica.
4. **Discusión** — Lecciones, conclusiones y preguntas para trabajar en clase.

---

# Parte 1
## Fundamentos: organizarse frente a la complejidad

*VUCA, el marco Cynefin y los límites de la jerarquía tradicional*

---

## Organización y Métodos, revisitada

Durante décadas, Organización y Métodos (O&M) diseñó estructuras a partir de organigramas jerárquicos y manuales de procedimiento estáticos: una separación clara entre quien planifica y quien ejecuta.

Ese enfoque funciona cuando el problema es estable y repetitivo. Pero muchos proyectos actuales —como una plataforma tecnológica— enfrentan requisitos que emergen sobre la marcha y múltiples interesados con intereses distintos.

> **Pregunta que guía esta sesión:** ¿Qué estructura organizacional diseñamos cuando el problema es complejo, cambiante y multidisciplinario — y no simplemente "complicado"?

---

## El entorno VUCA

La mayoría de los proyectos tecnológicos actuales se desenvuelven en un entorno VUCA:

- **V — Volatilidad:** el cambio es rápido y difícil de anticipar.
- **U — Incertidumbre:** falta información para predecir resultados.
- **C — Complejidad:** múltiples variables interconectadas.
- **A — Ambigüedad:** las relaciones causa-efecto no son claras.

---

## El marco Cynefin: cuatro tipos de problema

| Dominio | Descripción | Ejemplo |
|---|---|---|
| **Simple (claro)** | Causa-efecto evidente. Se resuelve con procedimientos y buenas prácticas. | Check-in de un equipo en inventario. |
| **Complicado** | Requiere experticia, pero es analizable de antemano. | Configurar un clúster de Kubernetes. |
| **Complejo** | La causa-efecto solo se entiende en retrospectiva. Requiere probar–sentir–responder. | Diseñar un catálogo de imágenes para públicos distintos. |
| **Caótico** | No hay relación causa-efecto discernible; se debe actuar primero para estabilizar. | Caída total del laboratorio en plena evaluación. |

---

## Los problemas complejos no se resuelven planificando más

> "Los problemas complejos no se resuelven con más planificación anticipada, sino con estructuras que permiten experimentar rápido, aprender del error y ajustar el rumbo con frecuencia."

- Una jerarquía clásica es eficiente para lo simple y lo complicado: procedimientos claros, aprobación en cascada.
- Frente a lo complejo se vuelve lenta y frágil: cada cambio de requisito atraviesa varios niveles de aprobación.
- El conocimiento queda fragmentado entre silos que no se comunican con fluidez entre sí.

---

## Organización jerárquica vs. organización ágil

| Organización jerárquica | Organización ágil (squads) |
|---|---|
| Decisiones suben y bajan por niveles de aprobación | Equipos autónomos deciden de punta a punta |
| Especialización rígida por departamento | Equipos multidisciplinarios por misión de producto |
| Planificación extensa antes de ejecutar | Ciclos cortos de prueba, observación y ajuste |
| Cambios de alcance lentos y costosos | Cambios de rumbo en días, no en meses |

---

## El equilibrio entre autonomía y alineación

El reto del diseño organizacional ágil: equipos con libertad para decidir cómo resolver un problema, sin perder el rumbo estratégico común.

| | Baja alineación | Alta alineación |
|---|---|---|
| **Alta autonomía** | Caos: duplicación, direcciones contradictorias | Squads con misión clara y libertad de ejecución |
| **Baja autonomía** | Desorganización total | Burocracia lenta, no se adapta a la complejidad |

---

# Parte 2
## El Modelo Spotify

*Squads, Tribes, Chapters y Guilds: la anatomía de una organización ágil escalada*

---

## Origen y filosofía

El Modelo Spotify es un patrón de diseño organizacional popularizado por la empresa Spotify (que aclara que evolucionó y nunca fue un modelo "cerrado") para escalar equipos ágiles manteniendo autonomía y alineación a la vez.

Se organiza en cuatro unidades complementarias, dos "verticales" (**Squad**, **Tribe**) y dos "horizontales" (**Chapter**, **Guild**), que forman una matriz de trabajo.

---

## Squad
### "Una mini-startup dentro de la organización"

Unidad básica: equipo pequeño, multidisciplinario (5–9 personas) y autónomo, con todas las competencias para diseñar, construir y entregar una parte del producto de principio a fin.

- Misión de producto clara y acotada
- Mínima dependencia de otros equipos
- Decide su propia forma de trabajo (Scrum, Kanban, híbrido)

---

## Tribe
### "La familia de squads con una misma visión"

Agrupa varios squads que trabajan en un área de producto relacionada. Coordina la visión general y evita que los squads dupliquen esfuerzos o pierdan coherencia entre sí.

- Alinea prioridades entre squads relacionados
- Gestiona dependencias técnicas compartidas
- Tiene un líder de tribu que facilita, no ordena

---

## Chapter
### "La misma disciplina, repartida en varios squads"

Agrupación transversal de personas que comparten una misma disciplina o especialidad, aunque trabajen en squads distintos. Garantiza estándares técnicos comunes y mentoría.

- Estandariza calidad técnica entre squads
- Desarrollo profesional y mentoría
- No decide el día a día del squad

---

## Guild
### "Comunidad de interés, abierta a todos"

Comunidad informal y voluntaria que cruza toda la organización, abierta a cualquier interesado en un tema, sin importar su squad, tribe o chapter.

- Comparte conocimiento de forma orgánica
- Participación voluntaria, sin jerarquía formal
- Ejemplos: guild de seguridad, guild de accesibilidad

---

## La matriz: vertical por Squad, horizontal por Chapter

Cada persona pertenece "verticalmente" a un squad (entrega valor día a día) y "horizontalmente" a un chapter (mantiene su desarrollo técnico).

| | Squad A | Squad B | Squad C | Squad D |
|---|---|---|---|---|
| **Backend** | 👤 | 👤 | 👤 | 👤 |
| **DevOps** | 👤 | 👤 | 👤 | 👤 |
| **Frontend** | 👤 | 👤 | 👤 | 👤 |

---

## Ventajas y riesgos del modelo

**Ventajas**
- Ciclos de decisión más cortos: probar, observar, ajustar
- Escala sin perder identidad de producto (tribes por área)
- Conocimiento técnico estandarizado vía chapters

**Riesgos si se aplica sin cuidado**
- Squads sin chapter fuerte pierden estándares comunes
- Exceso de autonomía sin alineación genera duplicación
- Requiere líderes de squad/tribe con habilidades de facilitación

---

# Parte 3
## El caso aplicado

*Plataforma Híbrida de Gestión de Laboratorios de Computación*

---

## El problema: laboratorios de cómputo fragmentados

- **Tiempo perdido:** instalaciones y configuraciones manuales repetidas.
- **Entornos inconsistentes:** "funciona en mi máquina" — falta de estandarización.
- **Sin trazabilidad:** no hay registro auditable del software utilizado.
- **Difícil de replicar:** el estudiante no puede llevar el entorno a su PC.

*Este dolor lo comparten laboratorios universitarios y empresas de software: gestión fragmentada de recursos físicos y digitales.*

---

## El objetivo del proyecto

Desarrollar una plataforma híbrida (local + nube) que estandarice, automatice y trace los entornos de los laboratorios de computación.

- **Catálogo de imágenes:** contenedores Docker con procesos automatizados vía Harbor.
- **Gestión de hardware y usuarios:** recursos físicos, proyectos/cursos y permisos centralizados.
- **Trazabilidad completa:** registro auditable de todo el software utilizado.
- **Dos versiones:** Académica y Empresarial, con estándares superiores.

---

## ¿Por qué es un problema complejo (y no solo complicado)?

- No existe una única arquitectura "correcta" de antemano: aula universitaria y empresa tienen necesidades distintas (presupuesto y rotación vs. seguridad y SLAs).
- Múltiples interesados con intereses distintos: estudiantes, docentes, administradores de TI y empresas.
- La tecnología base (contenedores, Kubernetes, identidad, seguridad) evoluciona constantemente.
- Los requisitos reales solo se conocen con el uso: se necesita pilotar, observar y adaptar el diseño.

> **Conclusión Cynefin:** el proyecto se ubica en el dominio **COMPLEJO** → requiere fases piloto, experimentación y ajuste, no un plan cerrado desde el inicio.

---

## El Tribe "Platform Lab"

El proyecto organiza a estudiantes y docentes bajo un único Tribe que evoluciona en dos fases secuenciales.

**Tribe: Platform Lab**

| Fase 1 — Proyecto Universitario | Fase 2 — Proyecto Empresa |
|---|---|
| 4 squads, formación de estudiantes bajo mentoría docente. | Evolución a 5 squads con estándares profesionales. |

---

## Squads — Fase 1: Proyecto Universitario

- Squad Core Platform
- Squad Image & Container Management
- Squad Hardware & Lab Operations
- Squad Frontend & User Experience

---

## Squads — Fase 2: Proyecto Empresa (evolución)

- Squad Core Enterprise Platform
- Squad Advanced Image & Security
- Squad Hardware Fleet & Hybrid Operations
- Squad Enterprise Experience & Analytics
- Squad Integration & Ecosystem

---

## Chapters liderados por docentes

Cada Chapter agrupa a los estudiantes por especialidad técnica, de forma transversal a los squads, y está liderado por un profesor con mínimo 5 años de experiencia en la industria.

- Chapter Backend & Arquitectura
- Chapter DevOps & Platform Engineering
- Chapter Security & Compliance
- Chapter Frontend & UX

*El liderazgo docente aporta mentoría real y estándares profesionales dentro de cada disciplina.*

---

## El dilema: ¿dónde va "Organización y Procesos"?

**¿Un squad dedicado solo a procesos?**
Se descartó: generaría un silo desconectado de la ejecución técnica y sería costoso en recursos.

**Solución adoptada**
- **Chapter de "Organización y Procesos"** — liderado por un docente con experiencia en Gestión de Proyectos o ITIL.
- **Process Owner en cada squad** — un miembro de cada squad, dedicado parcialmente a documentar los procesos de su propia área.

*Autonomía (cada squad es dueño de sus procesos) + Alineación (RACI y estándares comunes vía Chapter) — sin crear burocracia separada.*

---

## Cadencia ágil y artefactos del proyecto

- **Dedicación semanal:** 15–20 h/estudiante (Fase 1) · 20–25 h/estudiante (Fase 2)
- **Ritmo de coordinación:** 2 reuniones de squad/semana · 1 revisión con el Chapter/semana
- **Backlog MoSCoW:** épicas priorizadas — Organización, Usuarios, Imágenes, Hardware, Frontend
- **Fases:** Diseño → Universitario → Empresa → Piloto → Mejora continua

---

## Lecciones para el diseño organizacional

1. La estructura debe reflejar el tipo de problema: lo simple/complicado admite jerarquía; lo complejo requiere squads autónomos que aprendan iterando.
2. Agilidad organizacional no significa "sin estructura": los Chapters y la matriz RACI muestran una estructura distinta, orientada a autonomía con alineación.
3. Los dilemas organizacionales rara vez se resuelven creando más unidades separadas: a menudo la respuesta es un rol transversal + responsabilidad distribuida.
4. Un mismo diseño (Tribe → Squads → Chapters) puede evolucionar de contexto académico a empresarial ajustando el número y enfoque de squads.

---

## Conclusiones

El caso de la Plataforma Híbrida de Gestión de Laboratorios muestra que O&M, aplicada a problemas complejos, no consiste en imponer un procedimiento fijo, sino en diseñar una estructura —el Modelo Spotify, en este ejemplo— que permita a equipos autónomos aprender, adaptarse y coordinarse con el resto de la organización.

*El valor pedagógico del caso está en observar cómo una decisión organizacional concreta —dónde ubicar el Chapter de Organización y Procesos— se deriva directamente de los principios de autonomía, alineación y del dominio "complejo" de Cynefin.*

---

## Preguntas de discusión

1. ¿Qué otros procesos del laboratorio son "complicados" (procedimiento claro) frente a los "complejos" (requieren experimentación)?

```diff
- Joaquin: Procesos como configurar una maquina virtual e instalar software específico para poder empezar a trabajar.
```

```diff
+ Sandra: En mi opinión, la instalación inicial de sistemas operativos o la renovación de licencias comerciales son procesos complicados pero predecibles. Por el contrario, gestionar la concurrencia y la asignación dinámica de laboratorios ante imprevistos es un proceso complejo que requiere monitoreo y adaptación constante.
```

2. Si el proyecto creciera a 10 squads, ¿en qué punto convendría dividir el Tribe "Platform Lab" en dos tribes independientes?

```diff
- Joaquin: Cuando los squads tengan problemas de coordinación y sea necesarios dividirlos para que trabajen de mejor manera.
```

```diff
+ Sandra: Desde mi perspectiva, dividiría la tribu en el momento en que los squads se especialicen en áreas funcionales distintas (por ejemplo, dividiendo un frente puramente de infraestructura y otro de experiencia de usuario), para evitar reuniones eternas y mantener la agilidad de los equipos.
```

3. ¿Qué riesgos aparecen si el Process Owner de cada squad no tiene tiempo protegido para documentar procesos?

```diff
- Joaquin: Se necesita ese tiempo para poder documentar de forma correcta el proyecto y así otros desarrolladores puedan seguir escalando el proyecto sin problemas.
```

```diff
+ Sandra: Considero que el mayor riesgo es que la documentación se convierta en una tarea secundaria y desactualizada. Sin un tiempo protegido para documentar, el conocimiento se quedará en las personas y no en la organización, generando cuellos de botella al incorporar nuevos integrantes.
```

4. ¿Cómo mediría, con indicadores concretos, si el modelo logra el equilibrio entre autonomía y alineación?

```diff
- Joaquin: Tomaria en cuenta los resultados de los proyectos sin aprobación y para la alineación mediria el cumplimiento de los objetivos de cada squad y el resultado de cada integrante del squad.
```

```diff
+ Sandra: Yo mediría la autonomía con el porcentaje de decisiones técnicas resueltas por el propio squad sin necesidad de escalamiento. La alineación la evaluaría mediante la tasa de cumplimiento de los estándares de seguridad y licencias definidos por el chapter en Harbor.
```

