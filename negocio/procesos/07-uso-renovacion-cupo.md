# 7. Uso y renovaciÃ³n del cupo

[â† Volver a Procesos](README.md)

| Documento | Uso y renovaciÃ³n del cupo |
|-----------|------------------------------|
| **Proyecto** | Fliipa |
| **VersiÃ³n** | 2.1 |
| **Estado** | Borrador para validaciÃ³n |
| **Responsable** | Riesgo y crÃ©dito |
| **Ãšltima actualizaciÃ³n** | 2026-07-13 |

---

## Control de versiones

| VersiÃ³n | Fecha | Autor | DescripciÃ³n |
|---------|-------|-------|-------------|
| 1.0 | 2026-07-09 | MarÃ­a Fernanda Herazo  | VersiÃ³n inicial, como secciÃ³n 7 del `procesos.md` original (monolÃ­tico). |
| 2.0 | 2026-07-13 | MarÃ­a Fernanda Herazo  | ReorganizaciÃ³n en archivo independiente con diagrama Mermaid, dentro del split de `negocio/procesos/`. |
| 2.1 | 2026-07-13 | MarÃ­a Fernanda Herazo | Se valida contra la pÃ¡gina 8 de `Journeys Fran finales.pdf`: el contenido ya era correcto, sin cambios de flujo. Se agrega esta tabla de control de versiones y la referencia cruzada a [06-dispersion-fondos.md](06-dispersion-fondos.md), que documenta la misma decisiÃ³n de renovaciÃ³n dentro del flujo de dispersiÃ³n. |

## Objetivo

Definir si un cliente califica para recibir un nuevo cupo despuÃ©s de usar el bono y cumplir con el comportamiento esperado de pago.

## DescripciÃ³n general

Una vez el cliente usa el bono en D1 y paga su crÃ©dito, se evalÃºa si la relaciÃ³n continua y si existe capacidad de cupo disponible para otorgar una renovaciÃ³n. La decisiÃ³n final depende de dos condiciones: buen comportamiento de pago y disponibilidad de cupo.

## Actores involucrados

- Cliente: usa el bono y paga el crÃ©dito.
- D1: registra el uso del bono y confirma el consumo.
- Riesgo y crÃ©dito: evalÃºa la renovaciÃ³n del cupo.
- Sistema: ejecuta la decisiÃ³n de renovaciÃ³n y actualiza el estado del cupo.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 8](../journeys-imagenes/page-08.png)

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

## Consideraciones

- Esta decisiÃ³n tambiÃ©n aparece en [06-dispersion-fondos.md](06-dispersion-fondos.md), porque el flujo de dispersiÃ³n y el flujo de renovaciÃ³n comparten el mismo punto de decisiÃ³n.
- La polÃ­tica exacta de renovaciÃ³n debe mantenerse alineada con negocio y riesgo.

## Pendientes de validaciÃ³n

> **Pendiente de validar con el dueÃ±o del proceso.** La regla exacta de renovaciÃ³n del cupo y los criterios de disponibilidad deben confirmarse con negocio y riesgo.

## Fuentes consultadas

- `Journeys Fran finales.pdf` (Journeys Colpatria B2B, junio 2026), pÃ¡gina 8 ("Flujo de dispersiÃ³n", swimlane Cliente)

