# Indicadores

| Documento | Indicadores |
|-----------|-------------|
| **Proyecto** | Fliipa |
| **Versión** | 2.0|
| **Estado** | Borrador para validación |
| **Responsable** | Negocio y operaciones |
| **Última actualización** | 2026-07-14 |

---

## Control de versiones

| Versión | Fecha | Autor | Descripción |
|---------|-------|-------|-------------|
| 0.1 – 1.1 | 2026-07-06 a 2026-07-14 | María Fernanda Herazo  | Historial completo en el `indicadores.md` original (monolítico): primera versión de los indicadores de negocio y corrección posterior tras el Weekly Sync de Producto (10 jul 2026), que agregó la clasificación por horizonte (MVP, Evolución, Largo plazo). |
| 2.0 | 2026-07-14 | María Fernanda Herazo | Reorganización: un archivo por categoría de indicador, siguiendo el mismo formato usado en [Actores](../Actores/README.md) y [Procesos](../procesos/README.md). Se agregan diagramas Mermaid: horizonte de indicadores, embudo comercial y flujo de buckets de cartera. |

---

## Objetivo

Definir los indicadores clave (KPIs) que permiten medir el desempeño comercial, de riesgo, de cartera y de servicio del negocio Fliipa, para apoyar la toma de decisiones del Comité de Cartera, del equipo comercial y del negocio en general.

## Alcance

Este documento cubre indicadores comerciales, de originación y riesgo, de cartera y cobranza, de uso del producto, de servicio al cliente, y financieros/de negocio. No define las metas de negocio de más alto nivel (ver [Objetivo del Producto](../../producto/objetivo.md)) ni las reglas que determinan cada estado de mora (ver [Reglas Negocio](../reglas-negocio.md)).

## Diagrama: indicadores por horizonte

Siguiendo lo acordado en el Weekly Sync de Producto (10 jul 2026), las categorías de indicadores se ubican en tres horizontes, para no duplicar objetivos entre etapas:

```mermaid
flowchart LR
    subgraph MVP["MVP (piloto)"]
        C1["Comerciales y captación"]
        C2["Originación y riesgo"]
        C3["Uso del producto"]
    end
    subgraph EVOL["Evolución"]
        C4["Cartera y cobranza"]
        C5["Servicio al cliente"]
    end
    subgraph LARGO["Largo plazo"]
        C6["Financieros y de negocio"]
    end
    MVP --> EVOL --> LARGO
```

## Categorías de indicadores

| # | Categoría | Horizonte | Resumen | Documento |
|---|-----------|-----------|---------|-----------|
| 1 | Comerciales y de captación | MVP | Tasa de respuesta por canal, conversión, clientes activados en el piloto (300 tenderos), seguimiento a primera compra. | [01-comerciales-captacion.md](01-comerciales-captacion.md) |
| 2 | Originación y riesgo | MVP | SLA de aprobación (72h), tasa de aprobación/rechazo, casos de biometría en revisión, duración del onboarding. | [02-originacion-riesgo.md](02-originacion-riesgo.md) |
| 3 | Cartera y cobranza | Evolución | Distribución por bucket, PAR, tasa de recuperación, castigo de cartera, casos priorizados por el Comité de Cartera. | [03-cartera-cobranza.md](03-cartera-cobranza.md) |
| 4 | Uso del producto | MVP | % de uso del cupo, tiempo al primer uso, tasa de renovación, ticket promedio. | [04-uso-producto.md](04-uso-producto.md) |
| 5 | Servicio al cliente | Evolución | % resuelto por IA, tiempo de resolución, NPS/CSAT, SLA de PQR. | [05-servicio-cliente.md](05-servicio-cliente.md) |
| 6 | Financieros y de negocio | Largo plazo | Costo de fondeo (GMF 4x1000), sostenibilidad financiera, información crediticia generada. | [06-financieros-negocio.md](06-financieros-negocio.md) |
| — | Pendientes | — | Metas numéricas y periodicidad de reporte todavía por definir. | [07-pendientes.md](07-pendientes.md) |

## Documentos relacionados

- [Negocio](../README.md)
- [Flipa - Biblioteca de Conocimiento](../../README.md)
- [Mapa Del Conocimiento](../../MAPA_DEL_CONOCIMIENTO.md)
- [Onboarding](../../ONBOARDING.md)
- [Convenciones](../../CONVENCIONES.md)
- [Producto](../../producto/README.md)
- [Funcional](../../funcional/README.md)
- [Qa](../../qa/README.md)
- [Descripcion Negocio](../descripcion_negocio/README.md)
- [Actores](../Actores/README.md)
- [Procesos](../procesos/README.md)
- [Reglas Negocio](../reglas-negocio.md)

## Fuentes consultadas

- Objetivo del Producto (`producto/objetivo.md`)
- Alcance del Producto (`producto/alcance.md`)
- Modelo Comercial B2B — *Modelo Comercial B2B.pptx*
- Modelo y Proceso de Cobranza B2B — *Modelo Cobranza/Modelo_de_Cobranza_B2B_.pptx* y *Modelo Cobranza/Modelo y gestion de cobranza.docx*
- Reglas Negocio (`negocio/reglas-negocio.md`)
- Journeys Colpatria B2B, junio 2026 — *Journeys Fran finales-1.pdf*
- Notas de la reunión "Producto: Weekly Sync" (10 jul 2026) y su transcripción asociada
