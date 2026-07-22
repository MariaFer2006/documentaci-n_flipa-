# Historias Usuario

| Documento | Historias Usuario |
|-----------|---------------------|
| **Proyecto** | Fliipa |
| **VersiÃ³n** | 1.2 |
| **Estado** | En revisiÃ³n |
| **Responsable** | Producto y negocio |
| **Ãšltima actualizaciÃ³n** | 2026-07-10 |

---

## Control de versiones

| VersiÃ³n | Fecha | Autor | DescripciÃ³n |
|---------|-------|-------|-------------|
| 0.1 | 2026-07-06 | Maria Fernanda Herazo | Borrador vacÃ­o (pendiente de completar). |
| 1.0 | 2026-07-10 | MarÃ­a Fernanda Herazo | Primera versiÃ³n completa: 28 historias de usuario por actor, en lÃ­nea con Actores y Casos de Uso. |
| 1.1 | 2026-07-10 | MarÃ­a Fernanda Herazo  | Se organizan las historias en tablas por actor, con prioridad y casos de uso relacionados. |
| 1.2 | 2026-07-10 | MarÃ­a Fernanda Herazo | Se convierte cada historia en una ficha individual (formato adaptado de plantilla de actor: descripciÃ³n, criterios de aceptaciÃ³n, relaciones, referencias, autor/fecha/versiÃ³n y comentarios). |

---

## Objetivo

Describir las necesidades de cada actor de Fliipa en lenguaje de negocio, como base para la priorizaciÃ³n y el desarrollo de las funcionalidades del sistema.

## Alcance

 Cubre historias de usuario para el cliente empresarial (tendero), el asesor comercial, el analista de riesgo, el analista de cartera, el agente de servicio al cliente y el administrador del producto, en lÃ­nea con los actores descritos en [Actores](../../negocio/Actores/README.md) y los casos de uso en [Casos De Uso](../02-casos-de-uso/01-casos-de-uso.md). Usa la numeraciÃ³n `HU-XXX` definida en [Convenciones](../../CONVENCIONES.md).

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
- [Casos De Uso](../02-casos-de-uso/01-casos-de-uso.md)
- [Requerimientos Funcionales](../04-requerimientos/01-requerimientos-funcionales.md)
- [Requerimientos No Funcionales](../04-requerimientos/02-requerimientos-no-funcionales.md)

## Contenido

Cada historia se documenta como una ficha individual, con el mismo espÃ­ritu de la plantilla de especificaciÃ³n de actor: identificador, descripciÃ³n, criterios de aceptaciÃ³n (equivalente a "caracterÃ­sticas"), relaciones con otros elementos del desarrollo, referencias de origen, control de autor/fecha/versiÃ³n y comentarios adicionales.

### Cliente empresarial (tendero)

#### HU-001: Recibir enlace Ãºnico de solicitud

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-001</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero recibir un enlace Ãºnico de solicitud por WhatsApp, para poder iniciar mi proceso de crÃ©dito sin tener que buscarlo.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El cliente recibe el enlace por WhatsApp como parte del contacto simultÃ¡neo (correo, WhatsApp, llamada). El enlace crea un checkout nuevo o reanuda uno existente en <code>REQUEST_STARTED</code> para su documento.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-001, CU-002. Historias relacionadas: HU-002, HU-013.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/procesos/01-captacion-comercial.md">Procesos</a>; <code>backends/b2b/src/controllers/checkouts/create-checkout.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">â€”</div>

