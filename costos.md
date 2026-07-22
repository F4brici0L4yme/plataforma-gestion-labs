# Estimación de Costos Iniciales

Documento de referencia para la Fase 1 (Proyecto Universitario). Los valores están tomados de precios públicos vigentes a julio de 2026. No es una cotización cerrada, es una base para discutir presupuesto.

Nota importante: las secciones marcadas como `[pendiente]` dependen de datos que aún no están disponibles (arquitectura detallada de Persona B y plan de dedicación de Persona D). En cuanto entreguen, se completan las filas vacías.

---

## 1. Costos de infraestructura (mensual)

| Componente | Función en el proyecto | Proveedor de referencia | Costo estimado | Fuente |
|---|---|---|---|---|
| VPS básico (2 vCPU, 4-8 GB RAM) | Nodo de control K3s / pruebas | Digital Ocean | 32 USD | https://cloud.digitalocean.com/droplets/ |
| VPS intermedio (dedicado, 2 vCPU, 8 GB RAM) | Nodo worker adicional si se necesita más carga | Digital Ocean | 76 USD | https://cloud.digitalocean.com/droplets/ |
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

Los datos de dedicación provienen de la planificación detallada de la Persona D en `docs/plan-dedicacion.md`. Se calcula en base a **16 semanas** de duración para la Fase 1.

| Squad | Horas/semana | Semanas (Fase 1) | Horas totales | Costo referencial/hora | Subtotal |
|---|---|---|---|---|---|
| Core Platform | 75 | 16 | 1,200 | 5 USD | 6,000 USD |
| Image & Container Management | 75 | 16 | 1,200 | 5 USD | 6,000 USD |
| Hardware & Lab Operations | 75 | 16 | 1,200 | 5 USD | 6,000 USD |
| Frontend & User Experience | 75 | 16 | 1,200 | 5 USD | 6,000 USD |
| **Total de Esfuerzo (Fase 1)** | **300** | **16** | **4,800** | **5 USD** | **24,000 USD** |

*Nota:* Para este proyecto de carácter estrictamente académico, el costo real por hora de los estudiantes es de **0 USD (trabajo de curso)**. No obstante, se mantiene el valor referencial de mercado junior de **5 USD/hora** con el fin de dimensionar y valorizar adecuadamente el esfuerzo y costo humano si el proyecto fuera contratado externamente.

---

## 3. Costos de infraestructura física (si no existe hardware previo)

*Nota de arquitectura (basado en diagramas C4 de Persona B):* Para albergar los servicios locales descritos (Proxmox VE que aloja GitLab, Harbor, Keycloak, PostgreSQL, MinIO y nodos de K3s/Talos), se propone la siguiente infraestructura física de referencia en caso de no contar con equipos disponibles en los laboratorios de la universidad.

| Ítem | Especificación Sugerida | Referencia de mercado | Notas |
|---|---|---|---|
| Servidor físico para Proxmox | Min. 8 Cores / 16 Hilos, 64 GB RAM DDR4, 2TB SSD NVMe | ~1,200 USD | Costo de adquisición único (CAPEX) |
| Switch Administrable de Red | Gigabit Ethernet, 24 puertos | ~150 USD | Costo único |
| **Total Hardware Físico** | | **~1,350 USD** | Solo si la universidad no tiene hardware libre |

---

## 4. Resumen

| Concepto | Estimado |
|---|---|
| Infraestructura mensual (mínimo, on-prem existente) | 0-20 USD/mes |
| Infraestructura mensual (con respaldo en nube) | 20-40 USD/mes |
| Dominio (anual) | 7-18 USD/año |
| Licencias de software | 0 USD (todo open source) |
| Horas-persona (Académico) | **0 USD** |
| Horas-persona (Valor referencial de esfuerzo) | **24,000 USD** |
| Hardware físico (si no existe previo, costo único) | **1,350 USD** |

**Total estimado Fase 1 (enfoque académico con hardware existente):** aprox. 30-60 USD para los primeros 1-2 meses (dominio + margen de nube de respaldo).


---

## 5. Notas metodológicas

Todos los componentes de software elegidos en la arquitectura (GitLab, Harbor, Keycloak, PostgreSQL, MinIO) tienen edición Community gratuita, así que el costo real del proyecto está en infraestructura (mínimo si se usa hardware ya existente de la universidad) y en horas-persona.

Los precios de VPS son volátiles: varios proveedores subieron precios durante 2026 por escasez de RAM y SSD en el mercado. Conviene reconfirmar el precio exacto antes de aprobar presupuesto final.

Valores en USD salvo que se indique lo contrario. Conversión EUR-USD aproximada al momento de la consulta.

Este documento es una estimación con fines académicos, no una cotización formal de proveedores.

  <img width="631" height="652" alt="image" src="https://github.com/user-attachments/assets/d95d306c-db26-4342-a9a9-dcbb8059051d" />


m<img width="664" height="659" alt="image" src="https://github.com/user-attachments/assets/7640419f-347c-4327-86ca-423a61427b1c" />
