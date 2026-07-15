# 2. Onboarding digital

## Objetivo

Registrar al cliente empresarial en la plataforma de Fliipa y preparar el recorrido de origen del crÃ©dito para que pueda avanzar a validaciÃ³n de identidad y riesgo.

## Journey

El recorrido se explica a continuaciÃ³n en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.



![Journey Colpatria B2B â€” pÃ¡gina 2](../journeys-imagenes/page-02.png)

- PÃ¡gina 2 del journey Colpatria B2B (junio 2026): onboarding, NIT/CC, ubicaciÃ³n y OTP.
- Fuente visual de respaldo para validar la secuencia documentada en este proceso.

## Explicación del Journey

1. InvitaciÃ³n por correo
   - QuÃ© sucede: el cliente recibe el link Ãºnico de invitaciÃ³n y accede a la plataforma.
   - QuÃ© actor interviene: cliente empresarial.
   - QuÃ© sistema participa: envÃ­o de correos y enlace Ãºnico.
   - QuÃ© informaciÃ³n se utiliza: correo del cliente y enlace de acceso.
   - QuÃ© decisiÃ³n se toma: si el cliente accede para iniciar el registro.
   - QuÃ© ocurre si el resultado es positivo: continÃºa con la captura de datos.
   - QuÃ© ocurre si el resultado es negativo: no se inicia el onboarding.

2. IdentificaciÃ³n del cupo preaprobado
   - QuÃ© sucede: el sistema asocia la solicitud a la capacidad de crÃ©dito disponible segÃºn el consumo en D1.
   - QuÃ© actor interviene: sistema de onboarding.
   - QuÃ© sistema participa: motor de identificaciÃ³n del cupo.
   - QuÃ© informaciÃ³n se utiliza: consumo histÃ³rico en D1 y datos del cliente.
   - QuÃ© decisiÃ³n se toma: si el cliente cuenta con un cupo preaprobado.
   - QuÃ© ocurre si el resultado es positivo: se continÃºa con el registro.
   - QuÃ© ocurre si el resultado es negativo: el proceso queda bloqueado o se descarta.

3. Registro de ubicaciÃ³n
   - QuÃ© sucede: se captura la ciudad y la direcciÃ³n del cliente.
   - QuÃ© actor interviene: cliente empresarial.
   - QuÃ© sistema participa: formulario de registro.
   - QuÃ© informaciÃ³n se utiliza: ubicaciÃ³n del negocio o del representante legal.
   - QuÃ© decisiÃ³n se toma: si la informaciÃ³n de ubicaciÃ³n es suficiente.
   - QuÃ© ocurre si el resultado es positivo: se avanza al tipo de cliente.
   - QuÃ© ocurre si el resultado es negativo: se solicita completar la informaciÃ³n.

4. ClasificaciÃ³n por tipo de cliente
   - QuÃ© sucede: el sistema define si el caso corresponde a un NIT o a un cliente con cÃ©dula/CC.
   - QuÃ© actor interviene: sistema y cliente.
   - QuÃ© sistema participa: validaciÃ³n interna contra la base de datos.
   - QuÃ© informaciÃ³n se utiliza: tipo de identificaciÃ³n y registro de la persona.
   - QuÃ© decisiÃ³n se toma: si el cliente es el representante legal.
   - QuÃ© ocurre si el resultado es positivo: se continÃºa con la captura de datos personales.
   - QuÃ© ocurre si el resultado es negativo: se requiere revisar la informaciÃ³n o detener el proceso.

5. AceptaciÃ³n de tÃ©rminos y captura de datos personales
   - QuÃ© sucede: el cliente acepta tÃ©rminos y proporciona datos del representante legal.
   - QuÃ© actor interviene: cliente empresarial.
   - QuÃ© sistema participa: formulario de onboarding.
   - QuÃ© informaciÃ³n se utiliza: cÃ©dula, telÃ©fono y datos de contacto.
   - QuÃ© decisiÃ³n se toma: si la informaciÃ³n es suficiente para avanzar.
   - QuÃ© ocurre si el resultado es positivo: el sistema pasa a la validaciÃ³n telefÃ³nica.
   - QuÃ© ocurre si el resultado es negativo: se solicita completar la informaciÃ³n faltante.