#### HU-002: Ver cupo preaprobado antes de completar el formulario

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-002</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero ver mi cupo preaprobado antes de completar todo el formulario, para decidir si vale la pena continuar. | 
| **Prioridad** | Alta |
| **Criterios de aceptaciÃ³n** | El sistema muestra el cupo preaprobado calculado a partir del histÃ³rico de consumo en D1, antes de exigir todos los pasos del onboarding. |
| **Relaciones** | Casos de uso: CU-002. Requerimiento: RF-005. |
| **Referencias** | <a href="../../negocio/procesos/02-onboarding-digital.md">Procesos</a> |
| **Autor / Fecha / VersiÃ³n** | MarÃ­a Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | RF-005 estÃ¡ marcado como "no verificable" en el cÃ³digo de <code>backends/b2b</code> disponible; validar con el equipo tÃ©cnico dÃ³nde vive el cÃ¡lculo. |

#### HU-003: Confirmar identidad por OTP

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero confirmar mi identidad con un cÃ³digo enviado por WhatsApp, correo o SMS, para proteger mi cuenta sin procesos complicados.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El cliente recibe un OTP por el canal elegido y puede solicitar reenvÃ­o tras 60 segundos, con un mÃ¡ximo de 3 intentos.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-003. Requerimiento: RF-006.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/b2b/src/controllers/otp/send-otp.ts</code>, <code>otp/validate-otp.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">Ver hallazgo de seguridad RNF-001 (cÃ³digo comodÃ­n de OTP) y RNF-007 (canal SMS no envÃ­a realmente el mensaje).</div>

#### HU-004: Completar KYC y cargar soportes desde el celular

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-004</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero completar la validaciÃ³n biomÃ©trica y cargar mis extractos bancarios desde el celular, para no tener que ir a una oficina.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El cliente completa la biometrÃ­a con el proveedor externo y carga certificaciÃ³n bancaria y extractos de los Ãºltimos 3 meses, todo desde el flujo mÃ³vil de onboarding.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-004, CU-005.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/procesos/03-validacion-kyc.md">Procesos</a>; <code>backends/b2b/src/controllers/clients/upload-document.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">No se encontrÃ³ en el cÃ³digo el nombre del proveedor de biometrÃ­a (Olimpia); probablemente vive en un microservicio no incluido en el repositorio revisado.</div>

#### HU-005: Conocer el resultado en mÃ¡ximo 72 horas

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-005</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero conocer el resultado de mi solicitud en mÃ¡ximo 72 horas, para poder planear mis compras en D1.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El cliente recibe notificaciÃ³n de aprobaciÃ³n o rechazo dentro de las 72 horas siguientes a completar la validaciÃ³n de identidad.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-006. Requerimientos: RF-010, RF-011, RF-012.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/reglas-negocio/01-cupo-credito.md">Reglas Negocio</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">La lÃ³gica de invocaciÃ³n real a Experian no se encontrÃ³ en el cÃ³digo de <code>backends/b2b</code> disponible.</div>

#### HU-006: Firmar contrato y pagarÃ© desde el celular

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-006</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero firmar mi contrato y pagarÃ© desde el celular con un cÃ³digo de verificaciÃ³n, para activar mi cupo sin papeleo fÃ­sico.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El cliente revisa el contrato y el pagarÃ©, recibe un OTP de firma vÃ¡lido por 24 horas, y el sistema genera el PDF firmado y lo envÃ­a por correo.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-007. Requerimientos: RF-013, RF-014.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/b2b/src/controllers/otp/send-signature-otp.ts</code>, <code>clients/sign-contract.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">La firma se bloquea 24 horas tras agotar los intentos (RNF-013).</div>

#### HU-007: Consultar cupo, plan de pagos y movimientos

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-007</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero consultar mi cupo disponible, mi plan de pagos y mis movimientos, para saber cuÃ¡nto puedo usar y cuÃ¡nto debo.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El cliente accede al dashboard de redenciÃ³n y visualiza cupo disponible, plan de pagos y movimientos, solo si su lÃ­nea de crÃ©dito estÃ¡ en estado <code>approved</code> o <code>active</code>.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-009. Requerimientos: RF-016, RF-017.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/b2b/src/controllers/credit-line/get-credit-status.ts</code>, <code>apps/redemption/actions/auth.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">â€”</div>

