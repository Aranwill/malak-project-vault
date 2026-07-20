---
document_id: VAULT-SECURITY-INDEX-001
title: Índice de seguridad
document_type: navigation
status: active
authority: derived
operational_authority: none
last_reviewed: 2026-07-20
tags:
  - malak
  - vault
  - security
  - navigation
---

# Índice de seguridad

> [!danger] Sin autoridad operativa
> Este documento no implementa, habilita ni modifica controles de seguridad de Malāk.
>
> Los controles efectivos deben existir y validarse en el repositorio oficial o en la infraestructura correspondiente.

## Propósito

Esta sección organiza conocimiento derivado relacionado con:

- modelo de autoridad;
- límites de confianza;
- políticas de autorización;
- amenazas y riesgos;
- controles propuestos;
- validaciones de seguridad;
- incidentes y hallazgos;
- decisiones pendientes.

## Estado actual

No se declara desde este índice que una iniciativa futura de seguridad esté implementada.

La presencia de conceptos de seguridad en el roadmap, el Vault o documentos de diseño no constituye evidencia de implementación.

## Navegación relacionada

- [[00-governance/DOCUMENT_AUTHORITY_MODEL|Modelo de autoridad documental]]
- [[02-current-baseline/CURRENT_BASELINE|Baseline vigente]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[07-audits|Auditorías]]
- [[10-knowledge-index/KNOWLEDGE_INDEX|Índice maestro]]

## Principios aplicables

- Human in Control.
- Denegación por defecto.
- Separación entre solicitar, autorizar, ejecutar y auditar.
- Menor privilegio.
- Defensa en profundidad.
- Zero Trust interno.
- Validación explícita de entradas y límites.
- Trazabilidad de decisiones y acciones.
- Ningún LLM constituye por sí mismo una autoridad de seguridad.
- Una propuesta de seguridad no equivale a un control implementado.

## Clasificación recomendada

Los futuros documentos de esta sección deberán identificarse como uno de los siguientes tipos:

- modelo de amenaza;
- evaluación de riesgo;
- propuesta de control;
- especificación de seguridad;
- validación;
- hallazgo;
- incidente;
- decisión;
- referencia derivada.

## Restricción permanente

El Vault no debe almacenar secretos operativos, credenciales, tokens, claves privadas ni datos sensibles necesarios para ejecutar Malāk.
