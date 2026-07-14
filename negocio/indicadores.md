# Indicadores

| Documento | Indicadores |
|-----------|-------------|
| **Proyecto** | Fliipa |
| **Versión** | 1.1 |
| **Estado** | Borrador para validación |
| **Responsable** | Negocio y operaciones |
| **Última actualización** | 2026-07-14 |

---

## Control de versiones

| Versión | Fecha | Autor | Descripción |
|---------|-------|-------|-------------|
| 0.1 | 2026-07-06 | Equipo Flipa | Borrador vacío (pendiente de completar). |
| 1.0 | 2026-07-09 | María Fernanda Herazo (con asistencia de Claude) | Primera versión completa de los indicadores de negocio, construida a partir del Objetivo del Producto, el Alcance del Producto, el Modelo Comercial B2B y el Modelo y Proceso de Cobranza B2B. Pendiente de que negocio defina metas numéricas para cada indicador. |
| 1.1 | 2026-07-14 | María Fernanda Herazo (con asistencia de Claude) | Corrección tras el Weekly Sync de Producto (10 jul 2026): se agrega la sección "Indicadores por horizonte", que clasifica los grupos de indicadores existentes según MVP, Evolución o Largo plazo, siguiendo el mismo criterio ya aplicado en [Objetivo del Producto](../producto/objetivo.md). Se ajusta la nota sobre rentabilidad para reflejar que es un objetivo de escalamiento, no una condición del piloto. |

---

## Objetivo

Definir los indicadores clave (KPIs) que permiten medir el desempeño comercial, de riesgo, de cartera y de servicio del negocio Fliipa, para apoyar la toma de decisiones del Comité de Cartera, del equipo comercial y del negocio en general.

## Alcance

Este documento cubre indicadores comerciales, de originación y riesgo, de cartera y cobranza, de uso del producto, de servicio al cliente, y financieros/de negocio. No define las metas de negocio de más alto nivel (ver [Objetivo del Producto](../producto/objetivo.md)) ni las reglas que determinan cada estado de mora (ver [Reglas Negocio](reglas-negocio.md)).

## Documentos relacionados

- [Negocio](README.md)
- [Flipa - Biblioteca de Conocimiento](../README.md)
- [Mapa Del Conocimiento](../MAPA_DEL_CONOCIMIENTO.md)
- [Onboarding](../ONBOARDING.md)
- [Convenciones](../CONVENCIONES.md)
- [Producto](../producto/README.md)
- [Funcional](../funcional/README.md)
- [Qa](../qa/README.md)
- [Descripcion Negocio](descripcion-negocio.md)
- [Actores](actores.md)
- [Procesos](procesos/README.md)
- [Reglas Negocio](reglas-negocio.md)

## Indicadores por horizonte

Siguiendo lo acordado en el Weekly Sync de Producto (10 jul 2026), los grupos de indicadores de este documento se ubican en tres horizontes, para no duplicar objetivos entre etapas:

| Horizonte | Qué valida | Grupos de indicadores de este documento |
|---|---|---|
| **MVP (piloto)** | Que el modelo funciona con los primeros clientes | Comerciales y de captación; Originación y riesgo; Uso del producto |
| **Evolución** | Que el modelo mejora a medida que crece la base de datos y de clientes | Cartera y cobranza; Servicio al cliente |
| **Largo plazo** | Que la operación es sostenible y escalable | Financieros y de negocio |

## Contenido

### Indicadores comerciales y de captación

- Tasa de respuesta por canal (correo, WhatsApp, llamada): % de clientes preaprobados que responden a cada canal de contacto simultáneo.
- Tasa de conversión: % de clientes contactados que completan la solicitud de crédito.
- Canal más efectivo y tipo de negocio: análisis por segmento para priorizar canales y perfiles de cliente.
- Clientes contactados y activados en el piloto (meta inicial de referencia: primeros 300 tenderos).
- Seguimiento a primera compra: % de clientes aprobados contactados dentro de los 7 días si no han usado el cupo.

### Indicadores de originación y riesgo

- Tiempo de aprobación o rechazo del crédito (SLA de referencia: máximo 72 horas desde la validación).
- Tasa de aprobación y tasa de rechazo automático de solicitudes.
- % de casos de biometría resueltos manualmente ("en revisión") por el analista de riesgo.
- Duración del proceso de onboarding (referencia: ~3 minutos).

### Indicadores de cartera y cobranza