#### HU-008: Usar el cupo en tienda D1

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-008</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero generar un cÃ³digo QR o un cÃ³digo de compra para usar mi cupo en la tienda D1, para pagar mi mercancÃ­a sin dinero en efectivo.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El cliente genera un QR con TTL o revela un cÃ³digo de compra, y el punto de venta D1 lo valida para aplicar el cupo a la compra.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-010. Requerimientos: RF-019, RF-020.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/b2b/src/controllers/qr/get-or-create-qr.ts</code>, <code>clients/get-client-coupon.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">Coexisten dos mecanismos de canje (QR y cÃ³digo de compra); pendiente de definir con negocio cuÃ¡l es el vigente.</div>

#### HU-009: Pagar por dÃ©bito automÃ¡tico o prepago

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-009</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero que mi cuota se debite automÃ¡ticamente o poder prepagar por PSE, para no tener que hacer trÃ¡mites adicionales de pago.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El sistema debita automÃ¡ticamente vÃ­a Druo en la fecha de corte, o permite prepago voluntario por PSE en cualquier momento antes del corte.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-011. Requerimiento: RF-022.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/procesos/08-cobro-pago.md">Procesos</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">La ejecuciÃ³n real del prepago por PSE no se encontrÃ³ en el cÃ³digo de <code>backends/b2b</code> disponible.</div>

#### HU-010: Recibir alivios ante dificultades de pago

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-010</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero recibir alivios (abono parcial, congelamiento de intereses) cuando tengo dificultades temporales de pago, para no perder mi cupo ni mi historial.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El cliente puede acceder a abono parcial, congelamiento de intereses o condonaciÃ³n, segÃºn las condiciones y topes definidos por bucket de mora.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-013.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/reglas-negocio/03-alivios-negociacion.md">Reglas Negocio</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">â€”</div>

#### HU-011: Resolver dudas por WhatsApp con respuesta inmediata

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-011</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero resolver mis dudas o reclamos por WhatsApp con respuesta inmediata, para no depender de canales lentos o presenciales.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Un asistente virtual atiende el primer contacto y, si no resuelve el caso, escala a un agente humano con el contexto completo.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-014. Requerimientos: RF-028, RF-029.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/reglas-negocio/09-servicio-cliente.md">Reglas Negocio</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">No se encontrÃ³ un mÃ³dulo de asistente de IA en el cÃ³digo de <code>backends</code> revisado; puede residir en una herramienta externa.</div>

#### HU-012: Recuperar PIN o desbloquear la cuenta

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Cliente empresarial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-012</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como cliente empresarial, quiero recuperar mi PIN si lo olvido o mi cuenta se bloquea, para no perder el acceso a mi cupo.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El cliente puede iniciar un flujo de reseteo de PIN tras un bloqueo por intentos fallidos.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Requerimiento: RNF-014 (bloqueo de acceso).</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/b2b/src/db/models/Client.ts</code> (<code>loginAttempts</code>, <code>lockedAt</code>)</td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Media</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">â€”</div>

### Asesor comercial

#### HU-013: Contacto simultÃ¡neo multicanal

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Asesor comercial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-013</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como asesor comercial, quiero contactar simultÃ¡neamente por correo, WhatsApp y llamada a los clientes preaprobados, para maximizar la tasa de respuesta.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El asesor cuenta con la base de clientes preaprobados y las plantillas de contacto por los tres canales.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-001. Requerimiento: RF-001. Historia relacionada: HU-001.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/procesos/01-captacion-comercial.md">Procesos</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">â€”</div>

#### HU-014: AcompaÃ±ar la originaciÃ³n del cliente

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Asesor comercial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-014</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como asesor comercial, quiero acompaÃ±ar al cliente durante la originaciÃ³n (dudas, visita de confirmaciÃ³n), para reducir el abandono del proceso.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El asesor da seguimiento al cliente durante el onboarding y coordina, cuando aplica, la visita de originaciÃ³n (hunter/visitador).</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-001.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/Actores/03-actores-comerciales-cobranza.md">Actores</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">â€”</div>

