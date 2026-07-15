# 11. Servicio al cliente

[â† Volver a Procesos](README.md)

| Documento | Servicio al cliente |
|-----------|------------------------|
| **Proyecto** | Fliipa |
| **VersiÃ³n** | 2.1 |
| **Estado** | Borrador para validaciÃ³n |
| **Responsable** | Servicio al cliente / Riesgo |
| **Ãšltima actualizaciÃ³n** | 2026-07-13 |

---

## Control de versiones

| VersiÃ³n | Fecha | Autor | DescripciÃ³n |
|---------|-------|-------|-------------|
| 1.0 | 2026-07-09 | MarÃ­a Fernanda Herazo (con asistencia de Claude) | VersiÃ³n inicial, como secciÃ³n 11 del `procesos.md` original (monolÃ­tico). |
| 2.0 | 2026-07-13 | MarÃ­a Fernanda Herazo (con asistencia de Claude) | ReorganizaciÃ³n en archivo independiente con diagrama Mermaid, dentro del split de `negocio/procesos/`. |
| 2.1 | 2026-07-13 | MarÃ­a Fernanda Herazo (con asistencia de Claude) | CorrecciÃ³n de fondo tras validar contra la pÃ¡gina 9 de `Journeys Fran finales.pdf`: la decisiÃ³n final no es binaria "caso crÃ­tico vs. legal/PQR" â€” es un enrutamiento de 3 salidas (resoluciÃ³n autÃ³noma, escalaciÃ³n a un Ã¡rea responsable, o legal/PQR). La validaciÃ³n de identidad para casos crÃ­ticos se reubica como una acciÃ³n previa del agente al recibir el caso, no como una salida alternativa a "Legal/PQR". Se agregan los nombres de las Ã¡reas de escalaciÃ³n (riesgo, cobranza, TI). |

## Objetivo

Atender los casos del cliente de forma rÃ¡pida y responsable, resolviendo de primera lÃ­nea o derivando correctamente a las Ã¡reas competentes cuando el tema requiere intervenciÃ³n humana.

## DescripciÃ³n general

Todo caso del cliente puede llegar por WhatsApp, correo o llamada outbound. El asistente virtual intenta resolverlo en primer contacto; si no lo logra, un agente humano recibe el caso con contexto y decide si se resuelve de forma autÃ³noma, se escalada a riesgo, cobranza o TI, o se deriva a legal/PQR. Los casos crÃ­ticos requieren validaciÃ³n de identidad y aprobaciÃ³n manual antes de avanzar.

## Actores involucrados

- Cliente: reporta el caso y recibe la respuesta final.
- IA: clasifica y trata de resolver el caso en primer contacto.
- Agente humano: recibe el caso, valida identidad en casos crÃ­ticos y decide el enrutamiento.
- Ãreas internas: riesgo, cobranza y TI, ademÃ¡s de legal/PQR cuando aplica.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 9](../journeys-imagenes/page-09.png)

- PÃ¡gina 9 del journey Colpatria B2B (junio 2026): servicio al cliente, IA de primer nivel y escalamiento humano.
- Fuente visual de respaldo para validar la secuencia documentada en este proceso.

## Explicación del Journey

1. Contacto del cliente
   - QuÃ© sucede: el cliente reporta un caso por WhatsApp, correo o llamada outbound.
   - QuÃ© actor interviene: cliente.
   - QuÃ© sistema participa: canal de contacto y portal administrativo.
   - QuÃ© informaciÃ³n se utiliza: descripciÃ³n del caso y contexto del cliente.
   - QuÃ© decisiÃ³n se toma: si el caso entra al proceso de servicio al cliente.
   - QuÃ© ocurre si el resultado es positivo: el caso se registra y se clasifica.
   - QuÃ© ocurre si el resultado es negativo: no se genera un caso.

2. Primer contacto con la IA
   - QuÃ© sucede: la IA clasifica el caso e intenta resolverlo en primer contacto.
   - QuÃ© actor interviene: IA.
   - QuÃ© sistema participa: motor de clasificaciÃ³n y respuesta.
   - QuÃ© informaciÃ³n se utiliza: contexto del caso, historial y reglas de respuesta.
   - QuÃ© decisiÃ³n se toma: si la IA resuelve o no el reclamo.
   - QuÃ© ocurre si el resultado es positivo: se cierra el caso.
   - QuÃ© ocurre si el resultado es negativo: se escapa al agente humano.

3. RevisiÃ³n humana del caso
   - QuÃ© sucede: un agente humano recibe el caso con contexto y valida identidad si se trata de un caso crÃ­tico.
   - QuÃ© actor interviene: agente humano.
   - QuÃ© sistema participa: portal administrativo.
   - QuÃ© informaciÃ³n se utiliza: contexto del caso y verificaciÃ³n de identidad.
   - QuÃ© decisiÃ³n se toma: si el caso es estÃ¡ndar, crÃ­tico o legal/PQR.
   - QuÃ© ocurre si el resultado es positivo: se resuelve o se enruta.
   - QuÃ© ocurre si el resultado es negativo: se mantiene en espera o se escalada a la Ã¡rea responsable.

4. Enrutamiento final
   - QuÃ© sucede: el caso se resuelve de forma autÃ³noma, se deriva a riesgo/cobranza/TI o se envÃ­a a legal/PQR.
   - QuÃ© actor interviene: agente humano y Ã¡reas internas.
   - QuÃ© sistema participa: enrutamiento del caso y SLA.
   - QuÃ© informaciÃ³n se utiliza: tipo de caso y nivel de impacto.
   - QuÃ© decisiÃ³n se toma: quÃ© Ã¡rea asume la respuesta.
   - QuÃ© ocurre si el resultado es positivo: el cliente recibe la soluciÃ³n.
   - QuÃ© ocurre si el resultado es negativo: se mantiene en seguimiento.

## Reglas de negocio

- Todo caso debe registrarse en el portal administrativo.
- La IA intenta resolver el caso en primer contacto.
- Los casos crÃ­ticos requieren validaciÃ³n de identidad y aprobaciÃ³n manual.
- El enrutamiento final puede ser resoluciÃ³n autÃ³noma, escalaciÃ³n a riesgo/cobranza/TI o legal/PQR.

## Entradas

- Caso reportado por WhatsApp, correo o llamada outbound.
- Contexto del cliente y del problema.
- Reglas de clasificaciÃ³n y routing del servicio.

## Salidas

- Caso resuelto o derivado.
- Respuesta al cliente con soluciÃ³n o seguimiento.
- Cierre del caso en el admin con mÃ©tricas NPS/CSAT.

## Excepciones

- El caso no lo resuelve la IA y debe pasar a agente humano.
- El caso es crÃ­tico y requiere validaciÃ³n de identidad.
- El caso corresponde a legal/PQR y necesita SLA inmediato.
- Se detecta un fraude o uso indebido de cupo.

## Consideraciones

- El asistente virtual es una funcionalidad de largo plazo, pero el proceso ya contempla su uso en primer contacto.
- La decisiÃ³n de enrutar el caso a riesgo, cobranza o TI debe mantenerse alineada con la estructura interna.

## Pendientes de validaciÃ³n

> **Pendiente de validar con el dueÃ±o del proceso.** La polÃ­tica exacta de escalaciÃ³n y los SLAs de legal/PQR deben confirmarse con operaciones y servicio al cliente.

## Fuentes consultadas

- `Journeys Fran finales.pdf` (Journeys Colpatria B2B, junio 2026), pÃ¡gina 9 ("Servicio al cliente", swimlanes Cliente / IA / Agente humano / Ãreas internas)

