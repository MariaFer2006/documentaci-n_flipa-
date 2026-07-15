# 4. EvaluaciÃ³n de riesgo

[â† Volver a Procesos](README.md)

| Documento | EvaluaciÃ³n de riesgo |
|-----------|------------------------|
| **Proyecto** | Fliipa |
| **VersiÃ³n** | 2.1 |
| **Estado** | Borrador para validaciÃ³n |
| **Responsable** | Riesgo y crÃ©dito |
| **Ãšltima actualizaciÃ³n** | 2026-07-13 |

---

## Control de versiones

| VersiÃ³n | Fecha | Autor | DescripciÃ³n |
|---------|-------|-------|-------------|
| 1.0 | 2026-07-09 | MarÃ­a Fernanda Herazo| VersiÃ³n inicial, como secciÃ³n 4 del `procesos.md` original (monolÃ­tico). |
| 2.0 | 2026-07-13 | MarÃ­a Fernanda Herazo  | ReorganizaciÃ³n en archivo independiente con diagrama Mermaid, dentro del split de `negocio/procesos/`. |
| 2.1 | 2026-07-13 | MarÃ­a Fernanda Herazo | CorrecciÃ³n solicitada tras validar contra la pÃ¡gina 4 de `Journeys Fran finales.pdf` (Journeys Colpatria B2B, junio 2026): se separa la evaluaciÃ³n de criterios de KYC (score, endeudamiento, tienda habitual â€” "reglas de Colpatria") de la validaciÃ³n de la cuenta bancaria contra Experian, como dos decisiones **consecutivas** en el orden correcto (antes aparecÃ­an fusionadas en una sola decisiÃ³n y en el orden invertido). Se agrega el paso inicial de apertura del caso y la cita explÃ­cita a "reglas de Colpatria".

## Objetivo

Determinar si el cliente cumple con los criterios de riesgo para aprobar, ajustar o rechazar el crÃ©dito antes de continuar a la firma de contrato.

## DescripciÃ³n general

El proceso empieza cuando el caso es abierto en el admin y el sistema consulta Experian y el histÃ³rico transaccional de D1. Luego evalÃºa automÃ¡ticamente los criterios de KYC con base en las reglas de Colpatria y decide si el cliente cumple con el score mÃ­nimo, la capacidad de endeudamiento y la tienda habitual. Si pasa esa primera validaciÃ³n, se revisa la cuenta bancaria reportada en Experian. Si la cuenta es vÃ¡lida, se aprueba o ajusta el cupo; si no, se rechaza el crÃ©dito y se emite una alarma.

## Actores involucrados

- Sistema de riesgo: ejecuta la evaluaciÃ³n automatizada y toma la decisiÃ³n inicial.
- Experian y D1: aportan la informaciÃ³n de score, historial y cuenta bancaria.
- Cliente empresarial: recibe la notificaciÃ³n de aprobaciÃ³n o rechazo.
- Admin: abre el caso y da entrada al proceso.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 4](../journeys-imagenes/page-04.png)

- PÃ¡gina 4 del journey Colpatria B2B (junio 2026): evaluaciÃ³n de riesgo, Experian, score y cupo.
- Fuente visual de respaldo para validar la secuencia documentada en este proceso.

## Explicación del Journey

1. Apertura del caso
   - QuÃ© sucede: el caso se recibe y se abre en el admin para iniciar la evaluaciÃ³n.
   - QuÃ© actor interviene: admin y sistema.
   - QuÃ© sistema participa: mÃ³dulo de administraciÃ³n del caso.
   - QuÃ© informaciÃ³n se utiliza: solicitud del cliente y datos bÃ¡sicos del caso.
   - QuÃ© decisiÃ³n se toma: si el caso entra a evaluaciÃ³n.
   - QuÃ© ocurre si el resultado es positivo: se continÃºa con la consulta de datos.
   - QuÃ© ocurre si el resultado es negativo: el caso no entra al proceso.

2. Consulta a Experian y al histÃ³rico de D1
   - QuÃ© sucede: el sistema consulta la informaciÃ³n de riesgo y transaccional del cliente.
   - QuÃ© actor interviene: sistema de riesgo.
   - QuÃ© sistema participa: Experian y fuente transaccional de D1.
   - QuÃ© informaciÃ³n se utiliza: score, historial y datos del cliente.
   - QuÃ© decisiÃ³n se toma: si existe suficiente informaciÃ³n para evaluar.
   - QuÃ© ocurre si el resultado es positivo: se avanza a criterios de KYC.
   - QuÃ© ocurre si el resultado es negativo: el caso queda incompleto o se rechaza.