#### HU-015: Seguimiento de primera compra

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Asesor comercial</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-015</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como asesor comercial, quiero identificar a los clientes que no han usado su cupo 7 dÃ­as despuÃ©s de la activaciÃ³n, para hacer seguimiento de primera compra.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El asesor recibe o consulta la lista de clientes activados sin uso del cupo a los 7 dÃ­as.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">â€”</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/procesos/01-captacion-comercial.md">Procesos</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Media</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">No se encontrÃ³ un reporte automatizado de este seguimiento en el cÃ³digo revisado.</div>

### Analista de riesgo

#### HU-016: Resolver manualmente casos de biometrÃ­a en revisiÃ³n

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Analista de riesgo</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-016</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como analista de riesgo, quiero revisar manualmente los casos de biometrÃ­a marcados "en revisiÃ³n", para decidir si el cliente puede continuar el proceso.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El analista visualiza los casos "en revisiÃ³n" y registra la decisiÃ³n (continuar o rechazar), notificando al cliente.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-005.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/reglas-negocio/07-kyc-evaluacion-riesgo.md">Reglas Negocio</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">â€”</div>

#### HU-017: Ver score, Experian e histÃ³rico D1 en un solo lugar

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Analista de riesgo</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-017</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como analista de riesgo, quiero ver en un solo lugar el resultado de Experian, el histÃ³rico transaccional de D1 y el score calculado, para validar o ajustar la decisiÃ³n automÃ¡tica.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El analista consulta, para un cliente dado, el resultado de Experian, el histÃ³rico D1 y el score consolidado antes de aprobar o rechazar.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-006. Requerimiento: RF-010.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>companies/lookup-company.ts</code>, <code>institutions/get-advance-score.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">La lÃ³gica de invocaciÃ³n real a Experian no estÃ¡ en el cÃ³digo de <code>backends/b2b</code> disponible.</div>

### Analista de cartera / ComitÃ© de Cartera

#### HU-018: Ver cartera segmentada por bucket de mora

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Analista de cartera</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-018</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como analista de cartera, quiero ver la cartera segmentada por bucket de mora, para priorizar mi gestiÃ³n de cobro diaria.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El analista consulta la cartera agrupada en pago anticipado y buckets 1 a 5, con los datos necesarios para priorizar su gestiÃ³n.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-012.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/reglas-negocio/02-mora-buckets.md">Reglas Negocio</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">Existe una discrepancia documentada entre el esquema de buckets y el journey de Colpatria B2B sobre los plazos de escalamiento (ver RNF-017).</div>

#### HU-019: Registrar cada interacciÃ³n de cobranza

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Analista de cartera</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-019</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como analista de cartera, quiero registrar cada interacciÃ³n de cobranza (canal, tipo de contacto, resultado, compromiso de pago), para mantener trazabilidad completa del caso.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El analista registra canal, tipo de contacto, resultado y monto comprometido de cada interacciÃ³n, quedando disponible en el resumen de atenciÃ³n del cliente.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-012. Requerimientos: RF-025, RF-026.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/b2b/src/controllers/clients/collection-notes.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">Este mÃ³dulo estÃ¡ implementado en el cÃ³digo pero no descrito explÃ­citamente en el alcance de producto (ver informe de hallazgos de negocio y producto).</div>

#### HU-020: Tablero semanal de priorizaciÃ³n del ComitÃ© de Cartera

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">ComitÃ© de Cartera</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-020</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como miembro del ComitÃ© de Cartera, quiero un tablero semanal con los casos priorizados (dÃ­as de mora, monto, historial), para decidir alivios, visitas o escalamiento jurÃ­dico.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El comitÃ© visualiza semanalmente los casos priorizados segÃºn dÃ­as de mora, flujo de caja, cuotas vencidas, historial y monto adeudado.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-012, CU-013.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/reglas-negocio/04-gestion-escalamiento.md">Reglas Negocio</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">No se encontrÃ³ un tablero de priorizaciÃ³n automatizado en el cÃ³digo revisado.</div>

