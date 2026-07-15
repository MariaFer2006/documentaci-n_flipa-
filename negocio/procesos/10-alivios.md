# 10. Alivios y negociación

[← Volver a Procesos](README.md)

| Documento | Alivios y negociación |
|-----------|--------------------------|
| **Proyecto** | Fliipa |
| **Versión** | 2.1 |
| **Estado** | Borrador para validación |
| **Responsable** | Cobranza y cartera |
| **Última actualización** | 2026-07-13 |

---

## Control de versiones

| Versión | Fecha | Autor | Descripción |
|---------|-------|-------|-------------|
| 1.0 | 2026-07-09 | María Fernanda Herazo  | Versión inicial, como sección 10 del `procesos.md` original (monolítico), con tres tipos de alivio. |
| 2.0 | 2026-07-13 | María Fernanda Herazo  | Reorganización en archivo independiente, dentro del split de `negocio/procesos/`. |
| 2.1 | 2026-07-13 | María Fernanda Herazo  | Se agrega **Refinanciación** como cuarto tipo de alivio, con base en `Speech llamada cobranza B2B.xlsx` y `Tipificaciòn.xlsx`, y en que ya aparecía citada en la tipificación de contactos de [Reglas Negocio](../reglas-negocio/03-alivios-negociacion.md) sin estar en esta lista. Se marca como pendiente de definir por negocio, porque ninguna de las fuentes revisadas especifica sus condiciones (monto mínimo, plazo, tratamiento de intereses o qué pasa ante incumplimiento), a diferencia de los otros tres tipos. |

---

Durante la gestión de mora se pueden ofrecer cuatro tipos de alivio:

| Tipo de alivio | Descripción breve |
|-----------------|--------------------|
| Abono parcial | Pago parcial de la obligación |
| Congelamiento de intereses | Pausa temporal en la generación de intereses |
| Condonación | Perdón total o parcial de la deuda |
| Refinanciación ⚠️ | Reestructuración del crédito en nuevas condiciones de pago |

El detalle de condiciones de abono parcial, congelamiento y condonación está en [Reglas Negocio](../reglas-negocio/03-alivios-negociacion.md).

> **⚠️ Refinanciación — pendiente de definir por negocio:** aparece mencionada como opción de "escala de pagos" en el guion de llamada de cobranza (`Speech llamada cobranza B2B.xlsx`) y como categoría de tipificación en `Tipificaciòn.xlsx` y en [Reglas Negocio](../reglas-negocio/03-alivios-negociacion.md), pero ninguna fuente revisada especifica montos mínimos, plazos, ni el tratamiento ante incumplimiento. Hasta que negocio defina estas condiciones, cualquier solicitud de refinanciación debe escalarse al Comité de Cartera en lugar de ofrecerse con condiciones no documentadas.

## Fuentes consultadas

- `Speech llamada cobranza B2B.xlsx` (hoja "Speech", escala de pagos)
- `Tipificaciòn.xlsx` (categoría de resultado/promesa de pago)
