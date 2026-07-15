# 5. Firma de contrato y activaciÃ³n

[â† Volver a Procesos](README.md)

| Documento | Firma de contrato y activaciÃ³n |
|-----------|----------------------------------|
| **Proyecto** | Fliipa |
| **VersiÃ³n** | 2.1 |
| **Estado** | Borrador para validaciÃ³n |
| **Responsable** | Riesgo y crÃ©dito |
| **Ãšltima actualizaciÃ³n** | 2026-07-13 |

---

## Control de versiones

| VersiÃ³n | Fecha | Autor | DescripciÃ³n |
|---------|-------|-------|-------------|
| 1.0 | 2026-07-09 | MarÃ­a Fernanda Herazo | VersiÃ³n inicial, como secciÃ³n 5 del `procesos.md` original (monolÃ­tico). |
| 2.0 | 2026-07-13 | MarÃ­a Fernanda Herazo  | ReorganizaciÃ³n en archivo independiente con diagrama Mermaid, dentro del split de `negocio/procesos/`. |
| 2.1 | 2026-07-13 | MarÃ­a Fernanda Herazo  | CorrecciÃ³n solicitada tras validar contra las pÃ¡ginas 5 y 6 de `Journeys Fran finales.pdf`: se agrega el arranque del proceso (habilitaciÃ³n del crÃ©dito, solicitud de continuar la firma, link por correo); se corrige el orden â€” el cliente **acepta condiciones** (resumen general) antes de que el sistema muestre el detalle y el cliente **lea el contrato y el pagarÃ©** (paso nuevo de junio 2026), no al revÃ©s; se agregan las bifurcaciones de PIN olvidado y de cÃ³digo de verificaciÃ³n fallido; se agregan los pasos finales de notificaciÃ³n del bono y visualizaciÃ³n del cÃ³digo, que faltaban antes de "se aprueba el crÃ©dito". |

## Objetivo

Completar la firma del contrato y activar el crÃ©dito de forma que el cliente pueda recibir el bono D1 y usar el cupo aprobado.

## DescripciÃ³n general

El proceso inicia cuando el crÃ©dito ya fue aprobado y el core bancario habilita la firma. Luego se solicita al cliente continuar con la firma, se le envÃ­a un link por correo y se valida su identidad con NIT y PIN. DespuÃ©s de aceptar condiciones, revisar el contrato y el pagarÃ©, y validar un cÃ³digo de verificaciÃ³n, se generan los documentos firmados, se asigna el bono D1 y se notifica al cliente para que pueda ver el cÃ³digo y usar el cupo.

## Actores involucrados

- Cliente empresarial: completa la firma, acepta condiciones y valida el cÃ³digo de verificaciÃ³n.
- Core bancario y core de crÃ©dito-originaciÃ³n: habilitan el crÃ©dito y validan la aprobaciÃ³n.
- Sistema de firma y activaciÃ³n: gestiona el link, el PIN, la firma y la activaciÃ³n del bono.
- D1: recibe el bono y habilita su uso.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 5](../journeys-imagenes/page-05.png)

![Journey Colpatria B2B â€” pÃ¡gina 6](../journeys-imagenes/page-06.png)

- PÃ¡ginas 5 y 6 del journey Colpatria B2B (junio 2026): firma del contrato, pagarÃ©, validaciÃ³n y activaciÃ³n del bono.
- Fuente visual de respaldo para validar la secuencia documentada en este proceso.

## Explicación del Journey

1. HabilitaciÃ³n del crÃ©dito por el core bancario
   - QuÃ© sucede: el crÃ©dito aprobado queda habilitado para la firma.
   - QuÃ© actor interviene: core bancario y core de crÃ©dito-originaciÃ³n.
   - QuÃ© sistema participa: core bancario.
   - QuÃ© informaciÃ³n se utiliza: aprobaciÃ³n del crÃ©dito y estado del caso.
   - QuÃ© decisiÃ³n se toma: si el crÃ©dito estÃ¡ listo para continuar.
   - QuÃ© ocurre si el resultado es positivo: se solicita al cliente continuar la firma.
   - QuÃ© ocurre si el resultado es negativo: la firma no inicia.