#### HU-021: Recibir casos de escalamiento jurÃ­dico automÃ¡ticamente

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Analista jurÃ­dico / abogado</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-021</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como analista jurÃ­dico, quiero recibir automÃ¡ticamente los casos que llegan al bucket de escalamiento legal, para iniciar el proceso de cobro jurÃ­dico sin depender de un traspaso manual.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Los casos que alcanzan el bucket de escalamiento jurÃ­dico se enrutan automÃ¡ticamente al analista jurÃ­dico.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">â€”</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/Actores/03-actores-comerciales-cobranza.md">Actores</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Media</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">Depende de resolver primero la discrepancia de plazos de escalamiento (RNF-017).</div>

### Agente de servicio al cliente

#### HU-022: Recibir el caso escalado con contexto completo

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Agente de servicio al cliente</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-022</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como agente de servicio al cliente, quiero recibir el caso escalado por la IA con el contexto completo de la conversaciÃ³n, para no pedirle al cliente que repita su problema.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Cuando la IA escala un caso, el agente humano ve el historial completo de la conversaciÃ³n antes de responder.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-014. Requerimiento: RF-028.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/reglas-negocio/09-servicio-cliente.md">Reglas Negocio</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">No verificable en el cÃ³digo de <code>backends</code> disponible.</div>

#### HU-023: Validar identidad en casos crÃ­ticos

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Agente de servicio al cliente</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-023</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como agente de servicio al cliente, quiero validar la identidad del cliente antes de aprobar un caso crÃ­tico (suplantaciÃ³n, uso indebido del cupo), para evitar fraude.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Los casos crÃ­ticos requieren validaciÃ³n de identidad y aprobaciÃ³n manual explÃ­cita del agente antes de cerrarse.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-014. Requerimiento: RF-029.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><a href="../../negocio/reglas-negocio/09-servicio-cliente.md">Reglas Negocio</a></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">â€”</div>

### Administrador del producto (portal administrativo)

#### HU-024: Buscar cliente y ver historial auditado

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Administrador del producto</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-024</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como administrador, quiero buscar un cliente por documento y ver su historial completo de operaciones auditadas, para resolver dudas o disputas rÃ¡pidamente.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El administrador busca por documento y consulta hasta 500 registros de auditorÃ­a del cliente (lÃ­nea de crÃ©dito, desembolsos, pagos).</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-015. Requerimientos: RF-030, RF-031.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/admin/src/controllers/clients.controller.ts</code> (<code>getClientAuditedOperations</code>)</td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Media</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">â€”</div>

#### HU-025: Ajustar cupo o fecha de corte

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Administrador del producto</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-025</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como administrador, quiero ajustar el cupo o la fecha de corte de una lÃ­nea de crÃ©dito, para corregir casos excepcionales autorizados por negocio.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El administrador ajusta <code>lineCap</code> y <code>cutoffDay</code> dentro de los rangos vÃ¡lidos, quedando la acciÃ³n registrada en auditorÃ­a.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-015. Requerimiento: RF-018.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/admin/src/controllers/credit-lines.controller.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Media</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">El rango vÃ¡lido de <code>cutoffDay</code> no es consistente con el de redemption (ver RNF-016).</div>

#### HU-026: Simular plan de pago con distintas tasas

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Administrador del producto</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-026</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como administrador, quiero simular el plan de pago de un cliente en mora con distintas tasas, para preparar acuerdos de pago o alivios.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El administrador ingresa tasa corriente, tasa de mora y umbral de dÃ­as, y obtiene el plan de pago diario descargable en CSV.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-016. Requerimiento: RF-024.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/admin/src/controllers/calculator.controller.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Media</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">â€”</div>

