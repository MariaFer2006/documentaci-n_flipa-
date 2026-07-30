# 0. Caso de uso general: gestión de la solicitud de crédito empresarial

[← Volver a Casos De Uso](README.md)

## Diagrama general

![Diagrama de casos de uso: Administrador](diagramas/00-diagrama-general.svg)

## Descripción

Este es el caso de uso "paraguas" que agrupa los cuatro casos de uso específicos documentados hoy (CU-1 a CU-4). Describe, de principio a fin, cómo se gestiona una solicitud de crédito empresarial dentro de Fliipa: desde que el cliente empresarial registra la solicitud hasta que un administrador hace seguimiento al crédito ya aprobado.

Cada uno de los cuatro casos de uso específicos es una etapa de este flujo general, no un caso de uso independiente sin relación entre sí.

> ⚠️ **Corrección (2026-07-30):** la versión anterior de esta página describía los cuatro casos de uso como ejecutados enteramente por el administrador. Al validar contra el código (incluida la carpeta `services/`, no revisada en la primera validación), se confirma que el flujo tiene **actores mixtos**: el cliente empresarial registra la solicitud (CU-1), el sistema evalúa el riesgo automáticamente (CU-2), la decisión es automática con posibilidad de override manual del administrador (CU-3), y el administrador/analista de cartera hace el seguimiento (CU-4).

| Campo | Detalle |
|---|---|
| **Actor principal** | Mixto: cliente empresarial (CU-1), sistema automático (CU-2 y CU-3), administrador / analista de cartera (CU-3 manual y CU-4) |
| **Actores secundarios** | Ninguno documentado aún fuera de estos (ver "Alcance actual" más abajo) |
| **Precondición** | Existe un cliente empresarial identificado como potencial sujeto de crédito. |
| **Postcondición (éxito)** | La solicitud queda registrada, evaluada, decidida (aprobada o rechazada) y, si fue aprobada, en seguimiento activo. |
| **Postcondición (fallo)** | La solicitud queda registrada como rechazada, con el motivo documentado. |
| **Disparador (trigger)** | El cliente empresarial inicia una nueva solicitud de crédito desde el checkout. |

## Flujo general

1. **[CU-1 — Registrar una solicitud de crédito](01-registrar-solicitud-credito.md):** el cliente empresarial captura la solicitud y la información de su empresa desde `apps/checkout`.
2. **[CU-2 — Evaluar riesgo](02-evaluar-riesgo.md):** el sistema evalúa automáticamente el comportamiento comercial y transaccional del cliente mediante el motor de reglas.
3. **[CU-3 — Decidir aprobación o rechazo](03-decidir-aprobacion-rechazo.md):** el sistema decide automáticamente a partir de la evaluación, o el administrador decide manualmente si tiene el permiso correspondiente. Este caso de uso **incluye** siempre a CU-2, porque no puede haber decisión sin una evaluación de riesgo previa (relación «include» en el diagrama).
4. **[CU-4 — Dar seguimiento al crédito](04-seguimiento-credito.md):** una vez aprobado, el administrador o el analista de cartera registra y monitorea el cumplimiento del crédito.

## Alcance actual

Este caso de uso general, tal como está documentado hoy, cubre únicamente el proceso de originación del crédito (registro, evaluación de riesgo y decisión), con los actores mixtos descritos arriba. No cubre todavía:

- Los demás actores definidos en [Actores](../../negocio/Actores/README.md) (cliente empresarial, asesor de servicio al cliente, analista de riesgo, analista de cartera, agente de servicio al cliente).
- Los 11 procesos de negocio definidos en [Alcance del Producto](../../producto/alcance.md) — hoy solo se cubren, parcialmente, 2 de ellos (evaluación de riesgo y decisión).

Esta ampliación (de 4 a los 18 casos de uso que ya referencia [Historias de Usuario](../03-historias-usuario/README.md)) está pendiente y documentada como hallazgo H-02 en el Informe de Validación Funcional del 29 de julio de 2026.

## Documentos relacionados

- [Casos De Uso](README.md)
- [Historias Usuario](../03-historias-usuario/README.md)
- [Requerimientos Funcionales](../04-requerimientos/funcionales/README.md)
- [Actores](../../negocio/Actores/README.md)
- [Alcance del Producto](../../producto/alcance.md)
