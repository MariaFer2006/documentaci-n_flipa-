# Manual Usuario

## Objetivo

Servir como guía de referencia para que el **Cliente empresarial** (dueño o representante del comercio afiliado) use la cuenta Fliipa sin asistencia: ingresar de forma segura, entender y aceptar las condiciones de su crédito, firmar el contrato, y usar su código de compra en tiendas D1.

## Alcance

Incluye únicamente las pantallas orientadas al comercio (front-end de cliente): ingreso, activación del cupo de crédito, firma del contrato y uso del código de compra. No cubre el panel administrativo interno de Fliipa (ver [Manual Administrador](manual-administrador.md)) ni los procesos internos de aprobación, evaluación de riesgo o cobranza (ver `funcional/` y `negocio/` en la biblioteca de conocimiento).

## Responsable

Pendiente de asignación

## Fecha de actualización

2026-08-04

## Estado

Borrador — generado a partir de capturas de pantalla del flujo real (10 pantallas).

## Documentos relacionados

- [Manuales](README.md)
- [Flipa - Biblioteca de Conocimiento](../README.md)
- [Mapa Del Conocimiento](../MAPA_DEL_CONOCIMIENTO.md)
- [Onboarding](../ONBOARDING.md)
- [Convenciones](../CONVENCIONES.md)
- [Qa](../qa/README.md)
- [Producto](../producto/README.md)
- [Manual Administrador](manual-administrador.md)
- [Onboarding](onboarding.md)
- [Negocio/Actores](../negocio/Actores/README.md)

## Contenido

### 1. Actores

| Actor | Rol en este manual |
|---|---|
| **Cliente empresarial** | Micro o pequeña empresa afiliada (ej. *Tienda Express S.A.S.*) que solicita y usa el crédito. Es quien realiza cada acción descrita en este manual: inicia sesión, acepta condiciones, firma el contrato y usa el código de compra. |
| **Fliipa** | Equipo interno (de Sumz) que desarrolla y opera la plataforma de crédito: define las reglas de negocio, aprueba el cupo y opera el soporte al que se redirige el comercio cuando olvida su PIN. |
| **D1** | Aliado comercial. No participa en la operación del crédito ni en la cobranza; es la cadena de tiendas donde el comercio redime su cupo con el código único de compra. |

> Fuente: `negocio/Actores/02-actores-principales.md`

### 2. Flujo general cubierto en este manual

1. Ingreso a la cuenta (NIT + PIN) y recuperación de PIN.
2. Onboarding y aceptación de condiciones del cupo aprobado.
3. Revisión del plan de pagos del crédito.
4. Firma del contrato vía código enviado por WhatsApp.
5. Uso del código de compra en el dashboard para redimir el cupo en tiendas D1.

**Convención usada en este documento:** cada captura de pantalla incluye recuadros rojos numerados sobre cada botón, campo o enlace interactivo. La tabla debajo de la imagen explica, en el mismo orden, qué hace ese elemento y qué acción se espera del comercio.

**Nota sobre los datos de ejemplo:** las capturas usan un comercio ficticio (*Tienda Express S.A.S.*) con montos de ejemplo (p. ej. $1.800.000 y $2.000.000 en distintas pantallas). Son datos ilustrativos del flujo, no valores fijos del producto.

---

### Pantalla 1 de 10 — Ingreso: Identificación por NIT

*Paso 1: el comercio se identifica con el NIT de su negocio*

![Pantalla 1 - Ingreso por NIT](manual-usuario-imagenes/01-login-nit.png)

| # | Elemento | Qué hace / qué debe hacer el comercio |
|---|---|---|
| 1 | Cerrar (X) | Cierra la ventana de ingreso y regresa a la página anterior, sin iniciar sesión. |
| 2 | Campo NIT del negocio | El comercio digita el NIT de su negocio (sin el dígito de verificación). Con este dato Fliipa identifica que es un cliente empresarial ya afiliado/preaprobado. |
| 3 | Botón Continuar | Valida el NIT contra la base de clientes afiliados y, si existe, avanza a la pantalla de ingreso con PIN (Pantalla 2). |

---

### Pantalla 2 de 10 — Ingreso: Autenticación con PIN

*Paso 2: el comercio confirma su identidad con un PIN de 4 dígitos*