2. Solicitud de continuaciÃ³n de la firma
   - QuÃ© sucede: se contacta al cliente por correo, mensaje o llamada para continuar con la firma.
   - QuÃ© actor interviene: sistema y cliente.
   - QuÃ© sistema participa: canal de notificaciÃ³n.
   - QuÃ© informaciÃ³n se utiliza: estado del crÃ©dito aprobado.
   - QuÃ© decisiÃ³n se toma: si el cliente acepta seguir el proceso.
   - QuÃ© ocurre si el resultado es positivo: el cliente recibe el link.
   - QuÃ© ocurre si el resultado es negativo: la firma queda pendiente o se cancela.

3. RecepciÃ³n del link por correo
   - QuÃ© sucede: el cliente accede al link de continuaciÃ³n.
   - QuÃ© actor interviene: cliente empresarial.
   - QuÃ© sistema participa: correo y web de firma.
   - QuÃ© informaciÃ³n se utiliza: correo del cliente e identificaciÃ³n del caso.
   - QuÃ© decisiÃ³n se toma: si el cliente entra a la firma.
   - QuÃ© ocurre si el resultado es positivo: se solicita NIT y PIN.
   - QuÃ© ocurre si el resultado es negativo: no se inicia la firma.

4. ValidaciÃ³n de NIT y PIN
   - QuÃ© sucede: el cliente ingresa su NIT y PIN de seguridad para confirmar su identidad.
   - QuÃ© actor interviene: cliente empresarial y sistema.
   - QuÃ© sistema participa: autenticaciÃ³n de la cuenta.
   - QuÃ© informaciÃ³n se utiliza: NIT y PIN.
   - QuÃ© decisiÃ³n se toma: si la identidad del cliente es vÃ¡lida.
   - QuÃ© ocurre si el resultado es positivo: entra a la bienvenida y a la revisiÃ³n de condiciones.
   - QuÃ© ocurre si el resultado es negativo: puede pasar a soporte si olvidÃ³ el PIN.

5. RecuperaciÃ³n de PIN
   - QuÃ© sucede: si el cliente olvidÃ³ el PIN, se deriva al canal de soporte.
   - QuÃ© actor interviene: cliente empresarial y soporte.
   - QuÃ© sistema participa: canal de soporte.
   - QuÃ© informaciÃ³n se utiliza: identidad del cliente y acceso a la cuenta.
   - QuÃ© decisiÃ³n se toma: si se reanuda la firma luego de recuperar el acceso.
   - QuÃ© ocurre si el resultado es positivo: se retoma el proceso de firma.
   - QuÃ© ocurre si el resultado es negativo: la firma no continÃºa.

6. PresentaciÃ³n de condiciones generales y detalle del crÃ©dito
   - QuÃ© sucede: el sistema presenta el monto aprobado, las condiciones generales y el detalle del crÃ©dito.
   - QuÃ© actor interviene: sistema y cliente.
   - QuÃ© sistema participa: aplicaciÃ³n de firma.
   - QuÃ© informaciÃ³n se utiliza: monto, plan de pagos, valor, fecha, tasa y vigencia del cupo.
   - QuÃ© decisiÃ³n se toma: si el cliente acepta las condiciones.
   - QuÃ© ocurre si el resultado es positivo: se pasa al contrato y pagarÃ©.
   - QuÃ© ocurre si el resultado es negativo: el proceso se detiene o se cancela.

