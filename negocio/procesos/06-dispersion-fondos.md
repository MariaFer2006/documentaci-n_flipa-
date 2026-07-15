# 6. DispersiÃ³n de fondos

## Objetivo

Gestionar el desembolso de fondos, la activaciÃ³n del bono y el retorno del pago para que el crÃ©dito quede operativo y, cuando aplique, se evalÃºe la renovaciÃ³n del cupo.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 8](imagenes/page-08.png)

- PÃ¡gina 8 del journey Colpatria B2B (junio 2026): dispersiÃ³n de fondos, fiducia, GMF 4x1000 y bloqueo de cupo.
- Fuente visual de respaldo para validar la secuencia documentada en este proceso.

## Explicación del Journey

1. CreaciÃ³n y fondeo de la cuenta fiducia
   - QuÃ© sucede: Colpatria crea la cuenta fiducia y la fondea con los recursos del piloto.
   - QuÃ© actor interviene: Colpatria.
   - QuÃ© sistema participa: cuentas de fiducia y operaciÃ³n de tesorerÃ­a.
   - QuÃ© informaciÃ³n se utiliza: monto del piloto y condiciones del crÃ©dito.
   - QuÃ© decisiÃ³n se toma: si la cuenta estÃ¡ lista para operar.
   - QuÃ© ocurre si el resultado es positivo: se concentra el dinero del crÃ©dito.
   - QuÃ© ocurre si el resultado es negativo: el desembolso no se ejecuta.

2. ConcentraciÃ³n de fondos por la fiducia
   - QuÃ© sucede: la fiducia concentra la fuente y el retorno del dinero del crÃ©dito.
   - QuÃ© actor interviene: fiducia.
   - QuÃ© sistema participa: operaciÃ³n de tesorerÃ­a y cuentas de recaudo.
   - QuÃ© informaciÃ³n se utiliza: originaciÃ³n y retorno del crÃ©dito.
   - QuÃ© decisiÃ³n se toma: si el flujo financiero estÃ¡ listo para girar fondos.
   - QuÃ© ocurre si el resultado es positivo: se ejecuta el desembolso a D1.
   - QuÃ© ocurre si el resultado es negativo: la operaciÃ³n queda pendiente.

3. Desembolso y emisiÃ³n del bono
   - QuÃ© sucede: la fiducia gira los fondos a D1 y este emite el bono asociado al cupo utilizado.
   - QuÃ© actor interviene: D1 y fiducia.
   - QuÃ© sistema participa: proceso de desembolso y activaciÃ³n del bono.
   - QuÃ© informaciÃ³n se utiliza: valor del cupo utilizado y estado de la operaciÃ³n.
   - QuÃ© decisiÃ³n se toma: si el bono se activa correctamente.
   - QuÃ© ocurre si el resultado es positivo: el cliente recibe el bono.
   - QuÃ© ocurre si el resultado es negativo: se detiene la activaciÃ³n del cupo.

4. Uso del bono por parte del cliente
   - QuÃ© sucede: el cliente recibe el bono y lo usa en D1.
   - QuÃ© actor interviene: cliente y D1.
   - QuÃ© sistema participa: plataforma de uso del bono.
   - QuÃ© informaciÃ³n se utiliza: bono emitido y transacciÃ³n del cliente.
   - QuÃ© decisiÃ³n se toma: si la compra se registra como uso del crÃ©dito.
   - QuÃ© ocurre si el resultado es positivo: el cupo remanente se bloquea automÃ¡ticamente.
   - QuÃ© ocurre si el resultado es negativo: la operaciÃ³n no se consolida.

5. Pago del crÃ©dito
   - QuÃ© sucede: el cliente paga su crÃ©dito despuÃ©s de haber usado el bono.
   - QuÃ© actor interviene: cliente.
   - QuÃ© sistema participa: flujo de recaudo y pagos.
   - QuÃ© informaciÃ³n se utiliza: saldo del crÃ©dito y fecha de pago.
   - QuÃ© decisiÃ³n se toma: si el pago se registra adecuadamente.
   - QuÃ© ocurre si el resultado es positivo: el dinero retorna a la fiducia.
   - QuÃ© ocurre si el resultado es negativo: se activa seguimiento de cobranza.

6. EvaluaciÃ³n de renovaciÃ³n del cupo
   - QuÃ© sucede: el sistema evalÃºa si se otorga un nuevo cupo segÃºn el comportamiento de pago y la disponibilidad del cupo.
   - QuÃ© actor interviene: sistema y riesgo.
   - QuÃ© sistema participa: motor de renovaciÃ³n del cupo.
   - QuÃ© informaciÃ³n se utiliza: comportamiento de pago y disponibilidad del cupo.
   - QuÃ© decisiÃ³n se toma: si el cliente califica para una nueva asignaciÃ³n.
   - QuÃ© ocurre si el resultado es positivo: se otorga nuevo cupo.
   - QuÃ© ocurre si el resultado es negativo: finaliza el proceso sin renovaciÃ³n.

## Reglas de negocio

- La cuenta fiducia debe crearse y fondearse antes del desembolso.
- El giro de fondos va de la fiducia a D1 para activar el bono.
- El pago del crÃ©dito retorna a la fiducia, no a D1.
- El cupo remanente se bloquea automÃ¡ticamente tras el primer uso.
- La renovaciÃ³n del cupo depende del comportamiento de pago y de la disponibilidad de cupo.

## Entradas

- Fondos para el piloto y cuenta fiducia creada.
- Monto del cupo utilizado y estado del crÃ©dito.
- Compra del cliente en D1 para activar el bono.
- Pago del cliente y estado de la cartera.

## Salidas

- Desembolso ejecutado y bono emitido.
- Pago del crÃ©dito retornado a la fiducia.
- DecisiÃ³n de renovaciÃ³n del cupo segÃºn la polÃ­tica vigente.

## Excepciones

- La cuenta fiducia no se crea o no se fondea.
- No se ejecuta el desembolso a D1.
- El cliente no usa el bono o no paga el crÃ©dito.
- La renovaciÃ³n del cupo no aplica por mal comportamiento o falta de disponibilidad.

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso.**