6. ValidaciÃ³n OTP del telÃ©fono
   - QuÃ© sucede: el sistema envÃ­a un cÃ³digo OTP para verificar el telÃ©fono del usuario.
   - QuÃ© actor interviene: sistema y cliente.
   - QuÃ© sistema participa: servicio de envÃ­o y validaciÃ³n OTP.
   - QuÃ© informaciÃ³n se utiliza: nÃºmero de telÃ©fono capturado.
   - QuÃ© decisiÃ³n se toma: si el cÃ³digo es correcto.
   - QuÃ© ocurre si el resultado es positivo: se continÃºa con la verificaciÃ³n por correo.
   - QuÃ© ocurre si el resultado es negativo: se puede reenviar el cÃ³digo.

7. VerificaciÃ³n por correo
   - QuÃ© sucede: se envÃ­a un cÃ³digo de verificaciÃ³n al correo y el cliente lo ingresa para confirmar la cuenta.
   - QuÃ© actor interviene: sistema y cliente.
   - QuÃ© sistema participa: servicio de verificaciÃ³n por correo.
   - QuÃ© informaciÃ³n se utiliza: correo del cliente y cÃ³digo recibido.
   - QuÃ© decisiÃ³n se toma: si la verificaciÃ³n es vÃ¡lida.
   - QuÃ© ocurre si el resultado es positivo: se procede a la creaciÃ³n del PIN.
   - QuÃ© ocurre si el resultado es negativo: se solicita volver a intentar.

8. CreaciÃ³n del PIN de seguridad
   - QuÃ© sucede: el cliente crea un PIN de 4 dÃ­gitos para proteger su cuenta.
   - QuÃ© actor interviene: cliente empresarial.
   - QuÃ© sistema participa: creaciÃ³n de credenciales de acceso.
   - QuÃ© informaciÃ³n se utiliza: selecciÃ³n del PIN por parte del usuario.
   - QuÃ© decisiÃ³n se toma: si el PIN cumple con los requisitos de uso.
   - QuÃ© ocurre si el resultado es positivo: se habilita la cuenta de socio D1.
   - QuÃ© ocurre si el resultado es negativo: se solicita crear uno nuevo.

9. CreaciÃ³n de la cuenta de socio D1
   - QuÃ© sucede: se crea la cuenta de socio y el flujo queda listo para continuar a KYC.
   - QuÃ© actor interviene: sistema.
   - QuÃ© sistema participa: proceso de registro de usuario.
   - QuÃ© informaciÃ³n se utiliza: datos ya validados del cliente.
   - QuÃ© decisiÃ³n se toma: si la cuenta queda activa para avanzar.
   - QuÃ© ocurre si el resultado es positivo: el proceso continÃºa a validaciÃ³n de identidad.
   - QuÃ© ocurre si el resultado es negativo: la cuenta no queda activa y el proceso se interrumpe.

## Reglas de negocio

- El onboarding debe iniciar con un link Ãºnico enviado al correo del cliente.
- El sistema identifica el cupo preaprobado segÃºn el consumo en D1.
- La validaciÃ³n del telÃ©fono se realiza mediante OTP.
- La verificaciÃ³n del correo es necesaria antes de crear la cuenta.
- El PIN de seguridad se crea como parte del registro inicial del socio D1.

## Entradas

- Correo del cliente.
- IdentificaciÃ³n del cliente (NIT o cÃ©dula).
- InformaciÃ³n de ubicaciÃ³n y datos del representante legal.
- Historial de consumo en D1 para identificar el cupo preaprobado.

## Salidas

- Cuenta de socio D1 creada.
- Datos de onboarding validados y disponibles para la siguiente etapa de KYC.
- Cliente habilitado para avanzar a validaciÃ³n de identidad y riesgo.

## Excepciones

- El cliente no recibe o no usa el link de invitaciÃ³n.
- El cÃ³digo OTP falla o no llega.
- La informaciÃ³n de identidad o ubicaciÃ³n es incompleta.
- La validaciÃ³n interna contra la base de datos no confirma al representante legal.
- La cuenta no se activa correctamente y el proceso se detiene.

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso.**

