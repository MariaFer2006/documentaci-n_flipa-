# Actores del negocio

| Documento | Actores del negocio |
|-----------|----------------------|
| **Proyecto** | Fliipa |
| **Versión** | 1.4 |
| **Estado** | En revisión |
| **Responsable** | Negocio y operaciones |
| **Última actualización** | 2026-07-09 |

---

## Control de versiones

| Versión | Fecha | Autor | Descripción |
|---------|-------|-------|-------------|
| 1.0 | 2026-07-07 | María Fernanda Herazo | Creación inicial del documento. |
| 1.1 | 2026-07-08 | María Fernanda Herazo | Se agregaron actores comerciales, de cobranza y proveedores externos; |
| 1.2 | 2026-07-08 | María Fernanda Herazo | Se agregaron Colpatria (core bancario/fiducia), analista de riesgo, agente de servicio al cliente y asistente virtual (IA), con base en los Journeys Colpatria B2B. |
| 1.3 | 2026-07-09 | María Fernanda Herazo | Se actualiza el proveedor de biometría (Olimpia, antes "por confirmar") y se agregan Zenvia y Sendgrid como proveedores externos de notificaciones, con base en los Journeys Colpatria B2B y la documentación técnica de integraciones. |
| 1.4 | 2026-07-09 | María Fernanda Herazo | Se corrige el bucket del analista jurídico/abogado (bucket 4, no bucket 3) y se ajustan las descripciones de Hunter/visitador y Analista de cartera para citar de forma precisa la fuente de cada rol, con base en el Modelo y Proceso de Cobranza B2B e Investigación B2B. |

---

## Objetivo

Identificar los principales actores involucrados en el ecosistema de Fliipa y su rol dentro del proceso de crédito empresarial.

## Alcance

Este documento describe a los actores de negocio, operativos y de soporte que interactúan con el producto o se ven impactados por él.

## Documentos relacionados

- [Negocio](README.md)
- [Flipa - Biblioteca de Conocimiento](../README.md)
- [Mapa Del Conocimiento](../MAPA_DEL_CONOCIMIENTO.md)
- [Onboarding](../ONBOARDING.md)
- [Convenciones](../CONVENCIONES.md)
- [Producto](../producto/README.md)
- [Funcional](../funcional/README.md)
- [Qa](../qa/README.md)
- [Descripcion Negocio](descripcion-negocio.md)
- [Procesos](procesos.md)
- [Indicadores](indicadores.md)
- [Reglas Negocio](reglas-negocio.md)

## Contenido

### Actores principales

- Cliente empresarial: micro o pequeña empresa que compra frecuentemente en D1 y solicita financiamiento.
- Administrador del producto: persona interna que revisa, aprueba, rechaza o gestiona solicitudes.
- Equipo de negocio y operaciones: responsable de definir criterios, seguimiento y viabilidad del modelo.
- D1: canal comercial que aporta contexto y relación con el cliente.
- Sumz: empresa responsable de la operación financiera y del objetivo de sostenibilidad del negocio.
- Grupo Santo Domingo: entidad estratégica que ve en Flipa una oportunidad de crecimiento financiero.

### Actores comerciales y de cobranza