7. Lectura del contrato y el pagarÃ©
   - QuÃ© sucede: el cliente revisa los documentos legales y financieros para dar continuidad.
   - QuÃ© actor interviene: cliente empresarial.
   - QuÃ© sistema participa: vista de documentos legales.
   - QuÃ© informaciÃ³n se utiliza: contrato, pagarÃ© y condiciones del crÃ©dito.
   - QuÃ© decisiÃ³n se toma: si el cliente estÃ¡ listo para firmar.
   - QuÃ© ocurre si el resultado es positivo: se avanza a la verificaciÃ³n por cÃ³digo.
   - QuÃ© ocurre si el resultado es negativo: la firma queda pendiente.

8. VerificaciÃ³n por cÃ³digo
   - QuÃ© sucede: se envÃ­a un cÃ³digo de verificaciÃ³n al correo y el cliente lo ingresa.
   - QuÃ© actor interviene: sistema y cliente.
   - QuÃ© sistema participa: envÃ­o de cÃ³digo y validaciÃ³n.
   - QuÃ© informaciÃ³n se utiliza: correo del cliente y cÃ³digo recibido.
   - QuÃ© decisiÃ³n se toma: si la verificaciÃ³n es correcta.
   - QuÃ© ocurre si el resultado es positivo: se generan los documentos firmados.
   - QuÃ© ocurre si el resultado es negativo: se deriva a servicio al cliente.

9. GeneraciÃ³n de documentos firmados y activaciÃ³n del bono
   - QuÃ© sucede: se generan contrato y pagarÃ© firmados, se asigna el bono D1 y se notifica al cliente.
   - QuÃ© actor interviene: sistema, D1 y cliente.
   - QuÃ© sistema participa: generaciÃ³n de documentos y activaciÃ³n del bono.
   - QuÃ© informaciÃ³n se utiliza: contrato firmado y estado de aprobaciÃ³n del crÃ©dito.
   - QuÃ© decisiÃ³n se toma: si el crÃ©dito queda aprobado y operativo.
   - QuÃ© ocurre si el resultado es positivo: el cliente puede ver el cÃ³digo del bono y usarlo.
   - QuÃ© ocurre si el resultado es negativo: se interrumpe la activaciÃ³n o se requiere soporte.

## Reglas de negocio

- El crÃ©dito debe estar habilitado por el core bancario antes de iniciar la firma.
- El cliente debe validar su identidad con NIT y PIN antes de continuar.
- El cliente debe aceptar las condiciones generales antes de revisar el detalle del crÃ©dito.
- El cliente debe leer el contrato y el pagarÃ© antes de firmar.
- El cÃ³digo de verificaciÃ³n es un requisito para completar la firma.

## Entradas

- CrÃ©dito aprobado y habilitado.
- Datos del cliente y acceso a la cuenta.
- InformaciÃ³n del monto, plan de pagos, tasa y fecha de corte.
- Correo del cliente para recibir el link y el cÃ³digo.

## Salidas

- Contrato y pagarÃ© firmados.
- Bono D1 asignado y notificado al cliente.
- CrÃ©dito aprobado y listo para uso del cupo.

## Excepciones

- El cliente olvida el PIN y no puede continuar.
- El cÃ³digo de verificaciÃ³n falla.
- El cliente no acepta las condiciones o no completa la lectura del contrato.
- La firma no se completa por error de integraciÃ³n o de sistema.
- Se detecta un problema en la activaciÃ³n del bono.

## Consideraciones

- El proceso incorpora el detalle del contrato y el pagarÃ© como parte de la experiencia de firma.
- El bono D1 se asigna despuÃ©s de la firma y se hace visible en la cuenta del cliente.
- El flujo de activaciÃ³n se conecta con el uso del cupo y con la recepciÃ³n del bono.

## Pendientes de validaciÃ³n

> **Pendiente de validar con el dueÃ±o del proceso.** La polÃ­tica exacta de activaciÃ³n del bono y la experiencia final de visualizaciÃ³n del cÃ³digo deben confirmarse con negocio y tecnologÃ­a.

