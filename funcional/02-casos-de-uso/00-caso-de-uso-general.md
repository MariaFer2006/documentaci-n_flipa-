# CU-000. Caso de uso general: gestión del ciclo de vida del crédito empresarial

[← Volver a Casos De Uso](README.md)

## Diagrama general

![Diagrama de casos de uso: Administrador](diagramas/00-diagrama-general.svg)

## Descripción

Este es el caso de uso "paraguas" que agrupa los cuatro casos de uso específicos documentados hoy (CU-1 a CU-4). Describe, de principio a fin, cómo el administrador gestiona una solicitud de crédito empresarial dentro de Fliipa: desde que se registra la solicitud hasta que se hace seguimiento al crédito ya aprobado.

Cada uno de los cuatro casos de uso específicos es una etapa de este flujo general, no un caso de uso independiente sin relación entre sí.

| Campo | Detalle |
|---|---|
| **Actor principal** | Administrador |
| **Actores secundarios** | Ninguno documentado aún (ver "Alcance actual" más abajo) |
| **Precondición** | Existe un cliente empresarial identificado como potencial sujeto de crédito. |
| **Postcondición (éxito)** | La solicitud queda registrada, evaluada, decidida (aprobada o rechazada), y si fue aprobada, el cliente puede usar y pagar su cupo, con seguimiento activo por parte del equipo interno. |
| **Postcondición (fallo)** | La solicitud queda registrada como rechazada, con el motivo documentado. |
| **Disparador (trigger)** | El administrador identifica o recibe una nueva solicitud de crédito para gestionar. |

## Flujo general por etapa

### Originación

1. **[CU-1 — Registrar una solicitud de crédito](01-registrar-solicitud-credito.md):** el administrador captura la solicitud y la información del cliente y del negocio.
2. **[CU-2 — Evaluar riesgo](02-evaluar-riesgo.md):** el administrador revisa el comportamiento comercial y transaccional del cliente.
3. **[CU-3 — Decidir aprobación o rechazo](03-decidir-aprobacion-rechazo.md):** el administrador toma la decisión formal sobre la solicitud. Este caso de uso **incluye** siempre a CU-2, porque no puede haber decisión sin una evaluación de riesgo previa (relación «include» en el diagrama).
4. **[CU-4 — Dar seguimiento al crédito](04-seguimiento-credito.md):** una vez aprobado, el administrador registra y monitorea el cumplimiento del crédito.

## Alcance actual

Este caso de uso general, tal como está documentado hoy, cubre únicamente el proceso de evaluación y decisión de crédito desde la perspectiva del **administrador**. No cubre todavía:

- Los demás actores definidos en [Actores](../../negocio/Actores/README.md) (cliente empresarial, asesor de servicio al cliente, analista de riesgo, analista de cartera, agente de servicio al cliente).
- Los 11 procesos de negocio definidos en [Alcance del Producto](../../producto/alcance.md) — hoy solo se cubren, parcialmente, 2 de ellos (evaluación de riesgo y decisión).

Esta ampliación (de 4 a los 18 casos de uso que ya referencia [Historias de Usuario](../03-historias-usuario/README.md)) está pendiente y documentada como hallazgo H-02 en el Informe de Validación Funcional del 29 de julio de 2026.

## Documentos relacionados

- [Casos De Uso](README.md)
- [Historias Usuario](../03-historias-usuario/README.md)
- [Requerimientos Funcionales](../04-requerimientos/01-requerimientos-funcionales.md)
- [Requerimientos No Funcionales](../04-requerimientos/02-requerimientos-no-funcionales.md)
- [Actores](../../negocio/Actores/README.md)
- [Alcance del Producto](../../producto/alcance.md)
