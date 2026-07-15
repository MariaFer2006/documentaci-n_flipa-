# 6. DispersiÃ³n de fondos

[â† Volver a Procesos](README.md)

| Documento | DispersiÃ³n de fondos |
|-----------|-------------------------|
| **Proyecto** | Fliipa |
| **VersiÃ³n** | 2.1 |
| **Estado** | Borrador para validaciÃ³n |
| **Responsable** | Riesgo y crÃ©dito / TesorerÃ­a |
| **Ãšltima actualizaciÃ³n** | 2026-07-13 |

---

## Control de versiones

| VersiÃ³n | Fecha | Autor | DescripciÃ³n |
|---------|-------|-------|-------------|
| 1.0 | 2026-07-09 | MarÃ­a Fernanda Herazo  | VersiÃ³n inicial, como secciÃ³n 6 del `procesos.md` original (monolÃ­tico). |
| 2.0 | 2026-07-13 | MarÃ­a Fernanda Herazo  | ReorganizaciÃ³n en archivo independiente con diagrama Mermaid, dentro del split de `negocio/procesos/`. |
| 2.1 | 2026-07-13 | MarÃ­a Fernanda Herazo | CorrecciÃ³n solicitada tras validar contra la pÃ¡gina 8 de `Journeys Fran finales.pdf`: se agrega el paso inicial (Colpatria crea y fondea la cuenta fiducia); se corrige la direcciÃ³n del desembolso â€” la fiducia **concentra** los fondos y los **gira hacia D1** (no los "recibe" de D1); se corrige la atribuciÃ³n de la emisiÃ³n del bono, que hace **D1** (no la fiducia); se agrega el paso explÃ­cito "cliente paga su crÃ©dito"; se agrega la evaluaciÃ³n de renovaciÃ³n de cupo (SÃ­/No) al final del flujo, que faltaba por completo. |

## Objetivo

Gestionar el desembolso de fondos, la activaciÃ³n del bono y el retorno del pago para que el crÃ©dito quede operativo y, cuando aplique, se evalÃºe la renovaciÃ³n del cupo.

## DescripciÃ³n general

Los fondos se administran mediante una fiducia constituida por el aliado de core bancario (Colpatria), que concentra el origen y el retorno del dinero del crÃ©dito. El flujo inicia con el fondeo de la cuenta fiducia, continÃºa con el giro hacia D1 para activar el bono y termina con el pago del cliente y la evaluaciÃ³n de renovaciÃ³n del cupo.

## Actores involucrados

- Colpatria: crea y fondea la cuenta fiducia.
- Fiducia: concentra los fondos y recibe el retorno del crÃ©dito.
- D1: recibe el desembolso, emite el bono y activa su uso en la plataforma.
- Cliente: recibe el bono, lo usa y paga el crÃ©dito.
- TesorerÃ­a y riesgo: supervisan la operaciÃ³n y la continuidad del cupo.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 8](../journeys-imagenes/page-08.png)

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

## Consideraciones

- El bono se activa cuando un worker periÃ³dico detecta la compra del cliente en D1.
- El costo del GMF 4x1000 es relevante para la operaciÃ³n del flujo financiero.
- La evaluaciÃ³n de renovaciÃ³n se documenta tambiÃ©n en [07-uso-renovacion-cupo.md](07-uso-renovacion-cupo.md).

## Pendientes de validaciÃ³n

> **Pendiente de validar con el dueÃ±o del proceso.** La polÃ­tica exacta de renovaciÃ³n del cupo y el tratamiento de la cuenta fiducia deben confirmarse con tesorerÃ­a y negocio.

## Costo del GMF (4x1000)

| Concepto | Valor |
|----------|-------|
| GMF por giro de la fiducia a D1 | $4.000 por cada ciclo de $1.000.000 (0,4%) |
| Costo anual equivalente (12 ciclos sobre el mismo capital) | 4,8% anual |
| Ahorro posible | Si la fiducia se constituye en el mismo banco donde ya estÃ¡n los fondos, se evita el 4x1000 del fondeo inicial |

## Fuentes consultadas

- `Journeys Fran finales.pdf` (Journeys Colpatria B2B, junio 2026), pÃ¡gina 8 ("Flujo de dispersiÃ³n", swimlanes Colpatria / Fiducia / D1 / Cliente)