- Distribución de la cartera por bucket de mora (pago anticipado, bucket 1 a 5), en porcentaje y en monto.
- Tasa de mora y cartera en riesgo (PAR).
- Tasa de recuperación por bucket y por tipo de alivio otorgado (abono parcial, congelamiento de intereses, condonación).
- % de clientes reportados negativamente a centrales de riesgo.
- % de casos escalados a proceso jurídico y tasa de recuperación en esa etapa.
- % de castigo de cartera.
- Cumplimiento de compromisos y acuerdos de pago (promesas cumplidas vs. incumplidas).
- Casos priorizados por el Comité de Cartera y motivo de priorización (días de mora, cuotas vencidas, monto adeudado).

### Indicadores de uso del producto

- % de clientes que usan el cupo tras la aprobación.
- Tiempo entre la aprobación y el primer uso del bono.
- Tasa de renovación de cupo (clientes con buen comportamiento de pago que reciben un nuevo cupo).
- Ticket promedio de compra y recurrencia de compra en tiendas D1.

### Indicadores de servicio al cliente

- % de casos resueltos por el asistente virtual (IA) en el primer contacto.
- Tiempo de resolución por canal (WhatsApp, correo, llamada).
- NPS y CSAT medidos al cierre del caso.
- Cumplimiento del SLA de respuesta inmediata para casos legales o de PQR.

### Indicadores financieros y de negocio

- Costo de fondeo por GMF (4x1000): 0,4% por ciclo de giro fiducia → D1 (equivalente a ~4,8% anual sobre el mismo capital en 12 ciclos); ahorro potencial si la fiducia se constituye en el banco donde ya están los fondos.
- Sostenibilidad financiera de la operación (ingresos por intereses frente a costos operativos y de fondeo) — objetivo de escalamiento a largo plazo, no una condición del piloto; pendiente de definir metodología y meta.
- Información crediticia generada: número de historiales crediticios nuevos construidos para micro y pequeñas empresas, como aporte al ecosistema de datos del Grupo Santo Domingo.
- Indicadores de éxito del producto (según Objetivo del Producto): uso efectivo del crédito, tasa de pago, precisión de la evaluación de riesgo frente a modelos tradicionales, y nivel de automatización de la originación.

## Pendientes

- La mayoría de los indicadores no tiene todavía una meta numérica definida (salvo el SLA de 72 horas y la meta piloto de 300 tenderos); se recomienda que negocio defina umbrales objetivo por indicador.
- No se identificó una periodicidad formal de reporte más allá del Comité de Cartera semanal y los "tableros semanales" mencionados en Reglas Negocio; se recomienda definir la cadencia (diaria, semanal, mensual) por tipo de indicador y quién es el responsable de cada tablero.

## Fuentes consultadas

- Objetivo del Producto (`producto/objetivo.md`)
- Alcance del Producto (`producto/alcance.md`)
- Modelo Comercial B2B — *Modelo Comercial B2B.pptx*
- Modelo y Proceso de Cobranza B2B — *Modelo Cobranza/Modelo_de_Cobranza_B2B_.pptx* y *Modelo Cobranza/Modelo y gestion de cobranza.docx*
- Reglas Negocio (`negocio/reglas-negocio.md`)
- Journeys Colpatria B2B, junio 2026 — *Journeys Fran finales-1.pdf*
- Notas de la reunión "Producto: Weekly Sync" (10 jul 2026) y su transcripción asociada

- Alcance del Producto (`producto/alcance.md`)
- Modelo Comercial B2B — *Modelo Comercial B2B.pptx*
- Modelo y Proceso de Cobranza B2B — *Modelo Cobranza/Modelo_de_Cobranza_B2B_.pptx* y *Modelo Cobranza/Modelo y gestion de cobranza.docx*
- Reglas Negocio (`negocio/reglas-negocio.md`)
- Journeys Colpatria B2B, junio 2026 — *Journeys Fran finales-1.pdf*
- Alcance del Producto (`producto/alcance.md`)
- Modelo Comercial B2B — *Modelo Comercial B2B.pptx*
- Modelo y Proceso de Cobranza B2B — *Modelo Cobranza/Modelo_de_Cobranza_B2B_.pptx* y *Modelo Cobranza/Modelo y gestion de cobranza.docx*
- Reglas Negocio (`negocio/reglas-negocio.md`)
- Journeys Colpatria B2B, junio 2026 — *Journeys Fran finales-1.pdf*
