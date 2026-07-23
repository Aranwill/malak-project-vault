---
document_id: VAULT-SECURITY-INDEX-001
title: Índice de seguridad
document_type: navigation
status: active
authority: derived
operational_authority: none
last_reviewed: 2026-07-22
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

Este índice no declara implementado ningún componente de seguridad de Malāk.

El Vault Synchronization Agent permanece fuera del Security Control Plane, del Kernel y del runtime.

Su modelo de amenazas de Fase 1 fue aceptado y cerrado exclusivamente para una herramienta externa, determinista y de solo lectura.

La aceptación de ese modelo:

- documenta amenazas y controles verificados;
- registra riesgos residuales;
- no convierte al agente en un control de seguridad de Malāk;
- no concede autoridad operativa;
- no autoriza fases posteriores;
- no modifica el baseline operativo de Malāk.

## Navegación relacionada

- [[00-governance/DOCUMENT_AUTHORITY_MODEL|Modelo de autoridad documental]]
- [[02-current-baseline/CURRENT_BASELINE|Baseline vigente]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[07-audits/AUDIT_INDEX|Auditorías]]
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

## Modelos de amenazas documentados

- [[06-security/VAULT_SYNCHRONIZATION_THREAT_MODEL|Modelo de amenazas del Vault Synchronization Agent]]

Estado:

```text
accepted
```

Alcance:

```text
Fase 1 completada y cerrada
```

Autoridad operativa:

```text
none
```

Controles verificados durante la Fase 1:

- comandos Git auditados como read-only;
- validación de repositorio, rama y `HEAD`;
- allowlist y denylist;
- controles TOCTOU;
- validación de rutas;
- validación de Markdown y YAML;
- validación de enlaces y metadatos;
- hashes SHA-256;
- sanitización de evidencia;
- límites de tamaño y alcance;
- lock de ejecución;
- polling externo;
- invariantes de no modificación;
- `last_applied_commit: null`;
- Malāk intacto;
- Vault intacto;
- cero modificaciones de snapshots históricos.

Riesgos residuales documentados:

- error humano durante la revisión;
- publicación accidental de evidencia sensible;
- ampliación prematura de permisos;
- respaldo remoto sin revisión previa;
- falsos positivos y falsos negativos;
- deriva futura de políticas;
- TOCTOU en una eventual fase con escritura;
- compromiso de credenciales en fases posteriores.

El modelo no constituye un componente del Security Control Plane.

Fase 2 y posteriores permanecen no aprobadas.

Cualquier fase con escritura requerirá un nuevo modelo de amenazas, permisos mínimos, estrategia de credenciales, rollback y aprobación humana explícita.
