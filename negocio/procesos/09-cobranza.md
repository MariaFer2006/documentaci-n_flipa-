# 9. GestiÃ³n de cobranza por bucket de mora

[â† Volver a Procesos](README.md)

| Documento | GestiÃ³n de cobranza por bucket de mora |
|-----------|-------------------------------------------|
| **Proyecto** | Fliipa |
| **VersiÃ³n** | 2.1 |
| **Estado** | Borrador para validaciÃ³n |
| **Responsable** | Cobranza y cartera |
| **Ãšltima actualizaciÃ³n** | 2026-07-13 |

---

## Control de versiones

| VersiÃ³n | Fecha | Autor | DescripciÃ³n |
|---------|-------|-------|-------------|
| 1.0 | 2026-07-09 | MarÃ­a Fernanda Herazo | VersiÃ³n inicial, como secciÃ³n 9 del `procesos.md` original (monolÃ­tico). |
| 2.0 | 2026-07-13 | MarÃ­a Fernanda Herazo | ReorganizaciÃ³n en archivo independiente con diagrama Mermaid y nota de inconsistencia en tabla, dentro del split de `negocio/procesos/`. |
| 2.1 | 2026-07-13 | MarÃ­a Fernanda Herazo | CorrecciÃ³n de 3 errores detectados al validar contra `Mensajes WhatsApp B2B.xlsx` y la pÃ¡gina 10 de `Journeys Fran finales.pdf`: (1) Bucket 1 ahora cita dÃ­a 17 (preaviso informativo), dÃ­a 20 (aviso legal, Ley 2157 de 2021 Art. 3) y dÃ­a 30 (aviso previo final) en vez de "preaviso dÃ­a 15" sin base legal, corrigiendo tambiÃ©n que el dÃ­a 30 pertenece al rango de Bucket 1 (1-30 dÃ­as), no al de Bucket 2; (2) en la nota de inconsistencia, la "llamada de confirmaciÃ³n de causa" se reubica en el dÃ­a 6-15 (no dÃ­a 16-30, que corresponde a la reestructuraciÃ³n/acuerdo de pago y al reporte a centrales); (3) se agrega el paso final "castigo de cartera segÃºn polÃ­tica" que faltaba. |

## Objetivo

Gestionar la mora del crÃ©dito desde la originaciÃ³n y aplicar la estrategia de cobranza adecuada segÃºn el bucket en que se encuentre el cliente.

## DescripciÃ³n general

La cartera se segmenta en seis estados. La gestiÃ³n se mantiene activa en todos ellos mediante llamadas, correos y WhatsApp, y la cobranza inicia desde la originaciÃ³n del crÃ©dito, no desde la mora. La estrategia varÃ­a segÃºn la antigÃ¼edad de la obligaciÃ³n, la severidad del atraso y la necesidad de escalar a procesos jurÃ­dicos o de castigo de cartera.

## Actores involucrados

- Cliente: recibe los mensajes de cobranza y responde o negocia pagos.
- Cobranza y cartera: ejecutan las acciones de seguimiento y priorizaciÃ³n por bucket.
- ComitÃ© de Cartera: prioriza casos con mayor riesgo o mora.
- Ãrea jurÃ­dica: interviene en los buckets mÃ¡s avanzados del proceso.

## Buckets de mora

| Bucket | Rango | Acciones principales |
|--------|-------|------------------------|
| Pago anticipado | Antes del vencimiento | Visita de originaciÃ³n; mensajes de bienvenida por WhatsApp (dÃ­a -5, -3, -1, 0); visita de confirmaciÃ³n y verificaciÃ³n el dÃ­a 25 (contacto, medios de pago, inventario) |
| Bucket 1 | 1â€“30 dÃ­as | Llamada con guion estandarizado; WhatsApp informativo desde el dÃ­a 3; **preaviso informativo de posible reporte (dÃ­a 17)**; **aviso legal formal citando el Art. 3 de la Ley 2157 de 2021 (dÃ­a 20)**; **aviso previo final antes de reporte (dÃ­a 30)**; priorizaciÃ³n de visita segÃºn ComitÃ© de Cartera |
| Bucket 2 | 31â€“60 dÃ­as | Llamada para negociar y dar seguimiento a compromisos; comunicaciones por WhatsApp y correo |
| Bucket 3 | 61â€“90 dÃ­as | Email de preaviso de proceso jurÃ­dico |
| Bucket 4 | 91â€“120 dÃ­as | Aviso formal de inicio de proceso jurÃ­dico (email y carta fÃ­sica); contacto directo del analista jurÃ­dico o abogado |
| Bucket 5 | 120+ dÃ­as | DefiniciÃ³n de cuantÃ­a y juzgado; radicaciÃ³n de la demanda; verificaciÃ³n de datos de notificaciÃ³n; canal de negociaciÃ³n solo dentro del proceso legal, condicionado a pago inicial y compromiso documentado |