![Pantalla 2 - Ingreso con PIN](manual-usuario-imagenes/02-login-pin.png)

| # | Elemento | Qué hace / qué debe hacer el comercio |
|---|---|---|
| 1 | Cerrar (X) | Cierra la ventana de ingreso sin autenticarse. |
| 2 | Campo de PIN | El comercio digita su PIN numérico (4 dígitos) creado previamente para su cuenta. |
| 3 | Mostrar / ocultar PIN | Alterna entre ver el PIN en texto plano o mantenerlo oculto, para escribirlo con seguridad en lugares públicos. |
| 4 | Botón Ingresar | Valida el PIN y, si es correcto, da acceso al dashboard de la cuenta Fliipa. |
| 5 | Olvidaste tu PIN | Enlace que lleva al flujo de recuperación de PIN cuando el comercio no lo recuerda (Pantalla 3). |

---

### Pantalla 3 de 10 — Recuperación de PIN

*Modal que aparece al presionar "Olvidaste tu ¿PIN?"*

![Pantalla 3 - Recuperar PIN](manual-usuario-imagenes/03-recuperar-pin.png)

| # | Elemento | Qué hace / qué debe hacer el comercio |
|---|---|---|
| 1 | Cerrar (X) | Cierra el modal sin iniciar la recuperación; regresa a la pantalla de PIN. |
| 2 | Botón Ir al chat | Redirige al canal de soporte de Fliipa (chat/WhatsApp). Allí un agente ayuda al comercio a asignar un nuevo PIN de ingreso. |

> Este paso depende de un canal externo de soporte; no se resuelve automáticamente dentro de la app.

---

### Pantalla 4 de 10 — Bienvenida y activación del crédito

*Onboarding · 15% completado*

![Pantalla 4 - Bienvenida](manual-usuario-imagenes/04-bienvenida.png)

| # | Elemento | Qué hace / qué debe hacer el comercio |
|---|---|---|
| 1 | Encabezado del comercio | Muestra el nombre del negocio y su NIT (ej. "Tienda Express S.A.S. · NIT 52456842-1"). Confirma la cuenta activa; se mantiene visible durante todo el onboarding. |
| 2 | Barra de progreso (15%) | Indica el avance dentro del flujo de activación del crédito, que tiene varios pasos hasta llegar al 100% (firma del contrato). |
| 3 | Botón Entendido | Confirma que el comercio leyó el mensaje de bienvenida y avanza a la pantalla de condiciones del cupo aprobado (Pantalla 5). |

---

### Pantalla 5 de 10 — Cupo aprobado y condiciones

*Onboarding · 50% completado*

![Pantalla 5 - Cupo aprobado](manual-usuario-imagenes/05-cupo-condiciones.png)

| # | Elemento | Qué hace / qué debe hacer el comercio |
|---|---|---|
| 1 | Encabezado del comercio | Nombre del negocio y NIT (igual que en la pantalla anterior). |
| 2 | Barra de progreso (50%) | El comercio avanzó a la mitad del proceso de activación. |
| 3 | Tarjeta Cupo aprobado | Panel informativo (no es un botón) con el monto de crédito preaprobado y las condiciones de uso: solo en tiendas D1, número de cuotas, mejora de score, y congelamiento del cupo por mora. |
| 4 | Botón Aceptar condiciones | El comercio confirma que entiende y acepta las condiciones generales del crédito, y avanza al plan de pagos (Pantalla 6). |

---

### Pantalla 6 de 10 — Plan de pagos

*Onboarding · 70% completado*

![Pantalla 6 - Plan de pagos](manual-usuario-imagenes/06-plan-pagos.png)

| # | Elemento | Qué hace / qué debe hacer el comercio |
|---|---|---|
| 1 | Encabezado del comercio | Nombre del negocio y NIT. |
| 2 | Barra de progreso (70%) | El comercio avanzó a la revisión del plan de pagos. |
| 3 | Cambiar día de pago | Enlace que permite ajustar la fecha mensual en la que se cobrará cada cuota del crédito. |
| 4 | Botón Estoy de acuerdo | Confirma la tasa de interés efectiva anual, que la cuota ya incluye intereses y cargos administrativos, y que el cupo quedará disponible de inmediato. Avanza a la firma del contrato (Pantalla 7). |

---

### Pantalla 7 de 10 — Firma de contrato

*Onboarding · 90% completado*

