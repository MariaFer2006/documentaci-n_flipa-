# Casos de uso

## Objetivo

Definir los escenarios principales de interacción entre los actores y el sistema de Flipa.

## Alcance

Este documento presenta los casos de uso más relevantes para la primera versión del sistema, especialmente el proceso de gestión de crédito empresarial.

## Responsable

Producto y QA

## Fecha de actualización

2026-07-07

## Estado

En revisión

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
- [Historias Usuario](../03-historias-usuario/01-historias-usuario.md)
- [Requerimientos Funcionales](../04-requerimientos/01-requerimientos-funcionales.md)
- [Requerimientos No Funcionales](../04-requerimientos/02-requerimientos-no-funcionales.md)

## Contenido

### Caso de uso 1: registrar una solicitud de crédito

Actor principal: administrador.

Objetivo: capturar una nueva solicitud de crédito para un cliente empresarial.

Flujo principal:
1. El administrador ingresa a la aplicación.
2. Crea una nueva solicitud.
3. Asocia la información del cliente y del negocio.
4. Registra el estado inicial de la solicitud.

### Caso de uso 2: evaluar riesgo

Actor principal: administrador.

Objetivo: analizar si la solicitud cumple con criterios de negocio y riesgo.

Flujo principal:
1. El administrador revisa la información del cliente.
2. Evalúa los datos de comportamiento comercial y transaccional.
3. Determina si la solicitud procede o requiere revisión adicional.

### Caso de uso 3: decidir aprobación o rechazo

Actor principal: administrador.

Objetivo: tomar una decisión formal sobre la solicitud.

### Caso de uso 4: dar seguimiento al crédito

Actor principal: administrador.

Objetivo: registrar y monitorear el cumplimiento del crédito una vez aprobado.