## ComitÃ© de Cartera

| Frecuencia | Criterios de priorizaciÃ³n |
|------------|----------------------------|
| Semanal | DÃ­as de mora (foco en 20+), flujo de caja y tipo de negocio, cuotas vencidas, historial y respuesta del cliente, monto adeudado alto |

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 10](../journeys-imagenes/page-10.png)

- PÃ¡gina 10 del journey Colpatria B2B (junio 2026): cobranza, reintentos, reporte y escalamiento jurÃ­dico.
- Fuente visual de respaldo para validar la secuencia documentada en este proceso.

## Explicación del Journey

1. Pago anticipado
   - QuÃ© sucede: se inicia la gestiÃ³n de cobranza desde la originaciÃ³n con mensajes de bienvenida y confirmaciÃ³n.
   - QuÃ© actor interviene: cobranza y cliente.
   - QuÃ© sistema participa: canal de WhatsApp y registro de seguimiento.
   - QuÃ© informaciÃ³n se utiliza: fecha de vencimiento y estado del crÃ©dito.
   - QuÃ© decisiÃ³n se toma: si se activa el contacto previo al pago.
   - QuÃ© ocurre si el resultado es positivo: se mantiene seguimiento antes de la mora.
   - QuÃ© ocurre si el resultado es negativo: el cliente no responde y se avanza al bucket 1.

2. Bucket 1
   - QuÃ© sucede: se ejecutan llamadas, WhatsApp informativos y avisos legales conforme avanza el retraso.
   - QuÃ© actor interviene: cobranza y cliente.
   - QuÃ© sistema participa: comunicaciones y registro de acciones.
   - QuÃ© informaciÃ³n se utiliza: dÃ­as de mora y polÃ­tica de mensajes.
   - QuÃ© decisiÃ³n se toma: si el cliente responde o se requiere priorizaciÃ³n por ComitÃ© de Cartera.
   - QuÃ© ocurre si el resultado es positivo: se avanza a negociaciÃ³n o acuerdo.
   - QuÃ© ocurre si el resultado es negativo: se sigue escalando dentro de la estrategia de cobranza.

3. Bucket 2 y 3
   - QuÃ© sucede: se intensifica la negociaciÃ³n, el seguimiento a compromisos y el preaviso jurÃ­dico.
   - QuÃ© actor interviene: cobranza y Ã¡rea jurÃ­dica.
   - QuÃ© sistema participa: gestiÃ³n de cartera y alertas.
   - QuÃ© informaciÃ³n se utiliza: historial de pagos y compromiso del cliente.
   - QuÃ© decisiÃ³n se toma: si el caso sigue en negociaciÃ³n o se prepara para un proceso formal.
   - QuÃ© ocurre si el resultado es positivo: se evita la escalaciÃ³n legal.
   - QuÃ© ocurre si el resultado es negativo: se pasa a buckets superiores.

4. Bucket 4 y 5
   - QuÃ© sucede: se declara el inicio de proceso jurÃ­dico, se radica la demanda y se gestiona la notificaciÃ³n.
   - QuÃ© actor interviene: Ã¡rea jurÃ­dica y cobranza.
   - QuÃ© sistema participa: proceso legal y notificaciones.
   - QuÃ© informaciÃ³n se utiliza: cuantÃ­a, juzgado y documentos de la obligaciÃ³n.
   - QuÃ© decisiÃ³n se toma: si el proceso continÃºa o se suspende por acuerdo.
   - QuÃ© ocurre si el resultado es positivo: se retira la demanda si se acuerda el pago.
   - QuÃ© ocurre si el resultado es negativo: se continÃºa en proceso legal y castigo de cartera.

