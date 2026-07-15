# 8. Cobro y pago del crÃ©dito

## Objetivo

Generar el plan de pagos del crÃ©dito, registrar los pagos del cliente y actualizar el estado del saldo hasta liquidar o mover el caso a cobranza cuando no se cumpla con el pago.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 7](../journeys-imagenes/page-07.png)

- PÃ¡gina 7 del journey Colpatria B2B (junio 2026): calculadora, plan de pagos, prepago y liquidaciÃ³n del crÃ©dito.
- Fuente visual de respaldo para validar la secuencia documentada en este proceso.

## Explicación del Journey

1. DetecciÃ³n del uso del bono
   - QuÃ© sucede: un worker periÃ³dico detecta que el cliente usÃ³ el bono en D1.
   - QuÃ© actor interviene: sistema y D1.
   - QuÃ© sistema participa: proceso de detecciÃ³n del uso del bono.
   - QuÃ© informaciÃ³n se utiliza: evento de consumo del bono.
   - QuÃ© decisiÃ³n se toma: si se inicia la generaciÃ³n del crÃ©dito y del plan de pagos.
   - QuÃ© ocurre si el resultado es positivo: se crea el plan de pago.
   - QuÃ© ocurre si el resultado es negativo: el proceso no avanza.

2. GeneraciÃ³n del plan de pagos
   - QuÃ© sucede: la calculadora inicia los cÃ¡lculos de cobro y genera la cuota, fechas, tasa y saldo.
   - QuÃ© actor interviene: calculadora y sistema.
   - QuÃ© sistema participa: cÃ¡lculo del crÃ©dito.
   - QuÃ© informaciÃ³n se utiliza: monto del crÃ©dito, tasa y fechas de corte.
   - QuÃ© decisiÃ³n se toma: si se construye el plan de pagos.
   - QuÃ© ocurre si el resultado es positivo: el cliente visualiza su obligaciÃ³n.
   - QuÃ© ocurre si el resultado es negativo: se debe corregir la informaciÃ³n del crÃ©dito.

3. VisualizaciÃ³n de saldo y fecha de pago
   - QuÃ© sucede: el cliente revisa su saldo y la fecha de pago en la plataforma web.
   - QuÃ© actor interviene: cliente y plataforma web.
   - QuÃ© sistema participa: plataforma de crÃ©dito.
   - QuÃ© informaciÃ³n se utiliza: saldo, fecha y plan de pagos.
   - QuÃ© decisiÃ³n se toma: si el cliente decide pagar antes o esperar el dÃ©bito automÃ¡tico.
   - QuÃ© ocurre si el resultado es positivo: el cliente define su forma de pago.
   - QuÃ© ocurre si el resultado es negativo: se quedan pendientes de pago.

4. Pago por prepago o dÃ©bito automÃ¡tico
   - QuÃ© sucede: el cliente realiza un prepago por PSE o espera el cobro automÃ¡tico al cierre del ciclo.
   - QuÃ© actor interviene: cliente, PSE y Druo.
   - QuÃ© sistema participa: medios de pago y cobro automÃ¡tico.
   - QuÃ© informaciÃ³n se utiliza: forma de pago y saldo del crÃ©dito.
   - QuÃ© decisiÃ³n se toma: si el pago entra o no al sistema.
   - QuÃ© ocurre si el resultado es positivo: se registra el pago.
   - QuÃ© ocurre si el resultado es negativo: el caso puede pasar a mora o cobranza.

5. ActualizaciÃ³n del saldo y amortizaciÃ³n
   - QuÃ© sucede: el sistema registra el pago, aplica amortizaciÃ³n y actualiza el saldo del crÃ©dito.
   - QuÃ© actor interviene: sistema.
   - QuÃ© sistema participa: motor de amortizaciÃ³n.
   - QuÃ© informaciÃ³n se utiliza: pago recibido y saldo vigente.
   - QuÃ© decisiÃ³n se toma: si el crÃ©dito queda al dÃ­a.
   - QuÃ© ocurre si el resultado es positivo: se liquida el crÃ©dito.
   - QuÃ© ocurre si el resultado es negativo: se deriva a cobranza.

## Reglas de negocio

- El proceso se activa cuando el sistema detecta el uso del bono en D1.
- El cliente puede pagar por prepago o esperar el cobro automÃ¡tico al cierre del ciclo.
- El pago registrado se convierte en amortizaciÃ³n y actualiza el saldo del crÃ©dito.
- Si el crÃ©dito queda al dÃ­a, se liquida y se libera el cupo.
- Si no, el caso se deriva a cobranza.

## Entradas

- Uso del bono detectado en D1.
- Datos del crÃ©dito, tasa y plan de pagos.
- Pago del cliente por PSE o dÃ©bito automÃ¡tico.

## Salidas

- Plan de pagos generado.
- Pago registrado y saldo actualizado.
- CrÃ©dito liquidado o derivado a cobranza.

## Excepciones

- El pago no se registra correctamente.
- El cliente no paga y entra en mora.
- El crÃ©dito no queda al dÃ­a al cierre del ciclo.
- El cupo no se libera porque la liquidaciÃ³n no concluye.

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso.**

