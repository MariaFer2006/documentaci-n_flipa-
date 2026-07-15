# 2. Onboarding digital

## Objetivo

Registrar al cliente empresarial en la plataforma de Fliipa y preparar el recorrido de origen del crÃ©dito para que pueda avanzar a validaciÃ³n de identidad y riesgo.

## Journey

El recorrido se explica a continuación en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 2](imagenes/page-02.png)

- PÃ¡gina 2 del journey Colpatria B2B (junio 2026): onboarding, NIT/CC, ubicaciÃ³n y OTP.
- Fuente visual de respaldo para validar la secuencia documentada en este proceso.

## Explicación paso a paso
 
**A — Ingresa su correo y recibe el link único de invitación (Sendgrid/Zenvia).** El cliente escribe su correo electrónico y recibe a vuelta de correo un enlace de invitación individual e intransferible. Es el disparador del proceso; no hay decisión de negocio en este paso.
 
**B — Abre el link único e ingresa su NIT o cédula.** Al abrir el enlace, el cliente escribe su NIT (empresa) o su cédula de ciudadanía (persona natural). Este dato alimenta la identificación del cupo preaprobado en el paso siguiente.
 
**C — Sistema identifica el cupo preaprobado según consumo en D1.** Paso automático, sin intervención humana: el sistema Fliipa recupera o calcula el cupo preaprobado del cliente con base en criterios de consumo previamente definidos en D1.
 
**D — Ingresa ubicación (ciudad y dirección).** El cliente registra dónde opera su negocio. No hay validación automática documentada sobre la veracidad de esta dirección en este paso (se verifica más adelante, en el control de riesgo operativo).
 
**E — ¿Tipo de cliente: NIT o CC? (decisión).** El sistema clasifica al cliente según el identificador ingresado en el paso B.
- *Si es CC:* pasa al paso F (reconocimiento de representante legal, con validación interna contra la base de datos) antes de aceptar términos.
- *Si es NIT:* pasa directamente al paso G (acepta términos), sin ese reconocimiento.
- > Pendiente de validar con el dueño del proceso: confirmar si esta asignación de ramas (CC confirma representante legal / NIT no) es la correcta, o si están intercambiadas frente a la intención original del journey.
**F — Reconoce que es el representante legal (validación interna contra la BD).** *(Solo en la rama documentada para clientes CC.)* El cliente confirma explícitamente esa condición, y el sistema lo valida internamente contra su base de datos, antes de continuar a la aceptación de términos.
 
**G — Acepta términos y condiciones.** El cliente da su consentimiento explícito a los términos y condiciones del producto. Ambas ramas (con o sin el paso F) confluyen aquí.
 
**H — Provee información personal del representante legal (cédula y teléfono).** El cliente completa los datos personales necesarios para continuar: cédula y número de teléfono.
 
**I — Sistema envía código OTP para validar el teléfono.** El sistema (vía Zenvia) envía un código de un solo uso al teléfono registrado.
 
**J — Cliente inserta código OTP (decisión).**
- *Fallido:* el cliente puede solicitar el reenvío del código, y el sistema vuelve a enviarlo (regresa al paso I). > Pendiente de validar con el dueño del proceso: no hay un límite documentado de reintentos.
- *Exitoso:* continúa al paso K.
**K — Sistema envía código de verificación al correo.** Como segunda validación de identidad de contacto, el sistema envía un código al correo electrónico del cliente (vía Sendgrid).
 
**L — Cliente ingresa el código; el sistema lo verifica.** El cliente escribe el código recibido y el sistema confirma su validez antes de continuar.
 
**M — Crea su PIN de seguridad de 4 dígitos.** El cliente define un PIN de 4 dígitos que usará como mecanismo de seguridad dentro de la plataforma.
 
**N — Cuenta de Socio D1 creada.** Con el PIN definido, el sistema crea formalmente la cuenta de Socio D1 del cliente.
 
**O — Continúa a validación de identidad / KYC.** Con el onboarding completo, el proceso pasa a [Validación de identidad (KYC)](03-validacion-kyc.md).
 
## Reglas de negocio
 
