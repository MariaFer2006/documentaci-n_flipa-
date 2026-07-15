# 10. Alivios y negociaciÃ³n

[â† Volver a Procesos](README.md)

| Documento | Alivios y negociaciÃ³n |
|-----------|--------------------------|
| **Proyecto** | Fliipa |
| **VersiÃ³n** | 2.1 |
| **Estado** | Borrador para validaciÃ³n |
| **Responsable** | Cobranza y cartera |
| **Ãšltima actualizaciÃ³n** | 2026-07-13 |

---

## Control de versiones

| VersiÃ³n | Fecha | Autor | DescripciÃ³n |
|---------|-------|-------|-------------|
| 1.0 | 2026-07-09 | MarÃ­a Fernanda Herazo  | VersiÃ³n inicial, como secciÃ³n 10 del `procesos.md` original (monolÃ­tico), con tres tipos de alivio. |
| 2.0 | 2026-07-13 | MarÃ­a Fernanda Herazo  | ReorganizaciÃ³n en archivo independiente, dentro del split de `negocio/procesos/`. |
| 2.1 | 2026-07-13 | MarÃ­a Fernanda Herazo  | Se agrega **RefinanciaciÃ³n** como cuarto tipo de alivio, con base en `Speech llamada cobranza B2B.xlsx` y `TipificaciÃ²n.xlsx`, y en que ya aparecÃ­a citada en la tipificaciÃ³n de contactos de [Reglas Negocio](../reglas-negocio/03-alivios-negociacion.md) sin estar en esta lista. Se marca como pendiente de definir por negocio, porque ninguna de las fuentes revisadas especifica sus condiciones (monto mÃ­nimo, plazo, tratamiento de intereses o quÃ© pasa ante incumplimiento), a diferencia de los otros tres tipos. |

## Objetivo

Ofrecer alternativas de alivio a los clientes que atraviesan mora, de forma que se pueda negociar una soluciÃ³n y evitar que el caso siga escalando sin una ruta definida.

## DescripciÃ³n general

Durante la gestiÃ³n de mora se pueden ofrecer cuatro tipos de alivio: abono parcial, congelamiento de intereses, condonaciÃ³n y refinanciaciÃ³n. Los tres primeros tienen reglas mÃ¡s claras y estÃ¡n documentados en Reglas de Negocio; la refinanciaciÃ³n, en cambio, se mantiene como una opciÃ³n pendiente de definir por negocio porque no existen condiciones completas en las fuentes revisadas.

## Actores involucrados

- Cliente: solicita o acepta una alternativa de alivio.
- Cobranza y cartera: evalÃºan la propuesta y definen la ruta de negociaciÃ³n.
- ComitÃ© de Cartera: recibe los casos de refinanciaciÃ³n o escalamiento.
- Negocio: define las condiciones definitivas de la refinanciaciÃ³n.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.

![Journey Colpatria B2B — página 10](../journeys-imagenes/page-10.png)

## Explicación del Journey

1. IdentificaciÃ³n del caso en mora
   - QuÃ© sucede: el cliente presenta retrasos de pago y entra en un proceso de negociaciÃ³n.
   - QuÃ© actor interviene: cobranza y cliente.
   - QuÃ© sistema participa: registros de cartera y seguimiento.
   - QuÃ© informaciÃ³n se utiliza: estado de mora y comportamiento de pago.
   - QuÃ© decisiÃ³n se toma: si es viable ofrecer un alivio.
   - QuÃ© ocurre si el resultado es positivo: se evalÃºa la propuesta.
   - QuÃ© ocurre si el resultado es negativo: el caso sigue con la gestiÃ³n ordinaria.

2. EvaluaciÃ³n del tipo de alivio
   - QuÃ© sucede: la cartera define si corresponde abono parcial, congelamiento, condonaciÃ³n o refinanciaciÃ³n.
   - QuÃ© actor interviene: cobranza y cartera.
   - QuÃ© sistema participa: gestiÃ³n de cartera y documentos de negociaciÃ³n.
   - QuÃ© informaciÃ³n se utiliza: saldo, antigÃ¼edad y capacidad de pago del cliente.
   - QuÃ© decisiÃ³n se toma: si se ofrece una alternativa de alivio.
   - QuÃ© ocurre si el resultado es positivo: se acuerda la soluciÃ³n.
   - QuÃ© ocurre si el resultado es negativo: se mantiene la ruta de cobranza.

3. Acuerdo o escalamiento
   - QuÃ© sucede: el alivio se concreta o se eleva al ComitÃ© de Cartera cuando no existe una polÃ­tica completa.
   - QuÃ© actor interviene: comitÃ© de cartera y negocio.
   - QuÃ© sistema participa: registro y seguimiento de acuerdos.
   - QuÃ© informaciÃ³n se utiliza: tÃ©rminos de la negociaciÃ³n y polÃ­tica vigente.
   - QuÃ© decisiÃ³n se toma: si se aprueba o no el alivio.
   - QuÃ© ocurre si el resultado es positivo: se cierra la negociaciÃ³n.
   - QuÃ© ocurre si el resultado es negativo: se mantiene la gestiÃ³n de cobranza o se reevalÃºa el caso.

## Reglas de negocio

- Se pueden ofrecer cuatro tipos de alivio: abono parcial, congelaciÃ³n de intereses, condonaciÃ³n y refinanciaciÃ³n.
- Abono parcial, congelamiento y condonaciÃ³n cuentan con reglas mÃ¡s claras documentadas en [Reglas Negocio](../reglas-negocio/03-alivios-negociacion.md).
- La refinanciaciÃ³n debe escalarse al ComitÃ© de Cartera hasta que negocio defina sus condiciones.

## Entradas

- Caso en mora y estado del cliente.
- Historial de pagos y capacidad de pago del cliente.
- Reglas de negocio vigentes sobre alivios.

## Salidas

- Acuerdo de alivio o negociaciÃ³n.
- EscalaciÃ³n al comitÃ© de cartera cuando aplica.
- ContinuaciÃ³n o cierre del caso de cobranza.

## Excepciones

- El cliente no necesita o no acepta un alivio.
- La refinanciaciÃ³n no puede ofrecerse sin condiciones claras.
- El caso no puede resolver con un alivio y debe continuar a cobranza.

## Consideraciones

- La refinanciaciÃ³n sigue siendo una opciÃ³n pendiente de definir por negocio.
- El detalle de condiciones de abono parcial, congelamiento y condonaciÃ³n estÃ¡ en [Reglas Negocio](../reglas-negocio/03-alivios-negociacion.md).

## Pendientes de validaciÃ³n

> **Pendiente de validar con el dueÃ±o del proceso.** Las condiciones concretas de refinanciaciÃ³n deben definirse con negocio y cartera.

