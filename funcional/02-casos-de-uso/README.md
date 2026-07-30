# Casos De Uso

| Documento | Casos De Uso |
|-----------|----------------|
| **Proyecto** | Fliipa |
| **Versión** | 3.1 |
| **Estado** | En revisión |
| **Responsable** | Producto y QA |
| **Última actualización** | 2026-07-30 |

---

## Control de versiones

| Versión | Fecha | Autor | Descripción |
|---------|-------|-------|-------------|
| 0.1 | 2026-07-07 | Producto y QA | Primera versión: 4 casos de uso narrativos, sin identificador formal, centrados en el actor administrador. |
| 2.0 | 2026-07-29 | Revisión asistida por Claude | Reorganización: un archivo por caso de uso, siguiendo el mismo formato usado en [Actores](../../negocio/Actores/README.md) y [Procesos](../../negocio/procesos/README.md). Se preserva el contenido original sin modificarlo. **Pendiente:** ampliar de 4 a los 18 casos de uso (CU-001 a CU-018) que ya referencia [Historias de Usuario](../03-historias-usuario/README.md). |
| 2.1 | 2026-07-29 | Revisión asistida por Claude | Se agrega un diagrama de caso de uso (Mermaid `flowchart`) en cada archivo individual y un diagrama combinado en este README, con la relación «include» entre CU-3 y CU-2. |
| 2.2 | 2026-07-29 | Revisión asistida por Claude | Se reemplazan los diagramas Mermaid por diagramas de caso de uso UML reales (SVG, carpeta `diagramas/`). |
| 2.3 | 2026-07-29 | Revisión asistida por Claude | Se ajusta la paleta de los diagramas a los colores de marca. Se agrega [00-caso-de-uso-general.md](00-caso-de-uso-general.md). |
| 2.4 | 2026-07-30 | Revisión asistida por Claude | Se corrige el actor de los 4 casos de uso originales tras validar contra `services/` (no revisada antes): CU-1 → cliente empresarial; CU-2 y CU-3 → sí tienen respaldo real en código (antes marcados como "no verificables"); CU-4 → administrador / analista de cartera. |
| **3.0** | **2026-07-30** | **Revisión asistida por Claude** | **Ampliación completa de 4 a los 18 casos de uso** (CU-001 a CU-018) referenciados por [Historias de Usuario](../03-historias-usuario/README.md), con numeración `CU-XXX` formal. Se reasigna el contenido de los 4 casos de uso originales dentro de la nueva numeración: "registrar solicitud" → CU-001; "evaluar riesgo" se retitula "conocer el cupo preaprobado" → CU-002; "decidir aprobación o rechazo" se divide en CU-008 (aprobación automática, llenando un vacío de numeración que ya existía en Historias de Usuario) y se fusiona con CU-015 (override manual del administrador); "dar seguimiento al crédito" se fusiona con CU-015 (buscar cliente / ajustar cupo / seguimiento, todas acciones del mismo panel administrativo). Se crean 14 casos de uso nuevos (CU-003 a CU-007, CU-009 a CU-014, CU-016 a CU-018), cada uno validado contra `credits-platform-main` y con su propio hallazgo de implementación (implementado, parcial, o sin respaldo en código). Ver el detalle de cobertura en [00-caso-de-uso-general.md](00-caso-de-uso-general.md#alcance-actual). |
| **3.1** | **2026-07-30** | **Revisión asistida por Claude** | Se rehacen todos los diagramas: un diagrama UML individual por cada uno de los 18 casos de uso (actor con notación de monigote, caso de uso como óvalo, límite del sistema), más un diagrama general que agrupa los 18 en las 5 etapas del flujo, con la relación «include» de CU-008 hacia CU-002 y CU-006. Se eliminan los 2 diagramas huérfanos de la numeración anterior ("decidir aprobación o rechazo" y "dar seguimiento al crédito" sueltos). |

---

## Objetivo

Definir los escenarios principales de interacción entre los actores y el sistema de Fliipa.

## Alcance

Este documento cubre los 18 casos de uso (CU-001 a CU-018) que ya referenciaba [Historias de Usuario](../03-historias-usuario/README.md), correspondientes a 10 de los 11 procesos de negocio definidos en [Alcance del Producto](../../producto/alcance.md) (no incluye "Captación comercial" como caso de uso independiente). Cada caso de uso indica su actor principal, su fuente en el código de `credits-platform-main` cuando existe, y los hallazgos de la validación funcional cuando el comportamiento documentado no coincide con el código.

## Diagrama de casos de uso

![Diagrama de casos de uso: Administrador](diagramas/00-diagrama-general.svg)

> El diagrama agrupa los 18 casos de uso en 5 etapas (originación, administración del crédito, cobranza, servicio al cliente y portal administrativo). CU-008 (*Aprobar y activar la línea de crédito*) incluye a CU-002 y CU-006, porque no puede haber decisión sin evaluación previa. Cada caso de uso tiene además su propio diagrama individual en su documento correspondiente.

## Casos de uso

| CU | Caso de uso | Actor principal | Estado | Documento |
|----|--------------|------------------|--------|-----------|
| — | Caso de uso general (agrupa CU-001 a CU-018) | Mixto | — | [00-caso-de-uso-general.md](00-caso-de-uso-general.md) |
| CU-001 | Registrar una solicitud de crédito | Cliente empresarial | ✅ Implementado | [01-registrar-solicitud-credito.md](01-registrar-solicitud-credito.md) |
| CU-002 | Conocer el cupo preaprobado | Sistema (automático) | ✅ Implementado | [02-evaluar-riesgo.md](02-evaluar-riesgo.md) |
| CU-003 | Confirmar identidad por OTP | Cliente empresarial | ✅ Implementado, con hallazgo de seguridad | [03-confirmar-identidad-otp.md](03-confirmar-identidad-otp.md) |
| CU-004 | Completar KYC y cargar soportes | Cliente empresarial | ⚠️ Parcial (sin biometría automatizada) | [04-completar-kyc.md](04-completar-kyc.md) |
| CU-005 | Resolver manualmente casos de KYC en revisión | Analista de riesgo | ❌ Sin respaldo en código | [05-resolver-kyc-en-revision.md](05-resolver-kyc-en-revision.md) |
| CU-006 | Conocer el resultado de la evaluación (score, Experian, D1) | Cliente empresarial / Analista de riesgo | ⚠️ Parcial (mocks) | [06-conocer-resultado-evaluacion.md](06-conocer-resultado-evaluacion.md) |
| CU-007 | Firmar contrato y pagaré | Cliente empresarial | ✅ Implementado | [07-firmar-contrato-pagare.md](07-firmar-contrato-pagare.md) |
| CU-008 | Aprobar y activar la línea de crédito | Sistema (automático), override del Administrador | ✅ Implementado | [08-aprobar-activar-linea-credito.md](08-aprobar-activar-linea-credito.md) |
| CU-009 | Consultar cupo, plan de pagos y movimientos | Cliente empresarial | ✅ Implementado | [09-consultar-cupo-plan-pagos.md](09-consultar-cupo-plan-pagos.md) |
| CU-010 | Usar el cupo en tienda D1 | Cliente empresarial | ✅ Implementado, con hallazgo | [10-usar-cupo-tienda-d1.md](10-usar-cupo-tienda-d1.md) |
| CU-011 | Pagar por débito automático o prepago | Cliente empresarial | ⚠️ Parcial | [11-pagar-debito-prepago.md](11-pagar-debito-prepago.md) |
| CU-012 | Cobranza y segmentación por mora | Analista de cartera / Comité de Cartera | ⚠️ Parcial (cobranza sí, buckets no) | [12-cobranza-segmentacion-mora.md](12-cobranza-segmentacion-mora.md) |
| CU-013 | Alivios de pago | Cliente empresarial / Comité de Cartera | ❌ Sin respaldo en código | [13-alivios-pago.md](13-alivios-pago.md) |
| CU-014 | Atención por IA, escalamiento y validación en casos críticos | Cliente empresarial / Agente de servicio | ❌ Sin respaldo en código | [14-atencion-ia-escalamiento.md](14-atencion-ia-escalamiento.md) |
| CU-015 | Buscar cliente, historial auditado, ajustar cupo/corte y seguimiento | Administrador del producto | ✅ Implementado, con hallazgo | [15-buscar-cliente-ajustar-cupo.md](15-buscar-cliente-ajustar-cupo.md) |
| CU-016 | Simular plan de pago con distintas tasas | Administrador del producto | ✅ Implementado | [16-simular-plan-pago-admin.md](16-simular-plan-pago-admin.md) |
| CU-017 | Administrar la lista negra (blacklist) | Administrador del producto | ✅ Implementado, sin enforcement | [17-administrar-blacklist.md](17-administrar-blacklist.md) |
| CU-018 | Monitorear la salud del sistema en tiempo real | Administrador con rol de sistema | ⚠️ Parcial | [18-monitorear-salud-sistema.md](18-monitorear-salud-sistema.md) |

## Documentos relacionados

- [Funcional](../README.md)
- [Flipa - Biblioteca de Conocimiento](../../README.md)
- [Mapa Del Conocimiento](../../MAPA_DEL_CONOCIMIENTO.md)
- [Onboarding](../../ONBOARDING.md)
- [Convenciones](../../CONVENCIONES.md)
- [Negocio](../../negocio/README.md)
- [Tecnico](../../tecnico/README.md)
- [Qa](../../qa/README.md)
- [Documento Funcional](../01-marco-funcional/01-documento-funcional.md)
- [Historias Usuario](../03-historias-usuario/README.md)
- [Requerimientos Funcionales](../04-requerimientos/01-requerimientos-funcionales.md)
- [Requerimientos No Funcionales](../04-requerimientos/02-requerimientos-no-funcionales.md)

## Responsable

Producto y QA

## Fuentes consultadas

- Contenido original: `funcional/02-casos-de-uso/01-casos-de-uso.md` (versión 2026-07-07).
- [Historias de Usuario v1.4](../03-historias-usuario/01-historias-usuario.md), como fuente de la numeración `CU-001` a `CU-018` y de la relación caso de uso ↔ historia ↔ requerimiento.
- Revisión directa del código fuente de `credits-platform-main` (incluyendo `services/core/*`, `services/product/*`, `gateways/core-hub`, `backends/admin`, `backends/b2b`, `apps/admin`, `apps/checkout`, `apps/redemption`), realizada como parte de la ampliación v3.0.