- Asesor comercial: realiza la captación por llamada, correo y WhatsApp, aplica el speech comercial y acompaña al cliente durante la originación (Modelo Comercial B2B).
- Hunter / visitador: realiza la visita de originación en el negocio del cliente, apoyando el KYC y la firma del contrato (Modelo Comercial B2B). Las visitas de confirmación y verificación y la visita de cobro y gestión especial están documentadas como procesos en el Modelo y Proceso de Cobranza B2B, pero esa fuente no asigna explícitamente el rol que las ejecuta; se asume el mismo Hunter/visitador, pendiente de confirmar con negocio.
- Analista de cartera: ejecuta la gestión de cobranza por bucket descrita en el Modelo y Proceso de Cobranza B2B (llamadas, WhatsApp, seguimiento de compromisos de pago); aparece nombrado explícitamente como primer nivel de escalación en Investigación B2B, antes del Líder de Cartera.
- Comité de Cartera: instancia semanal que analiza la cartera y prioriza la gestión de cobro. Está conformado, entre otros, por un Senior Credit Strategy Analyst (estrategia de riesgo crediticio) y un Account and Portfolio Specialist / Product Manager (gestión de cuentas y portafolio), según el Modelo y Proceso de Cobranza B2B.
- Analista jurídico / abogado: gestiona la comunicación directa del área jurídica a partir del bucket 4 (91-120 días de mora, según el Modelo y Proceso de Cobranza B2B) y lleva los casos a proceso legal a partir del bucket 5.
- Administrador del punto (tienda D1): contacto de escalamiento en el bucket 1 (1-30 días de mora) cuando la gestión por WhatsApp y llamada no logra ubicar al responsable del negocio deudor (Investigación B2B).

### Actores de riesgo y servicio al cliente

- Analista de riesgo: resuelve manualmente los casos de biometría que quedan "en revisión" durante el KYC automático.
- Asistente virtual (IA): atiende el primer nivel de servicio al cliente (WhatsApp, correo, llamada), clasifica el caso e intenta resolverlo en el primer contacto.
- Agente humano de servicio al cliente: recibe los casos que la IA no logra resolver, con el contexto completo; valida identidad y aprueba manualmente los casos críticos (suplantación, uso indebido del cupo, desconocimiento de compra).

### Proveedores externos

- Experian: consulta de riesgo crediticio.
- Druo: débito automático para el recaudo de pagos.
- Olimpia: validación biométrica y verificación de identidad (KYC).
- Zenvia: gestión de notificaciones y comunicaciones con clientes (WhatsApp, correo y SMS) durante el onboarding y la operación.
- Sendgrid: envío de comunicaciones por correo electrónico, en conjunto con Zenvia, durante el onboarding.
- Colpatria: aliado de core bancario; administra la fiducia que fondea el crédito, concentra el origen y el retorno del dinero, y emite el bono que el cliente usa en D1.

### Relación entre actores

El cliente accede al producto a través del contexto comercial de D1; el negocio evalúa su riesgo y el administrador gestiona el proceso dentro del sistema. Durante la vida del crédito, el asesor comercial y el analista de cartera acompañan al cliente, y el Comité de Cartera prioriza los casos que requieren gestión especial o escalamiento jurídico. El resultado de esta gestión impacta directamente la relación comercial y la salud financiera del portafolio.

## Fuentes consultadas

- Journeys Colpatria B2B, junio 2026 — *Journeys Fran finales-1.pdf*
- Integraciones técnicas — Olimpia y Zenvia (`tecnico/Integraciones/Olimpia.md`, `tecnico/Integraciones/Zenvia.md`)
- Alcance del Producto (`producto/alcance.md`)
- Modelo Comercial B2B — *Modelo Comercial B2B.pptx*
- Modelo y Proceso de Cobranza B2B — *Modelo Cobranza/Modelo_de_Cobranza_B2B_.pptx* y *Modelo Cobranza/Modelo y gestion de cobranza.docx*
- Investigación B2B — *Modelo Cobranza/Investigacion B2B.docx*

## Fuentes consultadas

- Journeys Colpatria B2B, junio 2026 — *Journeys Fran finales-1.pdf*
- Integraciones técnicas — Olimpia y Zenvia (`tecnico/Integraciones/Olimpia.md`, `tecnico/Integraciones/Zenvia.md`)
- Alcance del Producto (`producto/alcance.md`)

El cliente accede al producto a través del contexto comercial de D1; el negocio evalúa su riesgo y el administrador gestiona el proceso dentro del sistema. Durante la vida del crédito, el asesor comercial y el analista de cartera acompañan al cliente, y el Comité de Cartera prioriza los casos que requieren gestión especial o escalamiento jurídico. El resultado de esta gestión impacta directamente la relación comercial y la salud financiera del portafolio.