- El onboarding debe completarse mediante un enlace único e individual por cliente (no genérico).
- El cupo preaprobado se calcula a partir de criterios de consumo en D1, no de una evaluación de riesgo tradicional en este paso.
- La clasificación del cliente como NIT o CC determina si pasa o no por el reconocimiento de representante legal antes de aceptar términos (dirección de la regla pendiente de confirmar; ver nota en el paso E).
- La aceptación de términos y condiciones es un paso obligatorio y no puede omitirse, para ambos tipos de cliente.
- La validación del teléfono mediante OTP es obligatoria, y el código puede reenviarse si falla.
- Existe una segunda validación de identidad de contacto por código de correo, adicional al OTP de teléfono.
- El PIN de seguridad tiene 4 dígitos y lo define el propio cliente.
- La cuenta de Socio D1 se crea únicamente después de completar ambas validaciones (teléfono y correo) y el PIN.
- Los datos de contacto (teléfono y correo) deben quedar registrados, ya que se validan mensualmente como control de riesgo operativo (ver [Reglas Negocio — Control de riesgo operativo](../reglas-negocio/05-control-riesgo-operativo.md)).
## Entradas
 
- Correo electrónico del cliente.
- Enlace de invitación individual.
- NIT o cédula de ciudadanía del cliente.
- Ubicación (ciudad y dirección) del negocio.
- Datos personales del representante legal (cédula, teléfono).
- Código OTP y código de verificación por correo.
- PIN de seguridad definido por el cliente.
## Salidas
 
- Cliente clasificado como NIT o CC, con cupo preaprobado identificado.
- Teléfono y correo validados.
- Cuenta de Socio D1 creada.
- Solicitud lista para continuar a validación de identidad (KYC).
## Excepciones
 
- El código OTP no llega o el cliente lo ingresa incorrectamente varias veces. > Pendiente de validar con el dueño del proceso (límite de reintentos no documentado).
- El código de verificación por correo no llega o es incorrecto. > Pendiente de validar con el dueño del proceso.
- El cliente abandona el proceso antes de crear el PIN o la cuenta de Socio D1. > Pendiente de validar con el dueño del proceso.
- El cliente no acepta los términos y condiciones: el proceso no puede continuar (inferido, no documentado explícitamente qué ocurre con el registro parcial).
- Dirección de la bifurcación NIT/CC en el paso E (ver nota). > Pendiente de validar con el dueño del proceso.
## Consideraciones
 
- El diseño del proceso prioriza la velocidad: la meta es completarlo en unos 3 minutos, lo que limita la cantidad de fricciones y validaciones manuales en este punto.
- La identificación del cupo preaprobado en este paso es preliminar; el cupo definitivo se confirma en la evaluación de riesgo (proceso 4), no aquí.
- El paso de creación del PIN (M) también aparece listado en [03-validacion-kyc.md](03-validacion-kyc.md). Según el journey, el PIN se crea antes de la biometría, como parte de este mismo tramo de onboarding: se recomienda quitarlo de `03-validacion-kyc.md` para no duplicarlo, dejando ese documento enfocado en biometría, cuenta bancaria y documentos.
- El proceso depende de dos proveedores externos de notificaciones (Sendgrid, Zenvia); una falla en cualquiera de los dos puede bloquear el cierre del onboarding para el cliente afectado.
## Notas
 
- La *duración aproximada de 3 minutos* es una referencia de diseño y puede variar según el dispositivo o la conexión del cliente.
- El *cupo preaprobado* identificado aquí es preliminar y puede ajustarse en la evaluación de riesgo posterior.
- No hay un número documentado de *reintentos permitidos* para el código OTP; este parámetro podría definirse o cambiar con el tiempo.
- La *dirección de la bifurcación NIT/CC* (cuál tipo de cliente confirma representante legal) está documentada tal como aparece en el journey fuente, pero se marca como pendiente de confirmar por resultar contraintuitiva.
## Fuentes consultadas
 
- `Journeys Fran finales.pdf` (Journeys Colpatria B2B, junio 2026), páginas 2 y 3 — swimlanes "Cliente" y "Web"
- Integraciones técnicas — Sendgrid y Zenvia (`tecnico/Integraciones/`)
- Alcance del Producto (`producto/alcance.md`)
 