![Pantalla 7 - Firma de contrato](manual-usuario-imagenes/07-firma-contrato.png)

| # | Elemento | Qué hace / qué debe hacer el comercio |
|---|---|---|
| 1 | Flecha atrás | Regresa a la pantalla anterior del flujo (plan de pagos) sin firmar. |
| 2 | Cerrar (X) | Cierra el flujo de firma sin completar el proceso. |
| 3 | Casillas del código de verificación | El comercio digita el código de 4 dígitos que Fliipa envía por WhatsApp, para confirmar que es él quien firma. |
| 4 | Reenviar código | Solicita un nuevo envío del código por WhatsApp si no llegó o ya expiró. |
| 5 | Ver contrato | Abre el documento completo del contrato para revisarlo antes de firmar. |
| 6 | Botón Firmar contrato | Firma electrónicamente el contrato, formalizando el crédito por el monto y las condiciones ya aceptadas. Con esto el cupo queda disponible en la cuenta. |

> ⚠️ **Nota para el equipo:** el texto del botón en esta captura aún dice "Firmar contrato y pagaré" y la tarjeta menciona "Contrato digital y pagaré". Si el pagaré ya no aplica al producto, conviene actualizar también esos textos en la interfaz para que coincidan con este manual.

---

### Pantalla 8 de 10 — Cuenta Fliipa: cargando

*Pantalla de carga del panel principal (dashboard)*

![Pantalla 8 - Dashboard cargando](manual-usuario-imagenes/08-dashboard-cargando.png)

| # | Elemento | Qué hace / qué debe hacer el comercio |
|---|---|---|
| 1 | Cerrar sesión | Permite al comercio salir de su cuenta Fliipa desde cualquier pantalla del dashboard. |

> Los bloques grises son un estado de "carga" (skeleton) mientras el dashboard trae la información del cupo y el código de compra (ver Pantalla 9).

---

### Pantalla 9 de 10 — Código para compras

*Panel principal — uso del cupo aprobado*

![Pantalla 9 - Código para compras](manual-usuario-imagenes/09-codigo-compras.png)

| # | Elemento | Qué hace / qué debe hacer el comercio |
|---|---|---|
| 1 | Cerrar sesión | Cierra la sesión de la cuenta Fliipa. |
| 2 | Botón Ver código | Revela el código único de compra, oculto por defecto (con puntos) por seguridad. El comercio debe verlo justo antes de pagar en caja (ver Pantalla 10). |
| 3 | Pagar cuota | Lleva al flujo externo/asociado para pagar la cuota mensual del crédito vigente. |

> Los pasos "¿Cómo usar tu cupo?" (1. Visita una tienda D1, 2. Avisa al cajero, 3. Realiza tu mercado) son instrucciones informativas, no botones.

---

### Pantalla 10 de 10 — Código revelado

*Advertencia de seguridad al mostrar el código*

![Pantalla 10 - Código revelado](manual-usuario-imagenes/10-codigo-revelado.png)

| # | Elemento | Qué hace / qué debe hacer el comercio |
|---|---|---|
| 1 | Botón Cerrar | Cierra el aviso "Cuida tu código" y deja visible el código de compra en el dashboard, listo para compartir con el cajero de D1. |

> El código (ej. A1B2C3D4) representa todo el valor del cupo aprobado: el comercio no debe compartirlo por canales distintos al pago en caja, para evitar que otra persona lo use.

---

### 3. Buenas prácticas para el comercio

- No compartir el PIN ni el código de compra por canales distintos al pago en caja de D1.
- Revisar el contrato completo (enlace "Ver contrato") antes de firmar.
- Confirmar el día de pago de las cuotas y ajustarlo si no se acomoda al flujo de caja del negocio.
- Usar el chat de soporte ante cualquier problema de acceso (PIN olvidado, código no visible, etc.).
- Mantener los pagos al día: el cupo se congela si hay atrasos, según las condiciones aceptadas.

### Pendiente de completar

- Nombre del responsable del documento.
- Capturas de los flujos de pago de cuota y de actualización de datos del negocio (no incluidos en el set de imágenes recibido).
- Validación de este manual con el equipo de soporte de Fliipa.
- Actualizar el texto "pagaré" que aún aparece en la interfaz real (Pantalla 7), para que coincida con el flujo vigente sin pagaré.
