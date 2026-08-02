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

Su modelo de amenazas cubre la Fase 1 read-only cerrada y la extensión
gobernada `controlled-proposal`, siempre como tooling externo,
determinista y sin autoridad operativa.

La aceptación de ese modelo:

- documenta amenazas, controles verificados y brechas conocidas;
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
Controlled-proposal aprobado
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
- validación estructural básica de Markdown y de archivos YAML
  independientes;
- validación de enlaces Markdown relativos y metadatos cubiertos;
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

Controles adicionales de `controlled-proposal`:

- escritura limitada a una rama aislada del Vault;
- allowlist de documentos, que actualmente mantiene snapshots fuera del
  alcance de escritura;
- PR obligatoriamente draft;
- ausencia de force-push, aprobación y merge;
- identidad exacta de la propuesta pendiente;
- reconciliación posterior a una decisión humana verificable.

Brechas técnicas conocidas:

- no existe revalidación del contenido final después de escribir;
- no se validan frontmatter YAML ni wikilinks;
- la denylist explícita usa `09-snapshots/**` en vez de
  `09-repository-snapshots/**`;
- una falla posterior a crear la PR puede dejar identidad remota sin
  persistencia local;
- los informes declaran `scheduled-detection` aunque el modo vigente es
  `manual-on-demand`.

Riesgos residuales documentados:

- error humano durante la revisión;
- publicación accidental de evidencia sensible;
- ampliación prematura de permisos;
- respaldo remoto sin revisión previa;
- falsos positivos y falsos negativos;
- deriva futura de políticas;
- TOCTOU entre push, PR y persistencia local;
- compromiso de credenciales con permiso sobre el Vault;
- rama o PR huérfana ante un fallo remoto;
- validadores documentales incompletos;
- diferencias entre Windows y CI.

El modelo no constituye un componente del Security Control Plane.

Fase 2 y posteriores permanecen no aprobadas.

Cualquier fase con escritura requerirá un nuevo modelo de amenazas, permisos mínimos, estrategia de credenciales, rollback y aprobación humana explícita.
