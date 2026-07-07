# Alcance del Producto

| **Documento** | Alcance del Producto |
|--------------|----------------------|
| **Proyecto** | Flipa |
| **Versión** | 1.0 |
| **Estado** | En revisión |
| **Responsable** | Equipo de Producto |
| **Última actualización** | 2026-07-07 |

---

# Control de versiones

| Versión | Fecha | Autor | Descripción |
|----------|------------|-------------------------|--------------------------------------------|
| 1.0 | 2026-07-07 | María Fernanda Herazo | Creación inicial del documento. |

---

# Propósito

Definir el alcance funcional y de negocio del producto durante su primera fase de implementación, estableciendo los procesos, funcionalidades e integraciones que hacen parte del Producto Mínimo Viable (MVP), así como las capacidades que serán desarrolladas en fases posteriores.

Este documento sirve como referencia para la toma de decisiones de producto, arquitectura, desarrollo y priorización del roadmap.

---

# Objetivo

Delimitar el alcance del MVP para validar el modelo de crédito empresarial basado en datos transaccionales, permitiendo ofrecer una solución financiera escalable, sostenible y alineada con los objetivos estratégicos del negocio.

---

# Contexto

Flipa es una plataforma de crédito rotativo B2B orientada a micro y pequeñas empresas que realizan compras frecuentes en D1.

El modelo busca ampliar el acceso al crédito formal mediante el uso de información transaccional y comportamiento comercial, disminuyendo la dependencia exclusiva del historial financiero tradicional.

La primera etapa busca validar la viabilidad del modelo de negocio, la aceptación del mercado y la efectividad del modelo de riesgo.

---

# Alcance del MVP

La primera versión del producto comprende los siguientes procesos de negocio.

## 1. Captación comercial

Incluye:

- Contacto inicial con clientes preaprobados.
- Campañas por correo electrónico.
- Campañas por WhatsApp.
- Contacto telefónico.
- Gestión del interés del cliente.
- Seguimiento comercial.

---

## 2. Onboarding digital

Incluye:

- Acceso mediante enlace único.
- Validación del NIT.
- Registro del representante legal.
- Validación mediante OTP.
- Aceptación de términos y condiciones.
- Registro de ubicación.
- Configuración del PIN de seguridad.
- Vinculación de cuenta bancaria.
- Cargue de certificación bancaria.
- Cargue de extractos bancarios.

---

## 3. Validación de identidad

Incluye:

- Biometría mediante proveedor externo.
- Validación automática del resultado.
- Gestión de casos en revisión.
- Rechazo automático cuando corresponda.

---

## 4. Evaluación del riesgo

Incluye:

- Consulta de Experian.
- Consulta de RUES.
- Consulta del historial transaccional D1.
- Evaluación automática de reglas de negocio.
- Cálculo del cupo aprobado.
- Validación de capacidad de endeudamiento.

---

## 5. Originación del crédito

Incluye:

- Aprobación del crédito.
- Comunicación del cupo aprobado.
- Generación del contrato.
- Firma digital.
- Generación del pagaré.
- Activación del cupo.

---

## 6. Administración del crédito

Incluye:

- Cupo rotativo.
- Consulta del estado del crédito.
- Consulta del plan de pagos.
- Consulta del saldo.
- Liberación automática del cupo cuando el crédito es cancelado.

---

## 7. Uso del crédito

Incluye:

- Generación del bono D1.
- Compra en tiendas D1.
- Bloqueo del cupo remanente.
- Evaluación para renovación del cupo.

---

## 8. Gestión de pagos

Incluye:

- Débito automático mediante Druo.
- Pago por PSE.
- Prepago.
- Actualización del saldo.
- Liquidación del crédito.

---

## 9. Cobranza

Incluye:

- Reintentos automáticos de débito.
- Recordatorios de pago.
- Bloqueo del cupo.
- Acuerdos de pago.
- Reestructuración.
- Reporte a centrales de riesgo.
- Cobro jurídico.
- Castigo de cartera.

---

## 10. Servicio al cliente

Incluye:

- Atención mediante IA.
- Escalamiento a agentes humanos.
- Atención por WhatsApp.
- Atención por correo electrónico.
- Atención telefónica.
- Gestión de PQRS.
- Medición de satisfacción (NPS y CSAT).

---

## 11. Portal administrativo

Incluye:

- Consulta de clientes.
- Consulta de solicitudes.
- Gestión del proceso crediticio.
- Consulta de resultados del análisis.
- Seguimiento del estado del crédito.
- Administración del proceso.

---

# Integraciones incluidas

El MVP contempla integración con:

| Sistema | Propósito |
|----------|-----------|
| D1 | Información transaccional y uso del bono |
| Experian | Consulta de riesgo |
| RUES | Validación empresarial |
| Druo | Débito automático |
| Olimpia | Biometría |
| Correo electrónico | Notificaciones |
| WhatsApp | Comunicación con clientes |
| SMS | OTP |
| Core Bancario | Originación del crédito |

---

# Fuera del alcance

No forman parte del MVP:

- Aplicación móvil nativa.
- Productos de ahorro.
- Productos de inversión.
- Tarjetas de crédito.
- Seguros.
- Marketplace financiero.
- Fidelización.
- Múltiples perfiles administrativos.
- Gestión completa de oficinas.
- Productos para personas naturales.
- Analítica avanzada basada en IA.
- Automatizaciones no relacionadas con el proceso de crédito.

---

# Restricciones

Durante la primera versión:

- El producto estará dirigido únicamente a clientes empresariales.
- El crédito podrá utilizarse únicamente en D1.
- Solo existirá un portal administrativo.
- El proceso estará enfocado en validar el modelo de negocio antes de escalar la operación.

---

# Criterios de priorización

Las funcionalidades serán priorizadas cuando aporten a alguno de los siguientes objetivos:

| Prioridad | Objetivo |
|-----------|-----------|
| Alta | Validar el modelo de negocio. |
| Alta | Reducir fraude. |
| Alta | Disminuir el riesgo crediticio. |
| Alta | Mejorar la experiencia del cliente. |
| Alta | Aumentar el uso del crédito. |
| Alta | Garantizar la sostenibilidad financiera. |
| Media | Optimizar procesos internos. |
| Baja | Funcionalidades de mejora continua. |

---

# Beneficios esperados

La implementación del alcance definido permitirá:

- Facilitar el acceso al crédito empresarial.
- Incrementar la recurrencia de compra en D1.
- Aumentar el ticket promedio.
- Evaluar el riesgo mediante datos transaccionales.
- Disminuir el fraude.
- Construir historial crediticio para pequeñas empresas.
- Validar un modelo financiero escalable para futuras etapas.

---

# Exclusiones

Este documento no describe:

- Arquitectura de software.
- APIs.
- Modelo de datos.
- Casos de uso.
- Historias de usuario.
- Reglas de negocio detalladas.
- Manuales de usuario.
- Casos de prueba.

Cada uno de estos temas se desarrolla en la documentación correspondiente.

---

# Documentos relacionados

- [Producto](README.md)
- [Objetivo](objetivo.md)
- [Visión](vision.md)
- [Roadmap](roadmap.md)
- [Negocio](../negocio/README.md)
- [Funcional](../funcional/README.md)
- [Conocimiento](../conocimiento/README.md)
- [Mapa del Conocimiento](../MAPA_DEL_CONOCIMIENTO.md)
