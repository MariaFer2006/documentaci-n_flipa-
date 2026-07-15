# 9. GestiÃ³n de cobranza por bucket de mora

## Objetivo

Gestionar la mora del crÃ©dito desde la originaciÃ³n y aplicar la estrategia de cobranza adecuada segÃºn el bucket en que se encuentre el cliente.

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

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso.**

