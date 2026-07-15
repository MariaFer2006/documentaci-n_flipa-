# 3. ValidaciÃ³n de identidad (KYC)

## Objetivo

Validar la identidad del cliente y completar la informaciÃ³n necesaria para que el caso pueda avanzar a evaluaciÃ³n de riesgo y originaciÃ³n.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 3](../journeys-imagenes/page-03.png)

- PÃ¡gina 3 del journey Colpatria B2B (junio 2026): biometrÃ­a, cuenta bancaria y validaciÃ³n de identidad.
- Fuente visual de respaldo para validar la secuencia documentada en este proceso.

## Explicación del Journey

1. EnvÃ­o del link de biometrÃ­a
   - QuÃ© sucede: el cliente recibe una invitaciÃ³n para completar la validaciÃ³n biomÃ©trica con Olimpia.
   - QuÃ© actor interviene: cliente empresarial y proveedor Olimpia.
   - QuÃ© sistema participa: canal de biometrÃ­a y flujo de onboarding.
   - QuÃ© informaciÃ³n se utiliza: datos del cliente y enlace de verificaciÃ³n.
   - QuÃ© decisiÃ³n se toma: si se inicia la validaciÃ³n.
   - QuÃ© ocurre si el resultado es positivo: continÃºa el proceso.
   - QuÃ© ocurre si el resultado es negativo: se termina el proceso o se notifica el caso.

2. Resultado de la biometrÃ­a
   - QuÃ© sucede: el sistema o el proveedor informa si la biometrÃ­a fue exitosa, rechazada o queda en revisiÃ³n.
   - QuÃ© actor interviene: proveedor Olimpia y sistema.
   - QuÃ© sistema participa: integraciÃ³n con biometrÃ­a.
   - QuÃ© informaciÃ³n se utiliza: resultado de la validaciÃ³n biomÃ©trica.
   - QuÃ© decisiÃ³n se toma: si se continÃºa, se revisa manualmente o se detiene.
   - QuÃ© ocurre si el resultado es positivo: se continÃºa con la vinculaciÃ³n de cuenta bancaria.
   - QuÃ© ocurre si el resultado es negativo: el proceso se detiene o se deriva a revisiÃ³n manual.

3. RevisiÃ³n manual por analista de riesgo
   - QuÃ© sucede: el caso queda en revisiÃ³n para validar identidad o fraude.
   - QuÃ© actor interviene: analista de riesgo.
   - QuÃ© sistema participa: flujo de casos en revisiÃ³n.
   - QuÃ© informaciÃ³n se utiliza: resultado de biometrÃ­a y contexto del cliente.
   - QuÃ© decisiÃ³n se toma: si se aprueba o rechaza el caso.
   - QuÃ© ocurre si el resultado es positivo: se continÃºa con el flujo.
   - QuÃ© ocurre si el resultado es negativo: se notifica el rechazo y se finaliza el proceso.

4. VinculaciÃ³n de cuenta bancaria
   - QuÃ© sucede: si la biometrÃ­a fue exitosa o aprobada, se vincula la cuenta bancaria para dÃ©bito automÃ¡tico.
   - QuÃ© actor interviene: cliente empresarial y sistema.
   - QuÃ© sistema participa: integraciÃ³n con Druo.
   - QuÃ© informaciÃ³n se utiliza: cuenta bancaria del cliente y estado de la biometrÃ­a.
   - QuÃ© decisiÃ³n se toma: si la cuenta puede integrarse al proceso.
   - QuÃ© ocurre si el resultado es positivo: se avanza a documentaciÃ³n bancaria.
   - QuÃ© ocurre si el resultado es negativo: el proceso queda bloqueado o requiere correcciÃ³n.

5. CertificaciÃ³n bancaria y extractos
   - QuÃ© sucede: se adjunta la certificaciÃ³n bancaria y los extractos de los Ãºltimos 3 meses.
   - QuÃ© actor interviene: cliente empresarial.
   - QuÃ© sistema participa: captura documental y carga de archivos.
   - QuÃ© informaciÃ³n se utiliza: informaciÃ³n bancaria y estados de cuenta.
   - QuÃ© decisiÃ³n se toma: si la informaciÃ³n es suficiente para continuar.
   - QuÃ© ocurre si el resultado es positivo: se pasa a la selecciÃ³n de localidad.
   - QuÃ© ocurre si el resultado es negativo: se solicita informaciÃ³n adicional.

