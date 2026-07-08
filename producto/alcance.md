# Alcance del Producto

| Documento | Alcance del Producto |
|------------|----------------------|
| **Proyecto** | Fliipa |
| **Versión** | 1.1 |
| **Estado** | En revisión |
| **Responsable** | Equipo de Producto |
| **Última actualización** | 2026-07-08 |

---

# Control de versiones

| Versión | Fecha | Autor | Descripción |
|---------|-------|--------|-------------|
| 1.0 | 2026-07-07 | María Fernanda Herazo | Creación inicial del documento. |
| 1.1 | 2026-07-08 | María Fernanda Herazo | Corrección del nombre del producto, detalle del proceso de validación biométrica e hipervínculos|

---

# Propósito

Definir el alcance funcional y de negocio del producto durante su primera fase de implementación, estableciendo los procesos, funcionalidades e integraciones que hacen parte del Producto Mínimo Viable (MVP), así como las capacidades que serán desarrolladas en fases posteriores.

Este documento sirve como referencia para la toma de decisiones de producto, arquitectura, desarrollo y priorización del roadmap.

---

# Objetivo

Delimitar el alcance del MVP para validar el modelo de crédito empresarial basado en datos transaccionales, permitiendo ofrecer una solución financiera escalable, sostenible y alineada con los objetivos estratégicos del negocio.

---

# Contexto

Fliipa es una plataforma de crédito rotativo B2B orientada a micro y pequeñas empresas, especialmente tenderos y comerciantes, diseñada para facilitar el acceso al crédito formal mediante el análisis de información transaccional y comportamiento comercial.

Durante el MVP, el crédito estará disponible para ser utilizado en tiendas D1, permitiendo validar el modelo de negocio, la aceptación del mercado y el desempeño del modelo de riesgo antes de su expansión a nuevos comercios y productos financieros.

La primera etapa busca establecer las bases para una plataforma financiera digital sustentada en datos transaccionales, automatización de procesos y generación de información crediticia.

---

# Alcance del MVP

La primera versión del producto comprende los siguientes procesos de negocio.

## 1. Captación comercial

Incluye:

- Contacto inicial con clientes preaprobados.
- Campañas comerciales.
- Comunicación mediante WhatsApp.
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

- Validación biométrica con posible proveedor externo, aún por confirmar, para verificación de identidad (KYC).
- Validación automática del resultado.
- Gestión de casos en revisión.
- Rechazo automático cuando corresponda.

---

## 4. Evaluación del riesgo

Incluye:

- Consulta de Experian.
- Consulta del historial transaccional de D1.
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

- Administración del cupo rotativo.
- Consulta del estado del crédito.
- Consulta del plan de pagos.
- Consulta del saldo disponible.
- Liberación automática del cupo cuando el crédito sea cancelado.

---

## 7. Uso del crédito

Incluye:

- Generación del bono D1.
- Compra en tiendas D1.
- Bloqueo temporal del cupo durante la compra.
- Evaluación para renovación del cupo.

---

## 8. Gestión de pagos

Incluye:

- Débito automático mediante Druo.
- Pago por PSE.
- Prepago.
- Actualización automática del saldo.
- Liquidación del crédito.

---

## 9. Cobranza

Incluye:

- Reintentos automáticos de débito.
- Recordatorios de pago.
- Bloqueo del cupo.
- Acuerdos de pago.
- Reestructuración de obligaciones.
- Reporte a centrales de riesgo.
- Cobro jurídico.
- Castigo de cartera.

---

## 10. Servicio al cliente

Incluye:

- Atención mediante asistente virtual basado en IA.
- Escalamiento a agentes humanos.
- Atención mediante WhatsApp.
- Atención telefónica.
- Gestión de PQRS.
- Medición de satisfacción mediante NPS y CSAT.

---

## 11. Portal administrativo

Incluye:

- Gestión de clientes.
- Gestión de solicitudes.
- Seguimiento del onboarding.
- Consulta del resultado del análisis de riesgo.
- Administración del proceso de originación.
- Seguimiento del ciclo de vida del crédito.
- Gestión de cobranza.
- Gestión de campañas comerciales.
- Consulta de indicadores operativos.

---

# Integraciones incluidas

El MVP contempla integración con los siguientes sistemas externos. Para información detallada sobre cada integración, incluyendo especificaciones técnicas, costos, riesgos y SLAs, consulte la documentación en la carpeta de Integraciones.

| Sistema | Propósito | Documentación |
|----------|-----------|---------------|
| D1 | Información transaccional y utilización del bono. | [Ver integración](../tecnico/Integraciones/D1.md) |
| Experian | Consulta de riesgo crediticio. | [Ver integración](../tecnico/Integraciones/Experian.md) |
| Druo | Débito automático para el recaudo de pagos. | [Ver integración](../tecnico/Integraciones/Druo.md) |
| Proveedor de biometría (por confirmar) | Validación biométrica y verificación de identidad (KYC). | Pendiente de definir |
| Zenvia | Gestión de notificaciones y comunicaciones con clientes mediante WhatsApp y otros canales habilitados. | [Ver integración](../tecnico/Integraciones/Zenvia.md) |
| Google Cloud Platform | Infraestructura y servicios del producto. | [Ver Infraestructura](../tecnico/infraestructura.md) |
| Core Bancario | Originación y administración del crédito. | [Ver integración](../tecnico/Integraciones/CoreBancario.md) |

---

# Fuera del alcance

No forman parte del MVP:

- Aplicación móvil nativa.
- Productos de ahorro.
- Productos de inversión.
- Tarjetas de crédito.
- Seguros.
- Marketplace financiero.
- Programas de fidelización.
- Múltiples perfiles administrativos.
- Gestión completa de oficinas.
- Productos para personas naturales.
- Analítica avanzada basada en inteligencia artificial.
- Consultas en lenguaje natural sobre la base de datos mediante IA.

---

# Restricciones

Durante la primera versión:

- El producto estará dirigido a micro y pequeñas empresas, especialmente tenderos y comerciantes.
- Durante el MVP, el crédito podrá utilizarse únicamente para realizar compras en tiendas D1.
- La solución contará con un portal administrativo para uso interno y aplicaciones desarrolladas bajo una arquitectura de microfrontends.
- El producto estará orientado a validar el modelo de negocio antes de escalar la operación.

# Criterios de priorización

Las funcionalidades serán priorizadas cuando aporten a alguno de los siguientes objetivos.

| Prioridad | Objetivo |
|-----------|----------|
| Alta | Validar el modelo de negocio. |
| Alta | Reducir el fraude. |
| Alta | Disminuir el riesgo crediticio. |
| Alta | Mejorar la experiencia del cliente. |
| Alta | Aumentar el uso del crédito. |
| Alta | Garantizar la sostenibilidad financiera. |
| Media | Automatizar procesos internos relacionados con la originación del crédito. |
| Baja | Funcionalidades de mejora continua. |

---

# Beneficios esperados

La implementación del alcance definido permitirá:

- Facilitar el acceso al crédito empresarial para micro y pequeñas empresas.
- Incrementar la recurrencia de compra en tiendas D1.
- Aumentar el ticket promedio.
- Evaluar el riesgo mediante datos transaccionales propios.
- Disminuir el fraude.
- Construir historial crediticio para pequeños comerciantes.
- Generar información crediticia basada en datos transaccionales que fortalezca la estrategia de datos del Grupo Santo Domingo.
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
