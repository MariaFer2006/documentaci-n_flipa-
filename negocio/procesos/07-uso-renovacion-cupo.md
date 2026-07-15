# 7. Uso y renovaciÃ³n del cupo

## Objetivo

Definir si un cliente califica para recibir un nuevo cupo despuÃ©s de usar el bono y cumplir con el comportamiento esperado de pago.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 8](imagenes/page-08.png)

- PÃ¡gina 8 del journey Colpatria B2B (junio 2026): uso del bono, pago del crÃ©dito y decisiÃ³n de renovaciÃ³n del cupo.
- Fuente visual de respaldo para validar la secuencia documentada en este proceso.

## Explicación del Journey

1. Uso del bono en D1
   - QuÃ© sucede: el cliente usa el bono en las tiendas D1.
   - QuÃ© actor interviene: cliente y D1.
   - QuÃ© sistema participa: plataforma de consumo del bono.
   - QuÃ© informaciÃ³n se utiliza: uso del bono y estado del cupo.
   - QuÃ© decisiÃ³n se toma: si el crÃ©dito se moviliza de forma vÃ¡lida.
   - QuÃ© ocurre si el resultado es positivo: se continÃºa a la evaluaciÃ³n de pago.
   - QuÃ© ocurre si el resultado es negativo: no se activa la renovaciÃ³n.

2. Pago del crÃ©dito
   - QuÃ© sucede: el cliente paga su obligaciÃ³n segÃºn el plan de pagos.
   - QuÃ© actor interviene: cliente.
   - QuÃ© sistema participa: flujo de pagos y recaudo.
   - QuÃ© informaciÃ³n se utiliza: historia de pagos y saldo del crÃ©dito.
   - QuÃ© decisiÃ³n se toma: si el cliente demuestra buen comportamiento.
   - QuÃ© ocurre si el resultado es positivo: entra a la evaluaciÃ³n de renovaciÃ³n.
   - QuÃ© ocurre si el resultado es negativo: se cierra la posibilidad de renovaciÃ³n.

3. EvaluaciÃ³n de renovaciÃ³n
   - QuÃ© sucede: se valida si el cliente mantiene un buen comportamiento de pago y si hay cupo disponible.
   - QuÃ© actor interviene: riesgo y crÃ©dito.
   - QuÃ© sistema participa: motor de renovaciÃ³n del cupo.
   - QuÃ© informaciÃ³n se utiliza: historial de pagos y capacidad de cupo.
   - QuÃ© decisiÃ³n se toma: si se otorga nuevo cupo.
   - QuÃ© ocurre si el resultado es positivo: se otorga el nuevo cupo.
   - QuÃ© ocurre si el resultado es negativo: se termina el proceso sin renovaciÃ³n.

## Reglas de negocio

- La renovaciÃ³n depende del comportamiento de pago.
- La renovaciÃ³n requiere cupo disponible.
- Si el comportamiento es deficiente o el cupo no estÃ¡ disponible, no se otorga renovaciÃ³n.

## Entradas

- Uso del bono registrado en D1.
- Pago del crÃ©dito realizado por el cliente.
- Estado del cupo disponible.

## Salidas

- Nuevo cupo otorgado o no otorgado.
- Continuidad o terminaciÃ³n de la relaciÃ³n de crÃ©dito.

## Excepciones

- El cliente no paga o incurre en mal comportamiento.
- No existe cupo disponible para renovar.
- El caso queda fuera de la polÃ­tica actual de renovaciÃ³n.

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso.**