## Reglas de negocio

- La cobranza inicia desde la originaciÃ³n del crÃ©dito, no desde la mora.
- Se manejan buckets de mora del 1 al 5, segÃºn la antigÃ¼edad del atraso.
- Bucket 1 incluye preaviso informativo, aviso legal y aviso previo final antes de reporte.
- El castigo de cartera aplica cuando la polÃ­tica lo exige y el caso no se recupera.
- La negociaciÃ³n sÃ³lo puede continuar dentro del proceso legal cuando exista pago inicial y compromiso documentado.

## Entradas

- CrÃ©dito activo y estado de pago del cliente.
- Historial de mora y compromisos de pago.
- Mensajes de WhatsApp, correos y notificaciones de cobranza.

## Salidas

- Seguimiento de cobranza por bucket.
- NegociaciÃ³n o acuerdo de pago.
- EscalaciÃ³n jurÃ­dica o castigo de cartera segÃºn la polÃ­tica.

## Excepciones

- El cliente paga a tiempo y no entra en mora.
- El cliente responde y se negocia un acuerdo de pago.
- El caso supera los lÃ­mites del bucket 5 y requiere proceso jurÃ­dico.
- El cliente no responde y el caso continua en escalada.

## Consideraciones

- El documento conserva la tabla de buckets y la nota de inconsistencia con el journey de Colpatria, porque la fuente oficial todavÃ­a necesita validaciÃ³n.
- El mismo tema aparece en [Reglas Negocio](../reglas-negocio/02-mora-buckets.md).

## Pendientes de validaciÃ³n

> **Pendiente de validar con el dueÃ±o del proceso.** La ruta exacta de la cobranza jurÃ­dica y el tratamiento del castigo de cartera deben confirmarse con negocio y operaciones.

## âš ï¸ Nota de inconsistencia (pendiente de validar)

El journey de Colpatria B2B (junio 2026) describe un flujo **mÃ¡s corto** que el esquema de buckets anterior:

| Journey Colpatria B2B | Esquema de buckets (este documento) |
|---|---|
| DÃ­a 0: dÃ©bito automÃ¡tico (Druo) | â€” |
| DÃ­a 1â€“5: reintento de dÃ©bito automÃ¡tico | â€” |
| DÃ­a 6â€“15: WhatsApp/SMS con preaviso de reporte a 15 dÃ­as **y** llamada de confirmaciÃ³n de causa (guion estandarizado) + bloqueo de cupo | Bucket 1: preaviso dÃ­a 17, aviso legal dÃ­a 20 (Ley 2157) |
| DÃ­a 16â€“30: reestructuraciÃ³n o acuerdo de pago (o castigo parcial con cancelaciÃ³n de cupo); si no acepta, reporte a centrales de riesgo (dÃ­a 15 de mora / dÃ­a 45 del crÃ©dito) | Bucket 1: aviso previo final dÃ­a 30 |
| Cliente continÃºa sin pagar â†’ **castigo de cartera segÃºn polÃ­tica**; bloqueo permanente de cupo (dÃ­a 30 de mora); se inicia cobro jurÃ­dico | Escalamiento jurÃ­dico entre bucket 3 y 5, es decir **61 a 120+ dÃ­as** |

Ambos flujos quedan documentados hasta que negocio y operaciones confirmen cuÃ¡l estÃ¡ vigente (la misma nota aplica en [Reglas Negocio](../reglas-negocio/02-mora-buckets.md)).

## Fuentes consultadas

- `Mensajes WhatsApp B2B.xlsx` (dÃ­as exactos de preaviso/aviso y cita de la Ley 2157 de 2021, Art. 3)
- `Journeys Fran finales.pdf` (Journeys Colpatria B2B, junio 2026), pÃ¡gina 10 ("Cobranza", swimlanes Cliente / Sistema / Analista de cobranza / Legal-JurÃ­dico)