#### HU-027: Administrar la lista negra (blacklist)

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Administrador del producto</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-027</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como administrador, quiero agregar o retirar clientes de la lista negra, para bloquear casos de fraude confirmado.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El administrador agrega o retira clientes de la blacklist, validando que el cliente exista.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-017. Requerimiento: RF-027.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/b2b/src/controllers/blacklist/*.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Alta</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">No se encontrÃ³ enforcement de la blacklist sobre checkout, riesgo o desembolso en el cÃ³digo revisado (ver RF-027).</div>

#### HU-028: Monitorear salud del sistema en tiempo real

<table style="width:100%; border-collapse:collapse; margin:10px 0; font-size:14px;">
  <tr style="background-color:#e8f4ff;">
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Actor</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:42%;">Administrador con rol de sistema (SYS_ADMIN)</td>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; width:18%;">Identificador</th>
    <td style="border:1px solid #c7d7eb; padding:8px; width:22%;">HU-028</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Descripcion</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Como administrador con rol de sistema, quiero ver el estado del core bancario y de la base de datos en tiempo real, para detectar incidentes antes de que afecten a los clientes.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Caracteristicas</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">El administrador de sistema consulta latencia y disponibilidad del core bancario y de Cloud SQL desde el panel.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#f7fbff;">Relaciones</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;">Casos de uso: CU-018. Requerimiento: RF-033.</td>
  </tr>
  <tr>
    <th style="border:1px solid #c7d7eb; padding:8px; text-align:left; background-color:#eefaf2;">Referencias</th>
    <td colspan="3" style="border:1px solid #c7d7eb; padding:8px;"><code>backends/admin/src/controllers/system-core-health.controller.ts</code>, <code>system-cloud-sql.controller.ts</code></td>
  </tr>
  <tr style="background-color:#fff9eb;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Autor</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">MarÃ­a Fernanda Herazo (con asistencia de Claude)</td>
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Fecha</th>
    <td style="border:1px solid #e7d9ad; padding:8px;">2026-07-10</td>
  </tr>
  <tr style="background-color:#fffdf5;">
    <th style="border:1px solid #e7d9ad; padding:8px; text-align:left;">Version</th>
    <td colspan="3" style="border:1px solid #e7d9ad; padding:8px;">1.0</td>
  </tr>
</table>

<table style="width:100%; border-collapse:collapse; margin:8px 0 12px 0; font-size:14px;">
  <tr style="background-color:#f3ebff;">
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Nombre</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left;">Descripcion</th>
    <th style="border:1px solid #d7c9ec; padding:8px; text-align:left; width:22%;">Tipo</th>
  </tr>
  <tr>
    <td style="border:1px solid #d7c9ec; padding:8px;">Prioridad</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Media</td>
    <td style="border:1px solid #d7c9ec; padding:8px;">Clasificacion</td>
  </tr>
</table>

**Comentarios**  
<div style="background-color:#f9fafb; border:1px solid #d9dee6; padding:8px 10px; border-radius:4px;">El monitoreo de "terceros" no cubre a los proveedores de negocio (ver RNF-012).</div>

## Fuentes consultadas

- [Actores](../../negocio/Actores/README.md)
- [Procesos](../../negocio/procesos/README.md)
- [Reglas Negocio](../../negocio/reglas-negocio/README.md)
- [Casos De Uso](../02-casos-de-uso/01-casos-de-uso.md)
- [Requerimientos Funcionales](../04-requerimientos/01-requerimientos-funcionales.md)
- [Requerimientos No Funcionales](../04-requerimientos/02-requerimientos-no-funcionales.md)
- Inventario funcional del cÃ³digo fuente `credits-platform-main`, realizado como parte de esta actualizaciÃ³n.