3. EvaluaciÃ³n de criterios de KYC
   - QuÃ© sucede: el sistema valida score mÃ­nimo, capacidad de endeudamiento y tienda habitual con base en reglas de Colpatria.
   - QuÃ© actor interviene: sistema.
   - QuÃ© sistema participa: motor de reglas de Colpatria.
   - QuÃ© informaciÃ³n se utiliza: score, endeudamiento y tienda habitual declarada.
   - QuÃ© decisiÃ³n se toma: si el cliente pasa el gate 1.
   - QuÃ© ocurre si el resultado es positivo: se continÃºa con la validaciÃ³n de cuenta bancaria.
   - QuÃ© ocurre si el resultado es negativo: se rechaza el crÃ©dito y se emite alarma.

4. ValidaciÃ³n de cuenta bancaria en Experian
   - QuÃ© sucede: se valida si la cuenta bancaria reportada coincide con productos reportados y es vÃ¡lida.
   - QuÃ© actor interviene: sistema.
   - QuÃ© sistema participa: Experian.
   - QuÃ© informaciÃ³n se utiliza: cuenta bancaria y reportes asociados.
   - QuÃ© decisiÃ³n se toma: si la cuenta supera el gate 2.
   - QuÃ© ocurre si el resultado es positivo: se aprueba o ajusta el cupo.
   - QuÃ© ocurre si el resultado es negativo: se rechaza el crÃ©dito.

5. DecisiÃ³n final de aprobaciÃ³n o rechazo
   - QuÃ© sucede: el sistema define si el crÃ©dito se aprueba, ajusta o rechaza.
   - QuÃ© actor interviene: sistema y cliente.
   - QuÃ© sistema participa: motor de decisiÃ³n de crÃ©dito.
   - QuÃ© informaciÃ³n se utiliza: resultados de los gates 1 y 2.
   - QuÃ© decisiÃ³n se toma: si el caso continÃºa a firma de contrato.
   - QuÃ© ocurre si el resultado es positivo: se avanza a la siguiente etapa.
   - QuÃ© ocurre si el resultado es negativo: el cliente recibe notificaciÃ³n de rechazo.

## Reglas de negocio

- La evaluaciÃ³n de riesgo es automÃ¡tica y no depende de revisiÃ³n manual del analista.
- Se deben validar tres criterios de KYC: score mÃ­nimo, capacidad de endeudamiento y tienda habitual.
- La cuenta bancaria debe validar contra productos reportados en Experian.
- Si alguno de los gates no se cumple, el crÃ©dito se rechaza.
- Si el cliente aprueba los gates, el cupo se aprueba o ajusta y se continÃºa a firma de contrato.

## Entradas

- Solicitud abierta en el admin.
- Datos de riesgo de Experian.
- HistÃ³rico transaccional de D1.
- InformaciÃ³n de la cuenta bancaria del cliente.

## Salidas

- DecisiÃ³n de aprobaciÃ³n, ajuste o rechazo del crÃ©dito.
- Cupo aprobado o ajustado para la etapa siguiente.
- NotificaciÃ³n de rechazo al cliente cuando aplica.

## Excepciones

- El cliente no cumple con el score mÃ­nimo o la capacidad de endeudamiento.
- La tienda habitual no coincide con el histÃ³rico de D1.
- La cuenta bancaria no es vÃ¡lida o no coincide con los reportes.
- El sistema no encuentra suficiente informaciÃ³n para evaluar.
- La decisiÃ³n final obliga a rechazar el crÃ©dito.

## Consideraciones

- La evaluaciÃ³n se ajusta a la lÃ³gica de junio de 2026 en la que se elimina el estudio manual del analista.
- La etapa de riesgo estÃ¡ conectada con la validaciÃ³n de identidad y con la firma del contrato.
- Se recomienda mantener alineadas las reglas de riesgo con la documentaciÃ³n de negocio y funcional.

## Pendientes de validaciÃ³n

> **Pendiente de validar con el dueÃ±o del proceso.** La regla exacta de score y capacidad de endeudamiento debe confirmarse con negocio y riesgo.