6. SelecciÃ³n de localidad habitual
   - QuÃ© sucede: el cliente selecciona la localidad donde realiza sus compras habituales.
   - QuÃ© actor interviene: cliente empresarial.
   - QuÃ© sistema participa: formulario de onboarding.
   - QuÃ© informaciÃ³n se utiliza: datos de negocio y contexto comercial.
   - QuÃ© decisiÃ³n se toma: si la informaciÃ³n de localidad es vÃ¡lida.
   - QuÃ© ocurre si el resultado es positivo: se envÃ­a la informaciÃ³n al asesor.
   - QuÃ© ocurre si el resultado es negativo: se solicita corregir o completar.

7. EnvÃ­o a asesor para anÃ¡lisis de crÃ©dito
   - QuÃ© sucede: la informaciÃ³n se comparte con el asesor para el anÃ¡lisis de crÃ©dito.
   - QuÃ© actor interviene: asesor y sistema.
   - QuÃ© sistema participa: flujo de asignaciÃ³n y envÃ­o de informaciÃ³n.
   - QuÃ© informaciÃ³n se utiliza: datos de KYC, cuenta bancaria y localidad.
   - QuÃ© decisiÃ³n se toma: si el caso continÃºa a evaluaciÃ³n de riesgo automatizada.
   - QuÃ© ocurre si el resultado es positivo: se espera respuesta en 2 dÃ­as.
   - QuÃ© ocurre si el resultado es negativo: el caso se detiene o requiere revisiÃ³n adicional.

8. ContinuaciÃ³n a evaluaciÃ³n de riesgo
   - QuÃ© sucede: el proceso pasa a la evaluaciÃ³n automatizada de riesgo.
   - QuÃ© actor interviene: sistema de riesgo.
   - QuÃ© sistema participa: motor de evaluaciÃ³n de riesgo.
   - QuÃ© informaciÃ³n se utiliza: datos convalidados del KYC.
   - QuÃ© decisiÃ³n se toma: si se aprueba o rechaza el crÃ©dito.
   - QuÃ© ocurre si el resultado es positivo: continÃºa el proceso de originaciÃ³n.
   - QuÃ© ocurre si el resultado es negativo: el cliente recibe notificaciÃ³n de rechazo.

## Reglas de negocio

- La biometrÃ­a es un paso obligatorio para avanzar con la validaciÃ³n de identidad.
- La cuenta bancaria solo se vincula si la biometrÃ­a fue exitosa o aprobada manualmente.
- La certificaciÃ³n bancaria y los extractos de 3 meses deben adjuntarse para completar el KYC.
- El analista de riesgo interviene solo cuando la biometrÃ­a queda en revisiÃ³n.
- El proceso avanza a evaluaciÃ³n de riesgo automatizada despuÃ©s del envÃ­o al asesor.

## Entradas

- Link de biometrÃ­a enviado por el sistema.
- Datos del cliente y del representante legal.
- Cuenta bancaria para dÃ©bito automÃ¡tico.
- CertificaciÃ³n bancaria y extractos de los Ãºltimos 3 meses.
- InformaciÃ³n de localidad habitual.

## Salidas

- Caso de KYC validado o rechazado.
- InformaciÃ³n completa enviada al asesor para anÃ¡lisis de crÃ©dito.
- Continuidad al proceso de evaluaciÃ³n de riesgo automatizada.

## Excepciones

- La biometrÃ­a es rechazada.
- La biometrÃ­a queda en revisiÃ³n y requiere aprobaciÃ³n manual.
- La vinculaciÃ³n de la cuenta bancaria falla.
- La informaciÃ³n documental es incompleta.
- El caso no alcanza la evaluaciÃ³n de riesgo por falta de datos o por rechazo manual.

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso.**

