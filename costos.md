# Estimación de Costos Iniciales

Documento de referencia para la Fase 1 (Proyecto Universitario). Los valores están tomados de precios públicos vigentes a julio de 2026. No es una cotización cerrada, es una base para discutir presupuesto.

Nota importante: las secciones marcadas como `[pendiente]` dependen de datos que aún no están disponibles (arquitectura detallada de Persona B y plan de dedicación de Persona D). En cuanto entreguen, se completan las filas vacías.

---

## 1. Costos de infraestructura (mensual)

| Componente | Función en el proyecto | Proveedor de referencia | Costo estimado | Fuente |
|---|---|---|---|---|
| VPS básico (2 vCPU, 4-8 GB RAM) | Nodo de control K3s / pruebas | Hetzner CX23 | desde 5,49 EUR/mes (~6 USD) | Hetzner Cloud, precios julio 2026 |
| VPS intermedio (dedicado, 2 vCPU, 8 GB RAM) | Nodo worker adicional si se necesita más carga | Hetzner CCX13 | ~15 EUR/mes (~16 USD) | Hetzner Cloud, precios julio 2026 |
| Servidor on-prem (Proxmox) | Host principal del laboratorio (GitLab, Harbor, Keycloak, PostgreSQL, MinIO) | Hardware propio de la universidad | 0 USD si ya existe el equipo; en caso contrario, costo de adquisición aparte (fuera de este presupuesto mensual) | Asumido, pendiente de confirmar con Persona B |
| Dominio (.com) | URL pública de la plataforma | Namecheap | ~7-11 USD primer año, ~15-18 USD renovación anual | Namecheap, precios julio 2026 |
| Certificado SSL | HTTPS para todos los servicios | Let's Encrypt | 0 USD (gratuito y automatizable) | Estándar de la industria |
| GitLab (self-hosted, edición Community) | Repositorios y CI/CD | Open source | 0 USD | Licencia GitLab CE |
| Harbor | Registro de imágenes de contenedores | Open source | 0 USD | Proyecto CNCF |
| Keycloak | Gestión de identidad y accesos | Open source | 0 USD | Proyecto Red Hat / CNCF |
| PostgreSQL | Base de datos | Open source | 0 USD | - |
| MinIO | Almacenamiento de objetos | Open source (edición Community) | 0 USD | - |

**Subtotal infraestructura mensual (escenario mínimo, todo self-hosted en hardware existente):** aprox. 0-20 USD/mes (solo dominio prorrateado + SSL gratis).

**Subtotal infraestructura mensual (escenario con nube de respaldo, 1-2 VPS adicionales):** aprox. 20-40 USD/mes.

---

## 2. Costos de horas-persona

`[pendiente de Persona D — plan de dedicación semanal por squad]`

| Squad | Horas/semana | Semanas (Fase 1) | Horas totales | Costo referencial/hora | Subtotal |
|---|---|---|---|---|---|
| Core Platform | | | | | |
| Image & Container Management | | | | | |
| Hardware & Lab Operations | | | | | |
| Frontend & User Experience | | | | | |

Nota: para un proyecto académico, el costo por hora puede dejarse en 0 (trabajo estudiantil) o usarse un valor referencial de mercado junior (ej. 4-8 USD/hora) solo para dimensionar el "valor" del esfuerzo si el profesor lo pide.

---

## 3. Costos de infraestructura física (si no existe hardware previo)

`[pendiente de Persona B — diagrama de arquitectura C4, para saber cuántos nodos y qué capacidad se necesita]`

| Ítem | Referencia de mercado | Notas |
|---|---|---|
| Servidor físico para Proxmox | Depende de specs, referencia de mercado desde ~500-1500 USD el equipo | Costo único, no mensual |
| Switch/red de laboratorio | Ya existente en la mayoría de universidades | 0 USD asumido |

---

## 4. Resumen

| Concepto | Estimado |
|---|---|
| Infraestructura mensual (mínimo, on-prem existente) | 0-20 USD/mes |
| Infraestructura mensual (con respaldo en nube) | 20-40 USD/mes |
| Dominio (anual) | 7-18 USD/año |
| Licencias de software | 0 USD (todo open source) |
| Horas-persona | `[pendiente]` |
| Hardware físico (si aplica, costo único) | `[pendiente]` |

**Total estimado Fase 1 (sin contar hardware físico ni horas-persona):** aprox. 30-60 USD para los primeros 1-2 meses, considerando dominio + margen de nube de respaldo.

---

## 5. Notas metodológicas

Todos los componentes de software elegidos en la arquitectura (GitLab, Harbor, Keycloak, PostgreSQL, MinIO) tienen edición Community gratuita, así que el costo real del proyecto está en infraestructura (mínimo si se usa hardware ya existente de la universidad) y en horas-persona.

Los precios de VPS son volátiles: varios proveedores subieron precios durante 2026 por escasez de RAM y SSD en el mercado. Conviene reconfirmar el precio exacto antes de aprobar presupuesto final.

Valores en USD salvo que se indique lo contrario. Conversión EUR-USD aproximada al momento de la consulta.

Este documento es una estimación con fines académicos, no una cotización formal de proveedores.
